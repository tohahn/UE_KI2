# KI2 Übung 2 Tobias Hahn 307337 5
1. Cookie Paradox

	It is not given how the guard chooses the cookie to be eaten. We assume that the guard picks one out randomly from the pool of available cookies at the time he chooses. As B was given the spare message, and was therefore removed from the pool of available cookies, the guard chooses randomly between two cookies, A and C. Therefore the propability of each cookie to be eaten is 1.2, or 0.5.

2. Three stoves

	The probabilities for failing on a stove are F(1)=0.05, F(2)=0.04, F(3)=0.02 respectively. The propabilites for cooking at each stove are C(1)=0.25, C(2)=0.35 and C(3)=0.4. Now, we need to find the propabilites for the stove given failure, or P(C(1)|f), P(C(2)|f), P(C(3)|f) respectively. In general, we can say that accoridng to Bayes P(C(x)|f) = P(f|C(x)) * C(x) / P(f). We have almost all the information to use this formule, since we know how probable failure is at any given stove, and also how propable it is that a given stove is used. However, we don't know how probable failure is in general, but luckily we can compute that: P(f) = SUM(P(f|C(x)) * C(x)) for all stoves. This gives us: 0.05 * 0.25 + 0.04 * 0.35 + 0.02 * 0.4 = 0.0345. Now we can just insert into Bayes and get: 
	1. P(C(1)|f) = 0.05 * 0.25 / 0.0345 =~ 0.36
	2. P(C(2)|f) = 0.04 * 0.35 / 0.0345 =~ 0.41
	3. P(C(3)|f) = 0.02 * 0.4 / 0.0345 =~ 0.23

3. Rational beliefs

	Let's look at the probability table for this incident.
	. | B | not(B)
	--- | --- | ---
	**A** | a | b
	**not(A)** | c | d

	Our propabilites can be expressed as sums of these unknowns as follows:

	P(A) = a + b = 0.4
	P(B) = a + c = 0.3
	P(A or B) = a + b + c = 0.5

	From this we can gather that c is 0.1 (P(A or B) - P(A)), if we know c we can calculate a as 0.2 (P(B) - c) and then we can get b as 0.2 (P(A) - a). Now, in order for the table to be rational, all the unknowns must add up to 1. So 1 = a + b + c + d must hold. If we substitute the values we already know, we get d = 0.5. The propability for P(A and B) is just a, so in this case we would assume it to be 0.2.

	If we change P(A or B) to be 0.8, we get different values for our calculations. Let's do them again. Now, c would be 0.4. Therefore a would be -0.1, or a negative propability - this is not rational. Another way to say this would be that the propability for any of two events happening cannot be greater than the sum of either of these events happening alone.

	According to Bayes, the propability for P(B|A) = P(A|B) * P(B) / P(A). Now, if P(B|A) > P(B), P(A|B) / P(A) has to be greater than 1. Now the propability for A is: P(A) = P(A|B) + P(A|not(B)). Since we know that P(A|B) > P(A) (otherwise P(A|B)/P(A) would be smaller than 1) we know that P(A) - P(A|B) < 0. So P(A|not(B)) is also smaller than zero, and therefore smaller than P(A). 

4. Poker

	The number of possible hands can be calculated with the binomial coefficient, 52 over 5 (there are 52 distinct cards and we draw five) which is 2598960.

	Each atomic event has a propability of 1 / (52 over 5), or 1 / 2598960. This is 3.89 * 10^-7.

	Since there are only four royal flushes in the deck, the frequency of it occuring in the deck is 4. Therefore we can just multiply the porpability for one atomic event by four, and we get the propability of 0.00000155705 or 1.557 * 10^-6.

	For the four of a kind, we have to draw the same card rank four times, in all of the four suits. The frequency of this occuring is (13 over 1) * (4 over 4). The last card can be in one of the remaining ranks and in every suit, the frequency of this is (12 over 1) * (4 over 1). So the frequency of this deck is (13 over 1) * (4 over 4) * (12 over 1) * (4 over 1) = 624. Now we need to divide this frequency by the domain of the game, all possible hands, and we get our Propability: 624 / 2598960 = 0.00024289985 or 2.43 * 10^-4.
