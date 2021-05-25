# SENG 474 Project

# Team Members
- Siddharth Pathak
- Gillian Bryson
- Nathan Denny
- Oliver Lewis
- Chao Ge

# Project Requirements
Since COVID-19 has spread out wildly through the world, each country has implemented
different government responses to defend against the virus. However the goal for each
government is the same, which is to reduce the number of COVID-19 cases and the ability for
the virus to spread through its population. Governments can be more efficient and place their
resources more precisely if they know which combination of responses have the greatest
chance to be effective in reducing spread. Therefore, our goal for this project has been to
create a machine learning program that can accurately predict if a set of government response
measures will lead to an increase or (preferably) a decrease of COVID-19 cases.
To achieve this goal, we collected our test and train data from Oxford University[1] and
Worldometers[2] who have been tracking COVID-19 since the beginning of it’s outbreak at
the beginning of 2020. Using this data, we ran several tests on different machine learning
models while tuning hyperparameters to determine which methods give the highest classification accuracy.

# Experiments
Outlined below are the experiments we conducted using the models to better gauge the results,
determine new ways of looking and analysing our data, and check consistency in the accuracy
levels.
## Experiment 1 - Different time periods as the target feature
After an initial review of the trends in the proportionality of active cases with government
measures we found that most of the measures result in an effect after an incubation period of 7
days, hence, we split the time periods to 1 week, 2 weeks, 3 weeks and 4 weeks after the
measure was placed into action.
## Experiment 2 - Adding an input feature for the number of new cases in the last week or two weeks
To measure accurate results in the success of the measure placed, we narrowed down our
cases dependency to active cases and new cases. In this experiment we’re adding “New
Cases” split over 2 time periods - 1 week & 2 weeks as a new input feature. We observed a
few countries with higher measures in place and observed their progress over 1 & 2 weeks by
monitoring their case numbers. Result in the numbers pointed towards the question - Should a
country reduce measures in place if it’s still experiencing an uprise in emerging cases?
## Experiment 3 - Removing country code as a input feature
Removing the country from the set of input features resulted in a generalized model that could
be applied to any country. Additional input features such as the one outlined in Experiment 2
were included in this experiment.
## Experiment 4 - Changing the Variables of each machine
Each machine has a set of variables that can be changed and adjusted to achieve better results.
The Decision Tree can use different splitting equations, the Random Forest can have the
number of trees fine tuned, and the Neural Network can have a multitude of parameters altered
(we chose to focus on the number of layers). We also tested what percentage of test/train split
would give us the best accuracy scores given that some methods like the Random Forest are
less susceptible to overfitting issues.

# Experimental Results

## Best data split percentage:
On all three machines on average the best accuracies were achieved at a .3 test/train split
which is a value supported by most literature and was generally expected.
## Best Tree Criterion:
The best on average performing split criterion for weeks was gini with an accuracy range of
[0.8375, 0.95]
## Best Neural Hidden Layers Count:
The best performing number of hidden Neural network layers was 20, having an accuracy
range of [0.78, 0.85]

The following graphs (Figure1, Figure2) show the accuracy scores of each method when
applied to each time interval, and when using the parameters that gave us the best accuracy
scores while testing:

Our accuracy results all came within the range of [0.7,0.95] which is very close to our goal of
75% accuracy. If we remove neural networks as one of our options we get an accuracy range
of [0.77,0.95] which is nicely within the goals we set for ourselves in the midterm report.

There are far too many figures that come from our testing to include in this document. To
view them please see our repo at
https://github.com/siddharthpk/SENG-474/tree/master/outputs

# References
- [1] COVID-19 Coronavirus Pandemic, Worldometer. [Online]. Available: https://www.worldometers.info/coronavirus/#countries
- [2] Corona Government Response Tracker, University of Oxford. [Online]. Available: https://www.bsg.ox.ac.uk/research/research-projects/coronavirus-government-response-tracker#data
- [3] Coronavirus, World Health Organization. Accessed: Aug. 06, 2020. [Online] https://www.who.int/health-topics/coronavirus/coronavirus#tab=tab_1
- [4] COVID-19 Projections Using Machine Learning, COVID-19 Projections. Accessed: Aug
05, 2020. [Online]. Available: https://covid19-projections.com/
- [5] MIT machine learning designed a COVID-19 vaccine that could cover a lot more people,
ZDNet. Accessed: Aug. 06, 2020. [Online]. Available:
https://www.zdnet.com/article/mits-machine-learning-designed-a-covid-19-vaccine-that-could
-cover-a-lot-more-people/3 

For more info on SARS-Cov-1 see https://www.who.int/ith/diseases/sars/en/
