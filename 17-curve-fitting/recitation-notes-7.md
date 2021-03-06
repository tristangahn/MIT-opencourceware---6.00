Distributions, Monte Carlo, and Regressions
===========================================

### Distributions

So far we have learned these distributions:

1. Normal/Gaussian - it looks like a bell curve, the peak is at the mean and it falls off symetrically. It can be fully specified by the standard deviation and the mean. - `(1/root(2Pi*standard_deviation**2) * e)**(-(x-Mean)**2/2standard_deviation**2)`. Standard deviations are also called `sigma`.
2. Uniform - it looks like a horizontal like - `1/b-a`
3. Exponential - it looks like a downward trend

### Monte Carlo method

What a Monte Carlo method is? It is trying to arrive at a solution by large amounts of random sampling.

#### Monty hall problem

Monty hall problem - always switch and by switching you will have a 2/3 chance of winning.

```Python
import random

def choose_door():
    return random.choice([1, 2, 3])
    
def play_monty_hall(num_trials = 1000):
    stay_wins = 0
    switch_wins = 0
    for trial in range(num_trials):
        prize_door = choose_door()
        player_door = choose_door()
        if prize_door == player_door:
            stay_wins += 1
        elif prize_door != player_door:
            switch_wins += 1
            
    print 'Stay wins: ', stay_wins / float(num_trials)
    print 'Switch wins: ', switch_wins / float(num_trials)
```

![monty hall 1](http://dl.dropbox.com/u/31042440/mit-ocw-600/unit-2/Monty_closed_doors.svg)

![monty hall 2](http://dl.dropbox.com/u/31042440/mit-ocw-600/unit-2/Monty_open_door_chances.svg)

#### Pi

The random dots thrown in a square that has a circle inside it. This is one of the ways of approximating Pi.

#### Integration

Using the same method, we can do **numeric integration**.

`f(x) = x**2` - integrated `f(x) = x**3/3`. This is an easy function to integrate, but there are function that are much easier to integrate using the Monte Carlo method.

1. Find the x-max and x-min values within a certain range
2. Generate random points within the selected rectangle
3. Find the integrated area by taking the relative area of the dots not inside the original function

Confidence intervals and confidence levels.

#### Monopoly analysis

A site to go to [Project Euler](http://projecteuler.net/).

What are the top 3 places you land on Monopoly?

### Regressions

When having a bunch of samples taken you need to calculate the amount of error present. To do that we use regression and plot fitting. Having that function also allows to get aditional data points that we couldn't get while experimenting.

Residual error. The regression is done by `numpy.polyfit()`.
