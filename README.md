# Ex-04-Multivariate-Analysis

## AIM:

To perform Multivariate EDA on the given data set.

## EXPLANATION:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:

### Step1:

Import the built libraries required to perform EDA and outlier removal.

### Step2:

Read the given csv file.

### Step3:

Convert the file into a dataframe and get information of the data.

### Step4:

Return the objects containing counts of unique values using (value_counts()).

### Step5:

Plot the counts in the form of Histogram or Bar Graph.

### Step6:

Use seaborn the bar graph comparison of data can be viewed.

### Step7:

Find the pairwise correlation of all columns in the dataframe.corr()

### Step8:

Save the final data set into the file.

## PROGRAM:
```
Developed by :S.M.Syed Mokthiyar
Registration Number :212222230156
```
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df.head(6)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
sns.scatterplot (df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sns.barplot(df['Postal Code'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
## OUTPUT:
### HEAD:
![Screenshot 2023-04-10 112823](https://user-images.githubusercontent.com/120232371/230836668-7d3e3693-81e3-4161-b4f9-8061f7a93980.png)
### INFO:
![Screenshot 2023-04-10 112940](https://user-images.githubusercontent.com/120232371/230836843-e3f90a90-e09e-4dc4-a4af-21ff0bea71c6.png)
### DESCRIBE:
![Screenshot 2023-04-10 113035](https://user-images.githubusercontent.com/120232371/230836996-c7d35a31-d995-4de9-8eb8-b831b1b4dd2b.png)
### REMOVING NULL VALUES:
![Screenshot 2023-04-10 113140](https://user-images.githubusercontent.com/120232371/230837175-a23de069-b3a5-4916-8199-1f7a765e445a.png)
### SCATTERPLOT:
![Screenshot 2023-04-10 113323](https://user-images.githubusercontent.com/120232371/230837352-0878c773-19a6-46bc-9da7-c1c34f87431d.png)
### BARPLOT:
![Screenshot 2023-04-10 113444](https://user-images.githubusercontent.com/120232371/230837560-7b8d3818-371e-4dc9-956e-04724e73dd8c.png)
![Screenshot 2023-04-10 113524](https://user-images.githubusercontent.com/120232371/230837655-f014580c-87ed-46c1-b7cc-b24d5fc110f5.png)
![Screenshot 2023-04-10 113539](https://user-images.githubusercontent.com/120232371/230837683-a81f1258-ce0d-4234-a656-b6703c6c3ebb.png)
### HEATMAP:
![Screenshot 2023-04-10 113644](https://user-images.githubusercontent.com/120232371/230837818-e40fb309-8c11-41db-a737-f4c9837ede1b.png)

## RESULT:
Thus the program to perform EDA on the given data set is successfully executed.




