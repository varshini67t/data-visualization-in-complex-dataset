# data-visualization-in-complex-dataset
## Ex:09 Data Visualization


# AIM

To Perform Data Visualization on a complex dataset and save the data to a file.
ALGORITHM

STEP 1

Read the given Data

STEP 2

Clean the Data Set using Data Cleaning Process

STEP 3

Apply Feature generation and selection techniques to all the features of the data set

STEP 4

Apply data visualization techniques to identify the patterns of the data.

Try to find solutions for the following questions

based on the "tips" dataset:

# CODE

import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
print(df)

df.isnull().sum()


# HANDLING OUTLIERS

plt.figure(figsize=(8,8))
plt.title("Data with Outliers")
df.boxplot()
plt.show()

# REMOVING OUTLIERS

plt.figure(figsize=(8,8))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()

1) Which day of the week has the highest total bill amount?

sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()


2) What is the average tip amount given by smokers and non-smokers?

sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")

3) How does the tip percentage vary based on the size of the dining party?

df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

4) Which gender tends to leave higher tips?

sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")

5) Is there any relationship between the total bill amount and the day of the week?

sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")

6) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()

7) Which dining party size group tends to have the highest average total bill amount?

sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()

8) What is the distribution of tip amounts for each day of the week?

sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()

9) How does the tip amount vary based on the type of service (lunch vs. dinner)?

sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()

10) Is there any correlation between the total bill amount and the tip amount?

sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()

# OUTPUT

![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/49f9c0a1-41f5-4dbd-8836-cd1d938da6d8)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/67e187ce-eac1-472c-a922-80cbb4009a06)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/7b97da7c-9632-4ed5-ac83-5c4fb298c737)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/9c363531-78b6-463b-81ef-58df206e28cd)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/9c1c6ec0-38f7-44f2-ab4c-33ce3060f2d5)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/d8a4cbdf-51ae-4322-b9b2-05be21e8f9f9)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/527a30ab-6a38-4647-aaaa-d9e1a1252aac)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/32de1b24-69ae-401a-99bf-227c8f6edc91)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/6750653f-7f3b-4281-a952-047dbc243b5f)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/08aa6164-8e7f-43b0-8ab9-85af8941bb56)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/a28c3a8d-895d-4d81-8678-d3fe3eb4c430)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/045a4373-c798-4886-b6dc-fabd4a142996)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/dd3d0a46-a926-4551-85bc-8c9de3703b42)
![image](https://github.com/varshini67t/data-visualization-in-complex-dataset/assets/107982953/2036d498-7e07-411d-bd5a-1d051009a613)


# RESULT

  Thus we have performed data visualization operations on complex dataset.
