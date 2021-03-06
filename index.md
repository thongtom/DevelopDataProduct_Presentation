---
title       : Develop Data Product - AQI
subtitle    : Air Quality Index for LDG. ULU REMIS area from date 1 Aug 2013 to 5 Feb 2015
author      : Thong
job         : Engineer
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

This Reproducible Pitch Presentation is the second part of the Course Project for the **Developing Data Products** module and it must satisfy the following:

1. It must be done in Slidify or Rstudio Presenter
2. It must be 5 pages
3. It must be hosted on Github or Rpubs
4. It must contained some embedded R code that gets run when slidifying the document

The source code for this Slidify slide is available at:

<https://github.com/thongtom/DevelopDataProduct_Presentation>

--- .class #id 

## The Shiny Application

The Shiny application for the Course Project is avalilable at:

<https://thongtom.shinyapps.io/DevelopDataProduct-AQI>


This Shiny application is to analyst the Air Quality Index (AQI) for LDG. ULU REMIS area from date 1 Aug 2013 to 5 Feb 2015.

Source code for ui.R and server.R files are available on the GitHub:

<https://github.com/thongtom/DevelopDataProduct>

You can find out the details of this Shiny application by reading the "Info" section in navigation tab of this [application.] (https://thongtom.shinyapps.io/DevelopDataProduct-AQI)

---

## The AQI Dataset


```r
data <-read.csv("aqi.csv",skip=1)
head(data)
```

```
##         Date Hour AQI
## 1 2013-08-01    1  66
## 2 2013-08-01    2  67
## 3 2013-08-01    3  67
## 4 2013-08-01    4  67
## 5 2013-08-01    5  67
## 6 2013-08-01    6  67
```

---

## Sample Plot Chart (Year 2014)


```r
library(ggplot2);library(lubridate);
dataSel <- data[(year(data$Date)==2014 & (month(data$Date)>=1 & month(data$Date)<=12)), ]
p <- ggplot(data=dataSel, aes(x=dataSel$Hour, y=dataSel$AQI, height=100, width=100)) 
p +geom_point(color="green")+labs(x="Hour", y="AQI")
```

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 

