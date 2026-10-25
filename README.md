# Customer Churn Analysis — Exploratory Data Analysis

## Project overview
This project explores customer churn in a telecom-style customer dataset to identify customer segments and service patterns that may warrant retention attention. The analysis is built in Python using Pandas, NumPy, Matplotlib and Seaborn.

**Analysis type:** Descriptive analytics / Exploratory Data Analysis (EDA)  
**Prediction model:** Not included in this notebook  
**Dataset snapshot in notebook:** 7,043 customers, 21 columns

## Business questions
- What proportion of customers churned?
- How does churn vary by contract type and tenure?
- Which service, billing and payment segments have higher observed churn?
- What practical retention experiments could be prioritised?

## Key findings from the notebook's saved outputs
- **Overall churn:** 1,869 of 7,043 customers churned — **26.54%**.
- **Contract type:** Month-to-month customers had a **42.71%** churn rate, compared with **11.27%** for one-year contracts and **2.83%** for two-year contracts.
- **Early tenure:** Customers with 0–6 months of tenure had a **52.94%** churn rate. The rate declined across later tenure bands, reaching **9.51%** for 49–72 months.
- **Payment method:** Electronic-check customers had a **45.29%** churn rate, notably above the overall rate.
- **Service segments:** Fiber-optic customers had a **41.89%** churn rate. Customers without online security (**41.77%**) or tech support (**41.64%**) also showed elevated churn.
- **Customer profile:** The recorded churn rate was **41.68%** among senior citizens versus **23.61%** among non-senior customers. Customers without dependents had a **31.28%** churn rate versus **15.45%** for customers with dependents.
- **Customer economics:** Median tenure was 10 months among churned customers versus 38 months among retained customers. Median monthly charges were 79.65 versus 64.43, respectively.

These are descriptive associations from the notebook outputs. They do not establish that any factor causes churn.

## Recommended business actions
1. **Prioritise the first 6 months:** Test welcome journeys, early-life check-ins and proactive issue resolution. Measure churn by acquisition cohort.
2. **Review month-to-month experience:** Investigate cancellation reasons, service incidents, price sensitivity and contract conversion opportunities. Do not assume longer contracts alone solve dissatisfaction.
3. **Audit electronic-check journeys:** Examine payment failures, billing confusion and customer friction; test support or payment-choice nudges.
4. **Investigate fiber-optic churn:** Compare speed/reliability complaints, local availability, pricing and service tickets before designing interventions.
5. **Test support/security engagement:** Check whether customers without these add-ons are experiencing unresolved issues. Offer relevant help based on need rather than pushing add-ons indiscriminately.
6. **Run controlled experiments:** Use a holdout/control group where feasible; compare churn, complaints, costs and customer experience before scaling an intervention.

## Methodology
- Loaded the CSV into Pandas.
- Standardised column labels and trimmed text fields.
- Converted `TotalCharges` to numeric after treating blank strings as missing. The notebook recorded 11 blank values, all associated with zero tenure, and filled them with zero.
- Checked duplicate customer IDs and missingness.
- Compared churn rates within each category using row-normalised cross-tabulations.
- Visualised churn distributions by contract, tenure, service, payment and charge metrics.

## Limitations
- The analysis is descriptive and does not train a churn prediction model.
- Segment-level differences may be confounded by other variables.
- The `TotalCharges` fill assumption should be rechecked if using a different dataset version.
- Exact outputs depend on the CSV used. The report reflects the uploaded notebook's saved outputs; re-run the notebook against the intended CSV to refresh all values and charts.
- The notebook expects a CSV file. Ensure `DATA_PATH` points to the exact filename and location; avoid accidental spaces in the filename.

## How to run
1. Put the CSV file in the same folder as `Customer_Churn_Analysis.ipynb`.
2. Open the notebook in Jupyter.
3. Confirm the filename in the `DATA_PATH` cell matches the actual CSV filename exactly.
4. Run all cells from top to bottom.

## Suggested next phase
Build a separate, properly evaluated churn-risk model only after confirming the dataset and target definition. Start with a train/test split and a baseline logistic regression; assess precision, recall, ROC-AUC and the cost of false negatives. Check leakage and calibration before proposing operational use.

## Files
- `Customer_Churn_Analysis.ipynb` — exploratory analysis.
- `Customer_Churn_Analysis_Report.pdf` — executive-style report with charts.
