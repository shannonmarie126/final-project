# final-project

Supervised Machine Learning Model created using XGBoost to predict a History of mental illness based on 14 socioeconomic factors. Factors are visualized using Tableau. 

Preprocessing of the data included binning ages and incomes to prevent overfitting, ordinal encoding and dummies encoding of the categorical data. SMOTE was used in the optimization model to synthesize data and decrease the imbalance in order to increase recall. 

Initial model: while the accuracy was about 70% on the initial model, this is likely due to the imbalance in the data causing the model to select "no" every time (data is approximately 30% yes and 70% no). The extremely low recall, 0.02%, for this model is further evidence of this, showing the model is recalling almost none of the true positives. The AUC score of 0.50 means the model is right about half the time, therefore not an ideal predictor of mental health. 

<img width="276" alt="initial_model" src="https://github.com/user-attachments/assets/5ea218e8-4f9f-4ca4-84ec-40d765592509" />

<img width="276" alt="initial_model_values" src="https://github.com/user-attachments/assets/35e03026-5e65-41ad-b4c1-0ce993a92b84" />

Optimized model: For the optimization, SMOTE was used to balance the data in order to increase the models ability to detect positives. Learning rate was decreased from 0.1 to 0.05 to prevent overfitting, max depth was increased from 6 to 10, n_estimators was increased from 100 to 300 and sub_sample was decreased from 1 to 0.8 to prevent overfitting. col_sample_by_tree and min_child_weight were left at preset values. 

For the final model, accuracy was still about 70%, but recall increased to 58% and precision to 78%, meaning 58% of positives were caught by the model, and 78% of the positives caught were true positives. The AUC ROC score for this model is 70.5%, a marked improvement from the initial model indicating better performance of this model overall. 

<img width="379" alt="optimized_model" src="https://github.com/user-attachments/assets/7f38f533-ab0c-4b11-acc9-289ce2d6a356" />

<img width="263" alt="optimization_values" src="https://github.com/user-attachments/assets/0ce8fcf1-63c0-4476-a184-6cf181d560a9" />


<img width="438" alt="classification_optimization" src="https://github.com/user-attachments/assets/08bf68d2-048a-48cf-bb6f-ec1831c1987d" />

Precision/Recall Graph: shows the trade off between precision and recall for this model. 

<img width="696" alt="precision:recall" src="https://github.com/user-attachments/assets/64fe950b-02b4-4381-8e9e-72def71462b3" />







