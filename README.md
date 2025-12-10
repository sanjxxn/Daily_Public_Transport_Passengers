# Public Transport Passenger Forecasting (ARIMA Time Series Model)

This project performs time-series analysis and forecasting on daily public transport passenger journeys across five service types:

- Local Route  
- Light Rail  
- Peak Service  
- Rapid Route  
- School Service  

The objective is to clean the dataset, analyze historical patterns, extract insights, and generate a 7-day forecast for each service category using ARIMA models.

---

# 1. Dataset Description

The dataset used is:

Daily_Public_Transport_Passenger_Journeys_by_Service_Type_20250603.csv

It contains daily passenger journey counts recorded across multiple public transport service categories over several years.

Although the dataset was provided for the assessment, it reflects real-world data typically published by:

- Government open-data portals  
- Public transport authorities  
- Public mobility analytics platforms  

These datasets support planning, forecasting, scheduling, and operational decision-making.

---

# 2. Why This Dataset Was Chosen

1. It contains continuous daily time-series data suitable for forecasting.  
2. Passenger journeys exhibit trend, seasonality, and noise, which are ideal conditions for ARIMA.  
3. Public transport data is operationally relevant and commonly used in forecasting projects.  
4. The dataset supports meaningful short-term forecasting tasks such as predicting demand for the next week.  
5. It allows demonstration of data cleaning, EDA, modeling, and visualization skills end-to-end.

---

# 3. Data Cleaning Steps

1. Convert the Date column into proper datetime format.  
2. Set Date as the index to enable time-series operations.  
3. Forward-fill and backward-fill missing values in service categories.  
4. Replace missing values in the "Other" column with zeros.  
5. Ensure the time-series index remains sorted and continuous.

These steps produced a clean and complete dataset suitable for exploratory analysis and forecasting.

---

# 4. Exploratory Data Analysis – Key Insights

**Insight 1 – Long-Term Trend**  
Passenger journeys show an overall upward trend with a noticeable drop around pandemic years and recovery in later years.

**Insight 2 – Weekly Seasonality**  
Passenger counts rise during weekdays and decline during weekends, indicating commuter-driven behavior.

**Insight 3 – Service Usage Variation**  
Light Rail and Rapid Route have the highest passenger counts on average. Peak Service and School Service have significantly lower but predictable volumes.

**Insight 4 – School Service Seasonality**  
School Service demand clearly aligns with academic calendars. Passenger counts remain near zero during holidays and increase during school months.

**Insight 5 – Annual Totals**  
Yearly totals reveal a dip around 2020 (pandemic period) followed by a strong recovery. This confirms the presence of trend and seasonality.

Plots associated with these insights are stored inside the plots folder.

---

# 5. Why ARIMA Was Selected

1. ARIMA is effective for short-term forecasting, especially for 7-day ahead predictions.  
2. It can model trend and noise components naturally.  
3. The dataset does not require complex external regressors, making ARIMA a suitable baseline model.  
4. ARIMA is interpretable and computationally efficient.  
5. It is widely used in real-world transport forecasting applications.

---

# 6. Modeling Approach

**Model Used:**  
ARIMA(2,1,2)

**Fallback Model:**  
ARIMA(1,1,1)  
(Used when the primary model fails to converge.)

**Forecast Horizon:**  
7 days

**Train/Test Split:**  
The last 7 days of data were reserved as a test set.  
The remaining historical data was used for training.

**Steps Performed:**  
1. Fit ARIMA model on training data.  
2. Predict values for the test period.  
3. Visualize train, test, and predicted values.  
4. Generate the next 7-day forecast.  
5. Save forecasts to individual CSV files.

---

# 7. Forecast Results

For each of the five service types, the script generates:

- Full historical time-series plot  
- Train/Test/Prediction comparison plot  
- 7-day forecast plot  
- A CSV file containing the next 7-day forecast  

Forecast files are stored in:

simple_arima_output/
 # 8. Conclusion

This project demonstrates the full workflow required for time-series forecasting:

- Data preprocessing and cleaning  
- Exploratory data analysis  
- Identifying trends and seasonality  
- Applying ARIMA for short-term forecasting  
- Generating visualizations and structured forecast outputs  

The outcome supports practical applications such as route planning, demand estimation, scheduling, and transport operations decision-making.
