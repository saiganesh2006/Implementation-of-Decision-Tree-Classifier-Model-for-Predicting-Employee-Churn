# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4. From sklearn import LabelEncoder to convert string values to numerical values.
5.From sklearn.model_selection import train_test_split.Assign the train dataset and test dataset.
6.From sklearn.tree import DecisionTreeClassifier.Use criteria as entropy.
7.From sklearn import metrics.Find the accuracy of our model and predict the require values.
Programs :
## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: D.B.V. SAI GANESH
RegisterNumber:  212223240025
*/
```
```
import pandas as pd
data = pd.read_csv("Employee.csv")
data.head()
data.info()
```
## Output:
![image](https://github.com/saiganesh2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145742342/9b90d5f1-5e6f-4699-a79e-11d8e8e7e81d)

```
data.isnull().sum()
```
## Output:
![image](https://github.com/saiganesh2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145742342/7237da58-3478-4610-9331-7af50c8824bd)

```
data["left"].value_counts
```
## Output:
![image](https://github.com/saiganesh2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145742342/58d2e516-bc88-4bb1-9295-d7dc4e039d39)

```
from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
```
## Output:
![image](https://github.com/saiganesh2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145742342/6e153fb4-d436-41c6-a49e-df0a6c66af3a)

```
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]

x.head()
```
## Output:
![image](https://github.com/saiganesh2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145742342/fa63566d-5d59-4203-9e39-f0a7054fe48c)

```
y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)

from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
```
## Output:
![Screenshot 2024-04-01 094718](https://github.com/saiganesh2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145742342/ab348377-356b-466b-bf36-30cb084c4ac0)

```
y_pred = dt.predict(x_test)
from sklearn import metrics

accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy
```
## Output:
![Screenshot 2024-04-01 094737](https://github.com/saiganesh2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145742342/ba88a734-1a9d-49b6-90ee-16ba33e3f198)

```
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```
## Output:
![Screenshot 2024-04-01 094759](https://github.com/saiganesh2006/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/145742342/62afddd4-c8be-48f1-b4c8-14b3a2ecc57a)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
