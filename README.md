# TITANIC_SURVIVAL_PROBLEM
Solution to Titanic Survival Problem at Kaggle

#Data Cleaning<br>
After taking a look at the data, it is quite clear that certain data fields are empty, i.e, we have some incomplete features.
As we can clearly see, there are 891 fields of data for the features contained in the training data out of which only 714 fields in Age feature is field.<br>
Apart from that, after further analysis it is quite complete that the Embarked feature also contain 2 incomplete fields, while Age have 177 and Cabin, the most, 687.<br>
Now, we need to look at the relations between the features and our target, i.e, survival. Plotting curves in easily the best method.<br>
We start with the age and sex and look at the plots. As you may notice, survival rate is higher for men whose age is between 18 and 30 years old while the the same rate is higher for women between the age of 14 and 40. Looking at this information gives a pretty useful result, i.e., we can create age groups which have certain survival probablity for themselves.<br>
Next we take a look at whether Passenger Class plays any significant role on his survival. Plotting the curves we can certainly look at the realtionship between the survival rate and the Passenger Class. So, passenger class is a useful feature.<br>
The two features Siblings and Parents on board for each passenger doesn't make much sense to me, so I'm going to group these two features and create a new feature known as relatives for the same. Apart from that another feature alone/not alone is attached alongside so as to keep track whether the passenger was alone or not alone.<br>
Now, we can take a look at the relationship between realtves and survival which indeed shows that survival is attached with the number of relaives onboard (Well, most of us do want to save our families, isn't it true?).<br>
Each passenger have their unique passenger ID, thus making the feature pretty useless as it always have a new value making it incapable of setting up a trend. So, we drop it.<br>
Next up, we need to complete the incomplete data. I started with the Age feature first.<br>
To complete the age feature I am going to use the rand function and generating random values between (mean - standard deviation and mean + standard deviation) which in my sight is quite a fair method.<br>
To complete the Embarked feature, we only have three possible values so I am going to sue the most frequent one.<rb>
The Name feature doesn't carry much significant value, yet we can extract the titles from it, we can give us some insight of the passenger's background, which may have some realtion with their survival.<br>
We convert the genders of the passenger to numbers so that the model can train on them easily.<br>
The fair also need to converted from float to an int value for easy computation and model training. Apart from that, missing values are filled with 0.<br>
Since, there are a large unique number of tickets, we drop the tickets feature as there exist a few patterns.<br>
We convert the embarked feature to numbers, i.e., 0, 1 and 2 for training purpose.<br>
We classify the Age feeature in a number of ranges like 0-11, 12-18, 18-22, etc.<br>
We know that, there is a really bog amount of data missing in Cabin feature, so we drop it.<br>
We create a new feature of age and pclass, as we earlier saw they were together related to survival.<br>
Fare Per Person (fpp) can be another useful feature, so we create fpp based on fare and number of family members aboard.<br>
  <br><br><b>#TRAINING MODEL</b><br>
Now, we train our model for the remaning features.<br>
For X_train, we drop the survived featurea nd for train_targets we use the survived feature, i.e., Survived is the label for our problem (We knew that all along).<br><br>
For the model purpose, I'm using the Ramdom Forest Classifier and I achieve an accuracy of 91.02%.
