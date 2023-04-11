# Ex-04-Multivariate-Analysis
## AIM:
To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file.

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr() .

### STEP 8
Save the final data set into the file.


## PROGRAM:
```
Developed By : Silambarasan K
Reg No: 212221230101
```

```py
Program developed by : Shrruthilaya G
Register number : 212221230097

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.isnull().sum()

data.dtypes

sns.scatterplot(data['Postal Code'],data['Sales'])

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Postal Code"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Postal Code",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES") 
plt.ylabel=("Postal Code") 
plt.show()

states=data.loc[:,["Segment","Sales"]] 
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SEGMENT") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)

```
## Output:
### Dataset:
![head](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/blob/main/dataset.png)

### Head:
![head](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/head.png)

### Info :
![info](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/info.png)

### Description:
![describe](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/describe.png)

### Data type:
![datatype](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/dtype.png)

### Null data:
![null](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/nulldata.png)

### Scattor plot:
![plot](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/scatterplot.png)

### Bar Plot(States & Sales):
![bar](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/barplot1.png)

### Bar Plot(States & Postal code):
![bar](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/barplot2.png)

### Bar plot:
![p](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/barplot3.png)

### Bar Plot:
![r](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/barplot4.png)

### Coorelation:
![corr](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/corr.png)

### Heat Map:
![map](https://github.com/Shrruthilaya-Gangadaran/Ex-04-Multivariate-Analysis/raw/main/heatmap.png)

## Result:
Thus the program to perform EDA on the given data set is successfully executed.

