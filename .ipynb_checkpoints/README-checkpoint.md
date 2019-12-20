# Kaggle Competition
## Santa Workshop Tour 2019

### Link
https://www.kaggle.com/c/santa-workshop-tour-2019/overview <https://www.kaggle.com/c/santa-workshop-tour-2019/overview>

### Description

Santa has exciting news! For 100 days before Christmas, he opened up tours to his workshop. Because demand was so strong, and because Santa wanted to make things as fair as possible, he let each of the 5,000 families that will visit the workshop choose a list of dates they'd like to attend the workshop.

Now that all the families have sent Santa their preferences, he's realized it's impossible for everyone to get their top picks, so he's decided to provide extra perks for families that don't get their preferences. In addition, Santa's accounting department has told him that, depending on how families are scheduled, there may be some unexpected and hefty costs incurred.

Santa needs the help of the Kaggle community to optimize which day each family is assigned to attend the workshop in order to minimize any extra expenses that would cut into next years toy budget! Can you help Santa out?

### Evaluation

Your submission is scored according to the penalty cost to Santa for suboptimal scheduling. The constraints and penalties are as follows:

The total number of people attending the workshop each day must be between 125 - 300; if even one day is outside these occupancy constraints, the submission will error and will not be scored.
Santa provides consolation gifts (of varying value) to families according to their assigned day relative to their preferences. These sum up per family, and the total represents the preference cost.

choice_0: no consolation gifts
choice_1: one $50 gift card to Santa's Gift Shop
choice_2: one $50 gift card, and 25% off Santa's Buffet (value $9) for each family member
choice_3: one $100 gift card, and 25% off Santa's Buffet (value $9) for each family member
choice_4: one $200 gift card, and 25% off Santa's Buffet (value $9) for each family member
choice_5: one $200 gift card, and 50% off Santa's Buffet (value $18) for each family member
choice_6: one $300 gift card, and 50% off Santa's Buffet (value $18) for each family member
choice_7: one $300 gift card, and free Santa's Buffet (value $36) for each family member
choice_8: one $400 gift card, and free Santa's Buffet (value $36) for each family member
choice_9: one $500 gift card, and free Santa's Buffet (value $36) for each family member, and 50% off North Pole Helicopter Ride tickets (value $199) for each family member
otherwise: one $500 gift card, and free Santa's Buffet (value $36) for each family member, and free North Pole Helicopter Ride tickets (value $398) for each family member
Santa's accountants have also developed an empirical equation for cost to Santa that arise from many different effects such as reduced shopping in the Gift Shop when it gets too crowded, extra cleaning costs, a very complicated North Pole tax code, etc. This cost in in addition to the consolation gifts Santa provides above, and is defined as:
accountingpenalty=∑d=1001(Nd−125)400Nd(12+|Nd−Nd+1|50)
a
c
c
o
u
n
t
i
n
g
p
e
n
a
l
t
y
=
∑
d
=
100
1
(
N
d
−
125
)
400
N
d
(
1
2
+
|
N
d
−
N
d
+
1
|
50
)

where Nd
N
d
 is the occupancy of the current day, and Nd+1
N
d
+
1
 is the occupancy of the previous day (since we're counting backwards from Christmas!). For the initial condition of d=100
d
=
100
, N101=N100
N
101
=
N
100
.

To be clear on the above summation, it starts on the date 100 days before Christmas and ends on Christmas Eve.

And finally:

score=preferencecost+accountingpenalty
s
c
o
r
e
=
p
r
e
f
e
r
e
n
c
e
c
o
s
t
+
a
c
c
o
u
n
t
i
n
g
p
e
n
a
l
t
y

This may seem complicated, but this nifty-difty starter notebook should get you started fast!