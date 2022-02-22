# Smart-Beta-Portfolio-Optimization

## Smart Beta Portfolio 

### Index Weight 
We will use the the volumne traded on a particular date to assign weight to each stock, largely traded stock will have a relative larger weight compare 
to those that are lightly traded. 

### Portfolio Weight 
Now that we have the index weights, let's choose the portfolio weights based on dividend. You would normally calculate the weights based on 
trailing dividend yield, but we'll simplify this by just calculating the total dividend yield over time.

### Returns 
Generate returns data for all the stocks and dates from price data. You might notice we're implementing returns and not log returns. 
Since we're not dealing with volatility, we don't have to use log returns.

### Weighted Returns 
With the returns of each stock computed, we can use it to compute the returns for an index or ETF.

### Cumulative Returns 
To compare performance between the ETF and Index, we're going to calculate the tracking error. 
Before we do that, we first need to calculate the index and ETF comulative returns. 

### Tracking Error
In order to check the performance of the smart beta portfolio, we can calculate the annualized tracking error against the index. 


## Portfolio Optimization 

### Covariance
We need to calculate the covariance of the return. 

### portfolio variance
We can rewrite the portfolio variance into its quadratic form.

### Distance from index weights
We want portfolio weights that track the index closely.  So we want to minimize the distance between them.
Recall from the Pythagorean theorem that you can get the distance between two points in an x,y plane by adding 
the square of the x and y distances and taking the square root.  Extending this to any number of dimensions is called the L2 norm.

### objective function
We want to minimize both the portfolio variance and the distance of the portfolio weights from the index weights. 

### constraints
We can also define our constraints in a list.  For example, you'd want the weights to sum to one.

### optimization
So now that we have our objective function and constraints, we can solve for the values of X.

### Optimized Portfolio 
Let's generate the optimal ETF weights without rebalanceing. We can do this by feeding in the covariance of the entire history of data. 
We also need to feed in a set of index weights. We'll go with the average weights of the index over time.

### Rebalance Portfolio Over Time 
The single optimized ETF portfolio used the same weights for the entire history. This might not be the optimal weights for the entire period. 
Let's rebalance the portfolio over the same period instead of using the same weights.

### Portfolio Turnover 
With the portfolio rebalanced, we need to use a metric to measure the cost of rebalancing the portfolio. 
