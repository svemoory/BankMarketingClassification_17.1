# Will a customer subscribe to term deposit?

### Overview:

This a a practical application assignment for PCMLAI program from Berkeley Haas to analyzes a Portuguese bank's direct phone call marketing campaigns, which aimed to promote term deposits among existing customers. 

### DataSet:
Our dataset comes from the UCI Machine Learning repository [link](https://archive.ics.uci.edu/ml/datasets/bank+marketing).  The data is from a Portugese banking institution and is a collection of the results of multiple marketing campaigns.  We will make use of the article accompanying the dataset [here](CRISP-DM-BANK.pdf) for more information on the data and features. Here is the link to the [Jupyter Notebook](https://github.com/svemoory/BankMarketingClassification_17.1/blob/main/prompt_III.ipynb).

### Business Understanding

The main objective is to increase the effectiveness of the bank's telemarketing campaign by determining the best predictive model to identify the customers and their traits such as Education, Marital Status, Age etc that most likely drives them to subscribe to term deposit.

### Findings:

After an EDA, we have identified various features to see which one qualifies to be numeric representation vs categorical. Outliers were eliminated and various classification techniques were used to find the best predictive model. The confusion Matrix and ROC curve for Logistic Regression is shown below:
![image](https://user-images.githubusercontent.com/28323151/216289467-c1ccaba4-9a40-4448-9481-347496233e5f.png)

The comparison of various classification problems after GridserachCV hyperparameter tuning is give below:

![image](https://user-images.githubusercontent.com/28323151/216289198-c39dd0a8-8528-4c5d-8514-3c685c802f15.png)



* The best model that is able to maximize the true postive so that there are no missed opportunities, is achieved  by Logistic Regression followed by Decision Tree 
* At the same time it is also important not to scam the customers and that is achieved by SVM. But using the full dataset it takes more than 4 hours to train.
* Inspecting the coefficients indicates that less educated groups and students and retirees are more susceptible to term deposits
* The months of July and Aug seem to add to successful calls, it could be because of summer college semesters, coorelated to the education group

### Next steps and recommendations

* We may need to collect more data to balance the classes.    
* Add more feature like gender and other economical factors to find cause and effect
* Try  different ranges for hyperparameter tuning.  May be use pruning to improve the perofrmance of decision tree
* ROC_AUC score was used because of highly imbalanced dataset. Try other scoring like Recall.
* Since contact mode telephone does not have a positive coefficient, the camplaigns can focus on other modes of communication like email or flyers
