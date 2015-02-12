# R-stats
fevd <- read.table("fev.dat.txt")
summary(fevd)

colnames <- c("age", "fev", "height", "sex", "smoke")

smoker <- filter(fevd, V5 == 1)
nsmoker <- filter(fevd, V5 == 0)

female <- filter(fevd, V4 == 0)
male <- filter(fevd, V4 == 1)

par(mar=c(3,3,1,1),mgp=c(1.75,.75,0))
mosaicplot(fevd, main = "FEV Data")
plot(fevd, main = "FEV Data")

## RUN AGAIN another time
plot(fevd[,1 ,2], main="FEV vs Age", xlab="FEV",ylab="Age")

## This sucks ass
hist(fevd[,1 ,2], breaks=16, xlab="Age", ylab="FEV", main="FEV vs Age")
hist(fevd[,1 ,2], breaks=20, xlab="FEV", ylab="Age", main="FEV vs Age")

## Female and Male mosaics
plot(female, main="Females")
plot(male, main="Males")

## Smoker and Non-Smoker mosaics
plot(smoker, main="Smokers")
plot(nsmoker, main="Non-Smokers")

summary(smoker)
summary(nsmoker)

## BLOWS
boxplot(smoker, main="Boxplot of Smokers Across Columns")
boxplot(nsmoker, main="Boxplot of Non-Smokers Across Columns")



## SUPER GREAT CODE   USE ARROWS!!!!
boxplot(age[smoke==1], age[smoke==0], main="Smokers Across Age Groups", xlab="Smoker   Non-Smoker")




## vom
boxplot(age[fev], main="FEV Across Age Groups")
hist(age, breaks=20, main="Age Distribution")
hist(fev[age == 15], breaks=20, main="Age & FEV Distribution")
hist(age[fev], breaks=20, main="FEV Across Ages")

par(mfrow=c(2,1))
hist(age[fev], breaks=20, main="FEV Across Ages")
boxplot(fev[age], horiz=FALSE, main="FEV Across Agez")

par(mfrow=c(1,1))
boxplot(fev[smoke], main="FEV of Smokers")
boxplot(fev[nsmoker], main="FEV of Smokers")

## Shivika is a boss
attach(fevd)
age <- V1
fev <- V2
height <- V3
sex <- V4
smoke <- V5
