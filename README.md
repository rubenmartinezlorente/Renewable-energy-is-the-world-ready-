<img src="https://bit.ly/2VnXWr2" alt="Ironhack Logo" width="100"/>

# RENEWABLE ENERGY: World are ready?
**Rubén Martínez Lorente**

** *Data Analytics at Ironhack School in Barcelona.  20/12/2019* ** 

## Content
- [Project Description](#project-description)
- [Hypotheses / Questions](#hypotheses-questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Statistics] (#Statistics)
- [Machine Learning](#machine-learning)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Workflow](#workflow)
- [Organization](#organization)
- [Links](#links)

## Project Description
This is the final project performed in the Data analytics Ironhack school of Barcelona (Spain). The project is based in analayze and stimate how ready are the countries in the new century for clean and green sources of energey.

 Through different datasets from a [US. European Information Administration](https://www.eia.gov/todayinenergy/), I analyze in 4 different modules all need information to answer the main questions (see [Hypotheses / Questions](#hypotheses-questions)).

The motivation of this project is make a review of the different renewable, so-called **RE**, and no renewable energies, so-called **NRE**. Energy concept is a topic that moves billions of dollars around the world. It is one of the most important, rich, powerful and basic business that support the humankind. You think if there is not such business, almost part of the life we conceive daily it would not exist.

Currently, is one of the most important issue in the world due to the climating emergency. Nowdays, the XXVth edition of **UN Climate Change Conference(COP25)** takes places in Madrid (Spain) from December 2nd to 13th (See [COP25](https://unclimatesummit.org/))

 With all data, using statistics tools and machine learning algorithms we want to cluster the countries about **how ready are these countries to implement renewable energies and not use fosile(not renewables) energies in the next decades**

## Hypotheses / Questions

**The society (countries in particular) is already ready to implement renewable energy, without the non-renewable dependency?**
* How to answer?
I notice the answer is very generic and ambiguous, for this reason, we have a step-to-step plan that we can answer with enought preccision. The plan consists in 4 sections with a very clear purpose:
 1. **Data cleaning**: Clean and organize the dataset to be useful for the next modules.
 2. **Data Analysis**: The second module helps us to understand what is the current worldwide scenario about the energy consumption (net, renewable and no renewable).
 3. **Statistics**: This module stimate in a *very simple stimation* (not using Machine Learning) the trends of the countries appliying the linear regression method for the next 80 years (2020-2100). With these data we propose a classification of green and not one countries (in reference of how much renewable energy use that country).
 4.**Machine Learning**: The last module we use unsupervised machine learning to cluster the countries (same number of cluster using in module three) using different features with NO or LOW correlation with energy attributes (population, GDP).

## Dataset
Information used in this project is provided from the [US. European Information Administration](https://www.eia.gov/todayinenergy/). In particular we use a interface from International Energy Statistics. There are much more information from what we need for this project and they have to be cleaned.
In particular we use the following information from the 229 countries along 37 years (from 1980 to 2017):

* Consumption: Net electricity consumpted by countries measured in Billions of KiloWatts per hour (b. Kwh)
* Generation: Electricity generated by county (b. Kwh). 
In this dataset (so-called 'superdataset') we have 4 different dataset that repeats ciclilly along 229 rows (countries) (see [Cleaning]).
    + Renewable
    + Fossile (Non Renewable)
    + Nuclear
    + Hydrodynamical pumped store


* Capacity: Electricity able to produce in the *installations* by county (b. Kwh).
Analogue situation than in generation dataset. This dataset (so-called 'superdataset') we have 4 different dataset that repeats ciclilly along 229 rows (countries) (see [Cleaning]).
    + Renewable
    + Fossile (Non Renewable)
    + Nuclear
    + Hydrodynamical pumped store

* Imports: in b. Kwh
* Exports: in b. Kwh
* C02 emissions: emissions measured in million metric tons carbon dioxide 

Also, from the same website, we use different countries ranking measures to make a quick description in the current energetic situation (2017):
* Ranking of electri

From these datasets, we make a data cleaning and data exploring to prepare ready for the last step: Time Series -Machine Learning-

## Cleaning
Data Cleaning information you may find in the Jupyter notebook file: **1.data_cleaning.ipnyb**. It is splitted in two different steps:
### 1st step **SLICING SUPERDATASET**
For Generation and Capacity superdatasets we define a function we slice these superdatasets in five small ones.

### 2nd step **CLEANING DATASET**
 Define two functions (*clean1*, *clean2*) to automatize the cleaning for all dataset we have. I checked previously that all of them share the same 'deffects', which are the following ones:

* 1 dropping the empty  and the units columns. 

    *Clean 1* drops the two first rows, *Clean 2* drops the first row.

* 2 dropping the first 2 rows because there are the quantity to analyze and the category

* 3 rename the country column

* 4 Set'country' index

* 5 Replacing '--', '-' for nan. I discover for trial and error.

* 6 Drop the missing values.

* 7 Convert the data from objetct to number (float or int)

* 8  Transpose the matrix to have the country as index and year as columns.

### 3rd step **Read and clean the ranking datasets**
I clean (I found these data pretty cleaned) a bit transforming some columns such as 'Value' in float64 and dropping a empty columnn.

### 4th step **SAVING DATA**
I save all datasets in different .csv files in the folder **CLEANED_DATA** to read in the Analysis part.

## Analysis
Data Analysis information you may find in the Jupyter notebook file: **1.data_analysis.ipnyb**. 
The description of the current energetic situation thourgh plots and descriptive analysis. 
The data analysis in 3 steps:

 ### 1.Evolution of  countries in renewable energy consumption.

Plots of some countries showing the eletricity net consumption, the renewable and fossilie (no renewable) generation and installatins. 

From these plots, we can extract an additional feature in the Machine Learning model: Check if the renewable energy absolute variation is higher than non-renewable absolute variation. If it is so, we can proceed to apply the Machine Learning algorithm, if it is not, renewable energy can converge with the electricity net demand of society.

 ### 2.Analysis for the *Generation renowable ratio* for all countries: 
We want to show through different kind of plots the current renewable electricity situation is in the world.
For this porpusse, we use Tablelau as visualization tool [Tableau]as visualiztion support to map different metrics such as, how is the balance of trade (exports-imports), how are the Ranking of the renewable, no-renewable or net electricity consumption countries. 

### 3.Preparation of information to apply Time Series in Machine Learning:
We prepare two different datasets to calculate how is the annual variation of energy consumption along the years for all countries: the *relative* variation, which offer more detail and is more useless and the *absolute* variation (from 1980).

## Statistics
## Machine Learning
*Include this section only if you chose to include ML in your project.*
* Describe how you trained your model, the results you obtained, and how you evaluated those results.

## Conclusion
* Summarize your results. What do they mean?
* What can you say about your hypotheses?
* Interpret your findings in terms of the questions you try to answer.

## Future Work
Address any questions you were unable to answer, or any next steps or future extensions to your project.

## Workflow
Outline the workflow you used in your project. What were the steps?
How did you test the accuracy of your analysis and/or machine learning algorithm?

## Organization

The project folder in Github [Repository] is organized in the following mode:

* jupyter_notebook_files
    - 1.data_cleaning.ipynb
    - 2.data_analyzing.ipynb

* cleaned_data
    * ranking

* analyzed_data
    * plot_countries
    * tableau
        * rankings

* raw_data

## Links
Here are the links related to the project, where you may find all files need to understand the project.


[Repository](https://github.com/)  

[Slides](https://slides.com/)  

[Trello](https://trello.com/en)

[Tableau](https://public.tableau.com/profile/rub.n5876#!/vizhome/Project5_15761776874140/ratio_consumptionbypopulation)