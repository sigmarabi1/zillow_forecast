## Forecasting average median housing value using using Zillow dataset and Facebook Prophet Python library

### Objectives:

    1-	Develop time series plots for the following Arkansas metro areas: Hot Springs, Little Rock, Fayetteville, Searcy. 
    
    2-	Develop model(s) for forecasting average median housing value by zip code for 2018.
 
    3-	Predict which three zip codes provide the best investment opportunity. 


### Data Analysis:

A model using Facebook Prophet python library is developed to predict the average home value for the area of Fayetteville in order to determine if this metro area presents a decent opportunity for investment.

Prophet is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects. It works best with time series that have strong seasonal effects and several seasons of historical data. Prophet is robust to missing data and shifts in the trend, and typically handles outliers well. 

The model was trained using timeseries data from January, 1997 until December of 2017. Following model training, a prediction is made for all months in 2018. 

### Down Sampling for General model:

Searching for the states with highest growth over a 3-year period (2014-2017), should help us reduce our target sample of zip codes to build and train our Prophet time series models. The objective is to forecast 2018 values using a reduced sample. 

The following procedure is followed:

      1- Obtain the values for December month.
    
      2- Calculate % Growth for 3-Year period = (Dec2017/Dec2014 – 1).
    
      3- Sort by % growth and get the top states (keep states with at least 25% growth).
    
 ### Criteria for finding best opportunities:
    
     - A dataframe is created with zip codes with low MAE and double-digit growth. This should help us find low-risk, decent          reward opportunities. 
  
     - Create another dataframe with high forecasted growth and MAE < 20k. This should reveal high-reward, high-risk                  opportunities. 
 
 ### Findings:
 
The Zillow dataset with average home prices by zip code in the US, turns out to be a very useful dataset to predict future home prices. By finding the states with the highest growth in a 3-year period—from 2014 through December of 2017—a reduced dataset was used to forecast home prices in 2018 for each individual zip code in Washington, Oregon, Nevada, Florida, Colorado, Utah, California, and Indiana. By running Prophet forecast models in parallel—minimizing runtime for all 3k zip codes—a dataset containing zip codes with low-risk (low MAE) and at least 10% return on investment was generated. From this dataset, we can recommend the following zip codes which happen to be in the state of Florida:

    -33919 in Fort-Myers, FL
    -34987 in Port Saint Lucie, FL
    -33063 in Margate (Miami-Fort Lauderdale market), FL

Margate and Port Saint Lucie are within one hour of each other in the south east of Florida, and Fort-Myers is in the south west corner of the state. The average home value in these zip codes is between $263k and $265k which offers an attractive entry point to market in 2018. A projected 10% increase in price represents a good opportunity for investment. Should the value growth remain steady for these 3 zip codes, a potential 30% return in investment over a 3-year period is fantastic. The fact that these zip codes are in relatively close proximity to each other, might help investors keep the cost of maintenance under control. On the negative side, Florida is always at risk of hurricanes, therefore high insurance premiums might work against the bottom line. Higher reward zip codes are found in California, however, the risk of investing in such zip codes is higher given the accuracy of our models. 
   
