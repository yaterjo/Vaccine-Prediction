# FluVax Forecast: Optimizing Supply with Data-Driven Predictions
#### By Bekah McLaughlin And Johnathan Yater

<p align="center">
  <img src = ./Images/vaccine.jpeg>
</p> 

## Overview and Business Need

The Public Health Department aims to boost influenza herd immunity this year, particularly amidst the ongoing prevalence of Covid-19. Ensuring adequate vaccine supply deployment is crucial to meet demand, prevent shortages, and avoid critical illness in the most vulnerable populations.

#### Optimizing Access

The primary objective is to ensure plenty of vaccine supply across regions, with a slight preference for overestimation rather than underestimation. Our goal is to prevent anyone who desires or requires vaccination from being unable to access it.

#### Incidental Opportunities for Targeted Health Initiatives

While optimizing supply remains our ultimate goal, examining factors influencing flu vaccine status provides the Public Health Department with insights into targeted health initiatives aimed at dismantling barriers to vaccination.

## The Dataset 

This dataset originates from the NHFS National Flu Survey conducted in 2009. It contains information regarding individuals' reception of both the seasonal flu and H1N1 flu vaccinations, alongside their demographic, behavioral, and health attributes. The survey contains responses from 26,707 participants. Information on the column labels can be found in the Column_Label file in the `Data` folder.

## Analysis, cleaning, and pre-processing

The dataset underwent minimal cleaning, primarily addressing missing values, removing irrelevant or incomplete data, and excluding columns related to H1N1 since our focus was on seasonal flu, not H1N1. Additionally, standard cleaning and preprocessing procedures were applied to prepare the data.

In particular, feature engineering techniques were used to consolidate numerous behavioral features into a single score and numerous opinion features into a single score.

## Modeling

In total, we trained and fine-tuned three distinct models to predict flu vaccine status.

Our initial model, a decision tree, utilized various demographic features to predict flu vaccine status. We took it from being noisy and unreadable to being optimized, but it's recall was still only ~ 0.63.

  <p align="center">
  <img src = ./Images/decisiontree1.png>
</p> 
  <p align="center">
  <img src = ./Images/decisiontree2.png>
</p> 
 <p align="center">
  <img src = ./Images/decisiontree3.png>
</p> 

We developed another model using logistic regression, which compared seasonal flu status to behavioral features including opinion score and whether a doctor recommended the vaccine. These features had fair correlations with vaccine status, as this model seemed promising. However, although it outperformed our initial model, it was not our top performer.

Our highest-performing model was a logistic regression model incorporating features related to behavior, opinion, demographics, and health literacy. After extensive fine-tuning, the model achieved a recall of approximately 0.73. This is the highest score we attained, therefore, it will be the model we will deploy for use by the Public Health Department.

  <p align="center">
  <img src = ./Images/log1.png>
</p> 
  <p align="center">
  <img src = ./Images/log2.png>
</p> 


## Recommendations and Next Steps

#### Public Health Recommendation
We strongly advise the Department of Health to utilize our top-performing model for predicting vaccine requirements in the upcoming flu season. While individual decisions regarding flu vaccination are nuanced, our model provides a valuable starting point for estimating vaccine supply needs. While it may not offer exact predictions, it serves as a valuable tool for initial planning.

#### Next Steps
During our Exploratory Data Analysis (EDA), we observed that factors like opinion and doctor recommendation exhibited stronger correlations with vaccine status. Further exploration of these factors could unveil potential barriers to vaccination among specific demographics, informing targeted public health interventions."

## Repository Structure

```
├── Data
├── Images
├── .gitignore
├── powerpoint.pdf.pptx
├── public_health_fluvaccine_modeling.ipynb.ipynb
└── README.md
```
