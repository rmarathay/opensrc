# Lab 8


### Lab 8 R-Studio Code 
```library(arules)
library(arulesViz)

setwd("/Users/ranyeezus/Dropbox/2016JS1/opensrc/lab8")

getwd()

admissions <- read.table("binary.csv", header = TRUE, sep = "," )

col_names <- names(admissions)

admissions[,col_names] <- lapply(admissions[,col_names] , factor)

str(admissions)

rules <- apriori(admissions,  parameter = list(minlen=2, supp=0.01, conf=0.02),
                 appearance = list(rhs=c("admit=1"), 
                                   default="lhs"),
                 control = list(verbose=F))
rules.sorted <- sort(rules, by="lift")
inspect(rules.sorted)

plot(rules.sorted)
plot(rules, shading="order", control = list(main = "Two-key plot",
                                            col=rainbow(max(size(rules))-1L)))
plot(rules, method="matrix", measure=c("lift", "confidence"))
```


### Lab 8 R-Studio Visualizations


![visualization1](/images/lab8-images/v1.png)
![visualization2](/images/lab8-images/v2.png)
![visualization3](/images/lab8-images/v3.png)


## Project Update

I looked up how to build an iOS framework and looked at the PayKit iOS framework from Apple's Developer website. I created a Github Repo and a Slack Channel. I am going to make a blog post later this week.
