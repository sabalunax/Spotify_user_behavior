...still in progress

UPDATE: need to chceck if sample sizes of categories other than age, in relation to the dependant variable, are ok.

[charts](https://github.com/sabalunax/Spotify_user_behavior/blob/spotify/02 - Charts/01 - Links_to_charts.md)

The data concerning Spotify users predominantly consisted of categorical variables.
Missing data were largely imputed using the mode. An exception was the variable spotify_subscription_plan,
which, due to its potential significance for future model development, 
was imputed by iterative imputer.

A logical condition was applied to exclude observations of individuals 
who neither have nor intend to have a paid plan but indicated a preferred plan.

In columns with numerous categorical variables, often with very small counts, 
variables were consolidated into new categories such as "other" or "mixed."

Where feasible, categorical variables were transformed 
into ordinal variables; for the remaining variables, one-hot encoding was performed.

For convenient data interpretation, a heatmap based on Kendall's correlation matrix was created, 
displaying only variables with correlations above 0.5 or below -0.5. 
These correlated variables were also listed.

To avoid multicollinearity, highly correlated variables were removed, 
as well as the age category 6-12, which contained only one observation.

The dependent variable was "premium_sub_willingness."

The machine learning algorithms applied included:
- Logistic Regression, 
- Regularized Logistic Regression, 
- XGB Classifier, 
- XGB Classifier with cross-validation, 
- Bagging XGB Classifier.

RFE was employed to select the best variables, appropriately tailored for each model.

The best results were achieved with the XGB Classifier with cross-validation 
and the Bagging XGB Classifier, with the following metrics:

Model: XGB cross-val
Accuracy: 0.76
Precision: 0.60
Recall: 0.58
F1-score: 0.56
ROC AUC: 0.78

Model: XGB bagging classifier
Accuracy: 0.78
Precision: 0.62
Recall: 0.58
F1-score: 0.57
ROC AUC: 0.79

The final step was creating interactive plots using Plotly, 
which were shared on Plotly Chart Studio, making them easily shareable.
