# Callable Inverse Swap

A Callable Inverse Floating Rate Swap is a forward swap agreement with an option of canceling the swap each year starting from several years in future. The deal is priced with a two factor Black-Karasinski model.

The Black-Karasinski class of models assumes the short term interest rates to be log-normally distributed. The spreadsheet mode used for the deal pricing has a hard-coded term structure of the mean reversion and volatility parameters, constructed as Chebyshev polynomials. 

The calibration procedure takes only an interest rate curve as input (ignoring volatility surfaces) and results in adjusting the “alpha” parameter of the model. To test the calculations over a range of parameters, we used  the “piece-wise constant parametrization” mode. 

The Black-Karasinski model is set with zero mean reversion. The zero mean reversion makes it easy to perform simulations on a recombining binomial tree.

To provide the ability to control interest rates for our testing, the interest rate curve was constructed as a flat yield curve at a prescribed yield level. One set of the tests used the interest rate term structure as generated.

A few tests of internal consistency of the model raise some concerns. The results of symmetry tests cannot be accounted for by numerical truncation errors. 

Fortunately, these discrepancies are not important for the deal under consideration. The reason is that the price dynamics that affect the deal is driven by essentially one factor process.  The history of tests of one factor driven processes supports the validity of pricing. 
However, extra caution is needed when the model is used for pricing deals that are driven by essentially two factor random processes. Eventually, the indicated inconsistencies in the model need to be eliminated. 


References:

https://finpricing.com/curveVolList.html
