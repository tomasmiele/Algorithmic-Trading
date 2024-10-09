# Algorithmic-Trading

## Stock Analysis

## SMABackTest

The SMABacktester class is designed to backtest a simple moving average (SMA) trading strategy on stock market data using the yfinance library for fetching historical stock prices. Here's a summary of the class and its functionality:

### Class: SMABacktester

### Attributes:
symbol: The stock symbol (e.g., AAPL) for which the backtest will be run.
SMA_S: The window size for the short-term moving average.
SMA_L: The window size for the long-term moving average.
start: The start date for fetching stock data.
end: The end date for fetching stock data.
results: Holds the DataFrame with the backtest results once the test has been run.

### Methods:
#### __init__(self, symbol, SMA_S, SMA_L, start, end)

Initializes the backtester with stock symbol, short and long-term moving average window sizes, and the start and end dates for the analysis.
Automatically calls the get_data() method to fetch stock data.

#### get_data(self)

Downloads the stock data for the given symbol and date range using yfinance.
Computes daily log returns and the short (SMA_S) and long-term (SMA_L) simple moving averages.
Stores the data in the attribute self.data2 for further analysis.

#### test_results(self)

Runs the trading strategy by comparing the short-term and long-term moving averages:
A "long" position (1) is taken if the short-term moving average is greater than the long-term moving average.
A "short" position (-1) is taken if the short-term moving average is below the long-term moving average.
Computes the performance of the strategy and the buy-and-hold strategy.
Returns two values:
perf: The cumulative performance of the strategy.
outperf: The difference in performance between the strategy and buy-and-hold.
The results are stored in self.results.

#### plot_results(self)

Plots the cumulative returns of both the buy-and-hold strategy and the SMA-based strategy for visual comparison.
Requires the test to be run first (i.e., the results attribute must be populated).

### Summary of Usage:

Instantiate the SMABacktester class with the desired stock symbol and moving average windows.
Call test_results() to run the backtest and get the performance.
Use plot_results() to visualize the comparison between the SMA strategy and the buy-and-hold strategy.
This class is useful for testing how a moving average strategy would perform historically compared to a simple buy-and-hold investment.

## Alpha Vantage API

In this file, I tested using the Alpha Vantage API to retrieve daily historical data for Apple Inc. (AAPL) stock. The code integrates with the API using an access key, and the data is downloaded in the form of a pandas DataFrame, allowing for manipulation and analysis of stock prices, such as the closing price.

This test demonstrates how to use Alpha Vantage to fetch market information and prepare the data for visualization or other types of analysis.
