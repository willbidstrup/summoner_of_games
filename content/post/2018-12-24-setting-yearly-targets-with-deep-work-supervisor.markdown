---
title: Setting yearly targets with Deep Work Supervisor
author: Will Bidstrup
date: '2018-12-24'
slug: setting-yearly-targets-with-deep-work-supervisor
categories:
  - R
tags:
  - R
---


The Deep Work Supervisor tells you how much deep work you have been doing.  

Today I'm going to play around with setting targets. 

A big TODO is to check out [packrat](https://rstudio.github.io/packrat/).  



```r
library(here)
```

```
## here() starts at /Users/williambidstrup/Documents/GitHub/dse_live
```

```r
library(tidyverse)
```

```
## ── Attaching packages ───────────────────────────────────────────────────────────────────────────────────────────────── tidyverse 1.2.1 ──
```

```
## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
## ✔ readr   1.1.1     ✔ forcats 0.3.0
```

```
## ── Conflicts ──────────────────────────────────────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
```

```r
library(padr)
```


Here is the year of 2019.  

First I will create the year with padr. 


```r
dates <- as.Date(c("2019-01-01", "2019-01-02", "2019-12-30", "2019-12-31")) 
dates <- as.data.frame(dates)
dates  <- dates %>%
  pad()
```

```
## pad applied on the interval: day
```



# Setting target number of intervals

I like to do my deep work intervals at 25 minutes.  I need to choose if I will set and manage targets based on number of intervals or time elapsed.  Number of intervals probably makes the most sense, from there I can always convert to hours if needed.  

# Treating workdays differently to weekends and vacation
