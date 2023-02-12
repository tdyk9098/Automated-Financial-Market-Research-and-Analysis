# 1M-USDPLN-Forecasting-Application

# ABSTRACT

This project extracts historical data from various financial instruments and economic indicators to develop a time series forecasting model for the currency cross USD/PLN. The code extracts the following instrument’s monthly historical data from Investing.com:
-	AUD/USD
-	EUR/USD
-	GBP/USD
-	USD/JPY
-	USD/CHF
-	USD/CAD
-	AUD/PLN
-	EUR/PLN
-	GBP/PLN
-	PLN/JPY
-	CHF/PLN
-	CAD/PLN 

A Currency Basket Index is then developed by standardizing the base currency and giving an equal weight to the returns of each currency.

The code also utilizes the FRED API and extracts the following monthly economic releases:
-	Poland 3M Bond Yield
-	USA 3M Bond Yield
-	Poland Import Value in Zloty, non-adjusted
-	Poland Export Value in Zloty, non-adjusted
-	Poland Net Value in Zloty, non-adjusted
-	USA Import Value in USD, non-adjusted
-	USA Export Value in USD, non-adjusted
-	USA Net Value in USD, non-adjusted

This application was designed to be run at the end of each month and concludes with a deep learning model predicting the close price of the following month.

Feature engineering and differencing of non-static variables were used to forecast a multivariate time series using a LSTM Deep Learning Model.

There was a total of 4 inputs with a window of 5 months. Future iterations of this project could explore utilizing various economic and currency basket features.

# TABLE OF CONTENTS

- Application – USDPLN 1M Forecast: Data preprocessing and multivariate and univariate time series forecasting.

# MODEL EVALUATIONS
MSE: .02
RMSE: .14
RRMSE: .04
MAE .10
RMAE: .03
EV: .81


While the EV of the model is quite high and the Relative RMSE and MAE are quite low, in the domain of currency trading, the margin of error is too high for a predictive valuation model. In FX trading, the lowest change in price can be .00001 and retail trades are commonly conducted using targets in pips (.0001). This means that a RMSE or MAE greater than .1000 would mean a risk of 1000 pips, far too large of a risk margin for any reasonable position sizing.

However, using the extreme upper and lower bound as a mean reverting trading signal may be a derivative application for this code. Note: the USD/PLN monthly close has an Augmented Dickey Fuller test p value of .20, the close data itself is not mean reverting. 
