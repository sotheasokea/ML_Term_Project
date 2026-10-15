# Experiment Summary Report (2026-10-15 11:47:31)

```text
================================================================================
EXPERIMENT RUN LOG — 2026-10-15 11:47:31
================================================================================

1. MASTER CONFIGURATION SETTINGS:
   - RANDOM_STATE           : 55
   - NUMBER_OF_FEATURES     : 3
   - RFE_SELECTOR_MODEL     : Random Forest
   - SFS_SELECTOR_MODEL     : Decision Tree
   - PCA_VARIANCE           : 0.95 (4 components kept)
   - CV_FOLDS               : 5
   - UNIQUE_FINALIST_MODELS : True

2. FEATURES SELECTED BY EACH METHOD:
   - Baseline (All 6)       : Type, Air temperature [K], Process temperature [K], Rotational speed [rpm], Torque [Nm], Tool wear [min]
   - ANOVA                  : Air temperature [K], Torque [Nm], Tool wear [min]
   - Pearson Correlation    : Torque [Nm], Tool wear [min], Air temperature [K]
   - Adapted Lasso (L1)     : Torque [Nm], Rotational speed [rpm], Air temperature [K]
   - RFE (Random Forest) : Rotational speed [rpm], Torque [Nm], Tool wear [min]
   - Forward SFS (Decision Tree) : Rotational speed [rpm], Torque [Nm], Tool wear [min]
   - Backward SFS (Decision Tree): Air temperature [K], Torque [Nm], Tool wear [min]
   - PCA (95% var)        : 4 orthogonal components

3. BEST MODEL PER FEATURE-SELECTION METHOD (VALIDATION SCREENING):
   Feature selection             Model  Validation failure F1  Validation failure recall  Validation failure precision  Validation missed failures  Validation false alarms
No feature selection               MLP               0.769231                   0.686275                      0.875000                          16                        5
               ANOVA Gradient Boosting               0.536585                   0.431373                      0.709677                          29                        9
 Pearson correlation Gradient Boosting               0.536585                   0.431373                      0.709677                          29                        9
  Backward selection Gradient Boosting               0.536585                   0.431373                      0.709677                          29                        9
       Adapted Lasso               MLP               0.506329                   0.392157                      0.714286                          31                        8
                 PCA               MLP               0.500000                   0.352941                      0.857143                          33                        3
   Forward selection               MLP               0.485714                   0.333333                      0.894737                          34                        2
                 RFE               MLP               0.485714                   0.333333                      0.894737                          34                        2

4. STACKING ENSEMBLE (VALIDATION):
   Feature selection            Model  Validation failure F1  Validation failure recall  Validation failure precision  Validation missed failures  Validation false alarms
No feature selection Stacking (Top 3)               0.808989                   0.705882                      0.947368                          15                        2

5. TOP 3 FINALISTS AFTER 5-FOLD CV HYPERPARAMETER TUNING (VALIDATION):
   Feature selection             Model  Validation F1  Validation recall  Validation precision  Validation missed failures  Validation false alarms
No feature selection Gradient Boosting       0.786517           0.686275              0.921053                          16                        3
No feature selection     Random Forest       0.777778           0.686275              0.897436                          16                        4
No feature selection               MLP       0.757895           0.705882              0.818182                          15                        8

6. SELECTED WINNER & TUNED HYPERPARAMETERS:
   - Winning Model          : Gradient Boosting
   - Winning Feature Method : No feature selection (Type, Air temperature [K], Process temperature [K], Rotational speed [rpm], Torque [Nm], Tool wear [min])
   - Best Hyperparameters   : {'learning_rate': 0.1, 'max_depth': 5, 'n_estimators': 200, 'subsample': 1.0}

7. FINAL UNSEEN TEST SET PERFORMANCE (EVALUATED ONCE):
   - Test Failure F1        : 0.8132
   - Test Failure Recall    : 0.7255
   - Test Failure Precision : 0.9250
   - Test Balanced Accuracy : 0.8617
   - Test Missed Failures   : 14
   - Test False Alarms      : 3
================================================================================


```
