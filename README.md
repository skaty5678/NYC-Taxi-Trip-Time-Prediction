# NYC-Taxi-Trip-Time-Prediction

### Technological advancement has provided different ways to commute from one place to another. These include buses, metros and especially cab services. New York city is one of the highly advanced and developed cities of the US with an intricate web of cab services. NYC has both and yellow cabs which mount to approximately 13,000 in number. 

### Here we are considering various machine learning models that provide reliable and improved accuracy for prediction based use cases, Linear regression, Random forest and XGBoost. Successful prediction of the trip duration would eventually be much useful in the future to make better taxi trip duration predictions applicable to multiple cities.

## Data Description
The dataset is based on the 2016 NYC Yellow Cab trip record data made available in Big Query on Google Cloud Platform. The data was originally published by the NYC Taxi and Limousine Commission (TLC). The data was sampled and cleaned for the purposes of this project. Based on individual trip attributes, you should predict the duration of each trip in the test set.
NYC Taxi Data.csv - the training set (contains 1458644 trip records)

## Data fields
id - a unique identifier for each trip

vendor_id - a code indicating the provider associated with the trip record

pickup_datetime - date and time when the meter was engaged

dropoff_datetime - date and time when the meter was disengaged

passenger_count - the number of passengers in the vehicle (driver entered value)

pickup_longitude - the longitude where the meter was engaged

pickup_latitude - the latitude where the meter was engaged

dropoff_longitude - the longitude where the meter was disengaged

dropoff_latitude - the latitude where the meter was disengaged

store_and_fwd_flag - This flag indicates whether the trip record was held in vehicle memory before sending to the vendor because the vehicle did not have a 
connection to the server - Y=store and forward; N=not a store and forward trip

trip_duration - duration of the trip in seconds

#

Started with the exploratory data analysis of dependent and independent variables. Then  searched for correlation between the variables to scrutinize. Proceeding further applied  feature engineering and dimensionality reduction to extract valuable statistics like distance and  speed from the geo coordinates and pickup hour, day, weekday and month from pickup and drop off datetime. Used haversine to extract distance from latitudes and longitudes of  the given trip.  


There were some important facts from the EDA like people generally like to travel alone. Most  number of pickups were done on Friday. Throughout the day between 5 PM to 9 PM the taxi  service had been availed the most number of times. 


Pickups done between 2 PM to 6 PM has seen the longer trips. Taxis were booked for longer trips  generally on Thursdays and Fridays. A static increase in trip duration from February onwards maybe because of the reason that from then the weather became less cold and more suitable for travelling by taxi. 


Majority of the trips were with distance less than 25 kms and time less than 3 to 4 hours which  indicates that people generally preferred to take cabs for not so long journeys. 


## We ran 3 models on the given dataset:
1. Linear Regression.
2. Random Forest.
3. XGBoost.


Linear regression didn’t perform well because there was no linear relationship between the  target variable and some of the independent variables. Next, tried random forest regressor  with some hyperparameter tuning and RMSE value was 0.32 and R2 score being 80%. And  finally, tried the XGBoost regressor which gave even better results than both the previous  ones with some hyperparameter tuning. 


Also plotted the feature importance for both the tree-based algorithms and distance played a  major role in both the models with more than 65% significance for the prediction. 


So, finally proceeded with the XGBoost model and were able to predict for 83% of the data with RMSE  of 0.29.

