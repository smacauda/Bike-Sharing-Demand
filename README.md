# Bike-Sharing-Demand

Bike sharing systems are a means of renting bicycles where the process of obtaining membership, rental, and bike return is automated via a network of kiosk locations throughout a city. Using these systems, people are able rent a bike from a one location and return it to a different place on an as-needed basis. Currently, there are over 500 bike-sharing programs around the world.

The data generated by these systems makes them attractive for researchers because the duration of travel, departure location, arrival location, and time elapsed is explicitly recorded. Bike sharing systems therefore function as a sensor network, which can be used for studying mobility in a city. This analysis uses data from the Capital Bikeshare program in Washington, D.C. to combine historical usage patterns with weather data in order to forecast bike rental demand.

## Introduction

The dataset consists of the following fields: 


- **datetime:** hourly date + timestamp
- **season:** **1** = spring, **2** = summer, **3** = fall, **4** = winter
- **holiday:** whether the day is considered a holiday
- **workingday:** whether the day is neither a weekend nor holiday
- **weather:**
	- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
	- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
	- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
	- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
- **temp:** temperature in Celsius
- **atemp:** "feels like" temperature in Celsius
- **humidity:** relative humidity
- **windspeed:** wind speed
- **casual:** number of non-registered user rentals initiated
- **registered:** number of registered user rentals initiated
- **count:** number of total rentals (Dependent Variable)

## Visualization

Several visualizations were created to better understand the data. 

### Correlation Matrix

A correlation matrix was created with a heatmap to understand the correlation betweeen demand and the other variables. 

![alt text](https://github.com/smacauda/Bike-Sharing-Demand/blob/main/images/corr-matrix.png)



## Results

This analysis considers 5 models: random forest, lasso, support vector, k-neighbors, and decision tree regressors. The root mean squared error (RMSE), R^2, and mean absolute error (MAE) are below. 

| Model | RMSE | R-squared | MAE |
| :---         |     :---:      |     :---:      |          ---: |
| RandomForestRegressor   | 0.325084   | 0.946889    |0.220068|
| Lasso	 | 1.021079  | 0.476024	  |0.807870  |
| DecisionTreeRegressor | 0.455941  | 0.895525  | 0.303313  |
| SVR | 1.299214 | 0.151690  | 0.958028 |
| KNeighborsRegressor | 0.861715  | 0.626818  | 0.625658  |
