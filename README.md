# Airline-Delays
Predicting airline delays in the US using Department of Transportation (DOT) public data. Classwork for Harvard CS109A
Code contains EDA, logit model and final conclusions of factors that strongly predict airline delays of domestic flights in the US.

#### KEY DESIGN DECISIONS AND METHODOLOGY
The main design decisions were cleaning up data of colinear predictors and  keeping predictors to a managable number and one that lets either customers or the airline industry take actionable decision was a key decision factor. The final number of predictors I worked with is 36. 

Classification model to predict Y/N delay of flight: Tried four different classification models to see which results in accuracy higher than 90% and AUC higher than 0.6 (the base case). I decided upon regularized logistic.

Linear regressesion for delay in time in min: For the linear regression to predict the delay in time - I chose a similar number of predictors but this time 'ARRIVAL DELAY' was my dependent variable, a continuous variable. R2 is quite low showing that the combination of these predictors don't do a great job in explaining the minutes of delay, and there are probably many other factors contributing.

What I could have done to improve my predictor selection is check the correlation of the residuals with each of my predictors and dependent variable to see if there is any omitted variable bias.

#### WHETHER A FLIGHT WILL BE DELAYED OR NOT
The top three predictors of whether a flight will be delayed or not are:

* Airline NK is 6.5 times more likely to be late. During the EDA we also saw about 38% of NK's flights are delayed.
* Being on Airline HA increases likelihood of being late by 2.4 times.
* Being on Airline UA increases likelihood of being late by 1.9 times. Other non-flight but important predictors are:
* Scheduled departure time: With every increase in hour (i.e. an hour later in the day) a flight is likely to the late 1.27 times. Thus flights later in the day are much more likely (upto 1.7 * 24 times) to be delayed.
* Month: Flights in June 2x more likely to be late than in January and this is supports our initial finding in the EDA that June had the highest number of delayed flights. After June, July and February are bad times to fly while Sept, Oct and Nov have the least delays. 

**Summary**: A customer should not fly on airlines NK and HA, try to fly as early in the day as possible and avoid flying in June if he/she cares about avoiding delays. From the airline industry perspective, they industry needs to understand why flights tend to get delayed later in the day, perhaps how airports can be better managed to avoid this. Both airport and airline personnel should prepare in advance for increased delays in June and plan to mitigate it.

#### HOW MUCH A FLIGHT WILL BE DELAYED ONCE IT IS DELAYED
This was a log-linear regression model, i.e. 1 unit increase in X1 is associated with a 100B1% change in Y. Top three factors which increase the time of delay:

* Being on airline NK increase the delay time by 18%
* Being on HA increases the delay time by 16%
* Being on airline B6 increase delay time by 9.5%.
* Non-airline reason that contributes to delay are: flying in the month of June increases airline delay by 11%.
