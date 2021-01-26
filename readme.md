# King County Home Buyers Budget Guide
**Author**: Wolfgang Wallach

## Outline
* [Overview](#Overview)
* [Business Project](#Business-Project)
* [Data](#Data)
* [Modeling](#Modeling)
* [Conclusions](#Conclusions)
* [More Information](#More-Information)
* [Repository Structure](#Repository-Structure)

## Overview
At the request of Keller Williams Greater Seattle Realty Group, I have conducted research into the King County real estate market. Using Data from [King County house sales](https://www.kaggle.com/harlfoxem/housesalesprediction) between May 2014 and May 2015, I have constructed a linear regression model that will serve as the basis for a zillow-like portal for home buyers in the area.

## Business Project
I have been tapped by the Greater Seattle division of Keller Williams (KW) to begin construction of a new web portal that will allow prospective home buyers to better understand what is within their price range, as well as which features they may be looking for that can drive the price of a home greater than potential other features, like square footage of the home or how many bathrooms it has. KW is hoping that the creation of this portal will allow their realtors to take on more clients at one time without becoming overwhelmed, as well as draw potential home buyers to KW and away from other realtors in the greater Seattle area. With this in mind, I will create a regression model that can answer the following questions for KW:
* What features are most likely to drive the price of a home?
* What features are least likely to drive the price of a home?
* If the model is an accurate prediction of home prices in the greater Seattle area, what else could be added to the model in the future to make a better user experience?

## Data
The data used for this project was held in a single .csv. There were eighteen possible predictors, and for the model I am constructing, I will be using the following :
* Square footage of the home
* The condition of the home
* How many bedrooms the home has
* How many bathrooms the home has
* How many floors the home has
* The grade of the home, based on the King County grading system
* The year the house was built
* The location of the house, based on [Geohash](https://en.wikipedia.org/wiki/Geohash) coordinates created from the latitude and longitude
Other than selecting the above features from all those available through inspection or discovery of multicollinearity, I will drop extreme values from all of the features, as well as removing entries in the house sales that may contain missing data. Once the data is all clean and usable, I will transform my continuous data as well as dummify and bin my categorical data so that my model does not reach an obscene number of features.

## Modeling
Having cleaned and preprocessed the data, I'll then begin the modeling process. Without dropping or editing any features, I'll create an OLS model of the continuous data to inspect it for linearity assumptions, then transform said data accordingly. Having set that data correctly, I'll reintegrate it with the dummified data and create another OLS model to inspect each feature as it relates to the output of the model, the sale price of the house. Having done that I'll test for the highest r-squared value to see if I need to drop any of the features to make the model a better predictor of price. Once that is done, I'll create the model using the features that grant the highest r-squared, and run a linear regression to test for the MSE between the test data and the training data using cross validation.

## Conclusions
Having created a model that can somewhat reliably predict the sale price of a house in the greater Seattle area, I can see from the data that most of the features actually don't have a noticeable affect the house price all that much. Some of the geohash values are significant, while others are not. The condition of the house is significant as well. The features that people may thing of most when looking into a house, being how many bedrooms there are, or how many bathrooms there are, are less significant as far as determining the sale price of the house goes.

Going forward, I would like to try to identify other features that may affect price, specifically on location based on nearby features. For instance, waterfront properties or properties that are closer to mountains, rather than properties that are within a rectangular bucket, such as the geohash coordinates that I used in the model for this project. This project is also just the first step in creating the portal for KW.

## More Information
Please review my full analysis in my Jupyter Notebooks above or in my [non technical presentation](https://youtu.be/jN2md27KKKk).

For any additional questions, please contact me at **wwallach95@gmail.com**

## Repository Structure
**Data:** Folder of data for the project

**Drafts:** Folder of notebooks of different initial data preprocessing to different degrees of success and cleanliness of code

**Photos:** Folder of pictures used in the project, mostly jpgs and pngs of visualizations

**Final_Pre:** The final notebook for the project, in which the final working model is reached

**Non Technical Slide Deck:** PDF of the powerpoint presentation that goes along with the [non technical presentation](https://youtu.be/jN2md27KKKk)


```python

```
