# fina-mom
# Momentum Trading Strategy, based on hostorical returns of Miscrisoft


# Data
In order to prepare the data for our analysis, we imported pandas, numpy, matplotlib and statsmodel. Then, we import the CRSP file which holds stock data and the FF file to get the three factor model data and the risk free rate. Further, we set the data in an exploitable format and calculate the past 12 month rolling returns for each month. Next, we form portfolios for every month, a portfolio consisting of different stocks and divide those into 10 groups. We shift two months backward to be certain that we use previous returns to predict future returns. We then merge the previous data and the portfolios, this is the final step in our data set creation.
We then discover some statistics for the portfolios we just created. We calculate characteristics such as mean and standard deviation for the top and bottom portfolios. Using the function ‘describe’ we calculate the characteristics of all the portfolios for all months. For further analysis, we plot and calculate the mean and standard deviation of the 10 portfolios we created.
We use the difference between top portfolio return and bottom portfolio return as strategy return. Then we take risk free rate away from it, we can get strategy excess. In order to make calculation convenient, we convert all returns into log returns, which shows as portofolio2 in codes(Graph 1). Here we also plot strategy return and market return. Besides, the standard deviation of the strategy return and market return are 8.40 and 5.34 individually. While the 12-month rolling excess return is 0.47.

Graph 1: portfolios2
 
  investing is a
which capitalizes on the continuance of an existing market trend.
 It involves going long on securities that show upward-trending prices and short the respective assets with downward-trending prices. In this report, we observe the results of the momentum strategy used on historical stock prices. We used CAPM, Factor model, Shapiro-Wilk Test and the visualisation of historical drawdown to find conclusive results that the strategy return is always larger than the risk
 free return.
 
# Results
Graph 2: Mean Return of 10 Portfolios
We have divided the stocks in 10 portfolios according to the momentum strategy. This graph shows the mean return of these portfolios. Except for the bottom portfolio, we observe an upward trend, where the top portfolio has the highest mean return.
Graph 3: Standard Deviation of 10 Portfolios
This graph shows the standard deviation of all the portfolios, we notice that the top and bottom portfolios have high standard deviations whereas portfolios with stocks that haven’t moved have a lower deviation.
   
Graph 4: Historical drawdown
The Graph 4 shows historical drawdown of the strategy return, we use the cumsum function to get this chart. We visualize history drawdown of our momentum strategy and we can see from the graph that our momentum strategy has very low drawdown risk after 1959.
Graph 5: Strategy Returns
As the Graph 5 shows, the strategy return fluctuated during the 90-years period. There are several significant increases that occurred at around 1934, 1941 and 2001.
  
Graph 6: Sharpe ratio of strategy return
Graph 7: Sharpe Ratio of market return
Sharp ratio could be calculated via the following formula:
Sharpe Ratio=σp/(Rp−Rf)
The Sharpe ratio of the strategy return is plotted in Graph 6. The Sharpe ratio for the momentum strategy is 0.47 while that of the market return is 0.82. The Sharpe ratio is the risk adjusted return of a portfolio, in this scenario to our surprise we see that the Sharpe ratio of the momentum strategy is less than that of the market.
   
Graph 8: 95% VAR - Momentum Strategy
Graph 9: 95% VAR - Market return
The graph shows 95% VAR of our momentum strategy is -12.18%, which means we have 95% confidence that this strategy will not lose more than 12.18%, whereas the graph for the market return shows that there is 95% confidence that it won't lose more than 7.50%
  
Graph 10: Regression Results
Fama and French Three-Factor Model is an extension model of Capital Asset Pricing Model. Here we try to create a regression model based on its formula
Rit−Rft=αit+β1(RMt−Rft)+β2SMBt+β3HMLt+ε
We use sm.ols function to create regression. From the regression results (Graph 10) we can find each independent variable has a p-value smaller than 0.001, so these independent variables show statistically significant relationship with the dependent variable. R square is equal to 0.237, which means around 23.7% stocks can be explained by this model. Then we do a Shapiro-Wilk test for normality test. Due to a p-value that is smaller than 0.05, null hypothesis of normality is rejected. Therefore, we can conclude that the strategy returns are not normally distributed.
# Conclusion
From the above analysis we observe that the standard deviation of the momentum strategy is 8.40% and on the market portfolio it’s 5.34%, hence, the momentum strategy holds higher risks. Besides, the mean sharp ratio of the market is calculated as 0.47, which is smaller than the sharp ratio of the momentum strategy which is 0.82. We can also find that the selected strategy has 95% confidence that it will not lose more than 12.18%, while this figure of market return is 7.50%, which means this strategy is riskier. Thus, to some extent, we conclude that the momentum strategy is not a rational strategy.
