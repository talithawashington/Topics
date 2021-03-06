Twitter Data
========================================================
author: Albert Y. Kim
date: Friday 2016/04/22





Mining Twitter Data
========================================================
[Beer vs church map](http://www.floatingsheep.org/2012/07/church-or-beer-americans-on-twitter.html)

What is the **most** important thing to keep in mind when observing such maps?





Mining Twitter Data
========================================================

**Strong** selection biases at every step:

* Who signs up to Twitter
* Who tweets at all
* Who tweets about these topics
* Who lets their location be revealed

i.e. the sample is non-random, so it is not representative of the population as
a whole, and hence the results of the sample are not generalizable to the
entire US population.

But there is still useful info nonetheless.





API
========================================================

Wikipedia: In computer programming, an **application programming interface**
(API) is a set of routines, protocols, and tools for building software and
applications.

So for example, if you want to build an App that uses Google Maps, Twitter, FB,
Instagram etc. data, you access their data via an API.





API Keys
========================================================

Wikipedia: An API key is a code passed in by computer programs calling an API to
identify the calling program, its developer, or its user to the Web site.

API keys are used to track and control how the API is being used, for example to
prevent malicious use or abuse of the API.





Obtaining a Twitter API Key
========================================================

We are getting digital permission to open the Twitter pipeline for our use, just
like any other developer would.






Steps
========================================================

* Install `twitteR` package from RStudio (homepage is
[here](https://github.com/geoffjentry/twitteR))
* Create a Twitter account if you don't already have one.
* Create a Twitter application at the [Twitter Application Management
page](https://apps.twitter.com/). You will need to give an original name.
* Click the "Keys and Access Tokens" tab
    + Note your "API key", "API secret"
    + Click on "Create Token" and note your "Access Token", and "Access Token
    Secret".





Crucial
========================================================

Do not share these values with anyone nor save them in a publicly viewable file.





Authenticating your Twitter API Key in R
========================================================

* Replace the four values below with the values in your "Keys and Access Tokens"
page. No spaces or line breaks.
* You will be prompted: "Use a local file to cache OAuth access credentials
between R sessions?" Say yes.


```r
library(twitteR)
setup_twitter_oauth(
  "API key", 
  "API secret", 
  "Access token", 
  "Access token secret"
)
```





Testing
========================================================


```r
some_tweets <- searchTwitter("prince", n=100, lang="en")
```

