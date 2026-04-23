# Meeting Context and Relationship Outcomes


## 1. Introduction

This analysis investigates how couples meet and whether meeting context is associated with later relationship outcomes. Two main questions guide the research:

1. Do same-sex and different-sex couples differ in how they meet?
2. Does meeting context at Wave 1 predict relationship status at Wave 3, controlling for prior relationship status and demographic factors?

Understanding these relationships provides insight into whether differences in relationship outcomes are driven by who couples are or how they meet.


## 2. Data and Feature Construction

The dataset contains survey responses across multiple waves (Wave 1, Wave 2, Wave 3).

Meeting Context Variables

Meeting context is constructed using multiple binary indicators (yes/no), including:

- Meeting through friends, family, or neighbors
- Meeting in bars, parties, or public places
- Meeting at work
- Meeting online

These are aggregated into three broad categories:

Social (offline, informal interactions)
Work (professional environments)
Online (digital platforms)

⚠️ These categories are not mutually exclusive. Respondents could select multiple meeting contexts, meaning the data reflects contexts involved in meeting, rather than a single definitive first meeting.

The number of reported meeting contexts per respondent is distributed as follows:

- 1 context: 1,371
- 2 contexts: 932
- 3 or more contexts: smaller counts
- Missing: 116

## 3. Clustering Relationship Profiles

To identify patterns in meeting behavior, KMeans clustering was applied using meeting context variables and relationship characteristics.

| Cluster | Social | Work | Online | Interpretation                   |
| ------- | ------ | ---- | ------ | -------------------------------- |
| 0       | **High**   | Low  | Low    | Socially-initiated relationships |
| 1       | Medium | Low  | **High**   | Online-initiated relationships   |
| 2       | Medium | **High** | Low    | Work-based relationships         |

Although social interaction appears across all clusters, clusters are defined by their dominant meeting pathway.

Therefore, the analysis reflects reported meeting contexts rather than a single definitive meeting pathway.


## 4. Meeting Context by Couple Type

### Unweighted Results

Same-sex and different-sex couples show distinct patterns:

- Same-sex couples are much more likely to report **online meeting contexts**
- Different-sex couples are more likely to report **work-based meeting**
- Social contexts are broadly similar across groups

| Group                 | Social (Unw) | Social (W) | Work (Unw) | Work (W) | Online (Unw) | Online (W) |
|----------------------|--------------|------------|------------|----------|--------------|------------|
| Different-sex couples | 55.6%        | 54.6%      | 24.0%      | 23.4%    | 8.6%         | 9.6%       |
| Same-sex couples      | 52.6%        | 50.3%      | 15.3%      | 15.6%    | 28.2%        | 30.2%      |

Weighted and unweighted results are highly consistent, with only minor differences in proportions.

### Weighted Results (Population-Adjusted)

| Group                 | Social | Work   | Online |
| --------------------- | ------ | ------ | ------ |
| Different-sex couples | 54.60% | 23.44% | 9.61%  |
| Same-sex couples      | 50.35% | 15.60% | 30.22% |


These results confirm that same-sex couples are approximately three times more likely to report online meeting contexts than different-sex couples.

The consistency between weighted and unweighted estimates indicates that these differences are not driven by sampling bias.


## 5. Relationship Stability by Meeting Context

### Wave 2 (More Reliable)

- Work-based relationships show the highest stability (~95%)
- Social relationships follow closely (~94–95%)
- Online relationships show lower stability (~89%)

### Wave 3 (Observed Status)

A similar pattern is observed, although interpretation is more cautious due to survey structure and attrition.

Online-initiated relationships consistently exhibit lower observed stability compared to work-based and socially initiated relationships.


## 6. Regression Analysis

To formally test whether meeting context predicts long-term relationship outcomes, logistic regression models were estimated.

### Model Structure
- Outcome (Y): Relationship status at Wave 3 (still together vs separated)
- Main predictor (X): Meeting context (cluster)
- Controls (Z):
    - Wave 2 relationship status
    - Marital status
    - Same-sex indicator
    - Partner education

![Odds ratios from logistic regression model](logistic_regression_results.png)

*Figure 6.1: Odds ratios from logistic regression models predicting relationship survival at Wave 3.*

The results indicate that meeting context is associated with relationship stability. Compared to online-initiated relationships, both socially and work-initiated relationships show higher odds of remaining together.

However, once controlling for Wave 2 relationship status, the magnitude of these effects is reduced, suggesting that early relationship survival is a strong predictor of long-term outcomes.

Other control variables, such as marital status, show expected positive associations with stability, while same-sex status is not statistically significant.

Overall, the findings suggest that meeting context has an initial association with relationship outcomes, but much of this effect operates through earlier relationship survival.

### Key Results (Adjusted Model)

- Wave 2 relationship status is the strongest predictor of long-term survival (OR ≈ 4.77, p < 0.001)
- Marriage is associated with higher odds of remaining together (OR ≈ 1.63, p < 0.05)
- Work-based relationships show higher odds compared to online (OR ≈ 1.84), but this effect is only marginally significant
- Differences between social and online meeting contexts are not statistically significant
- Same-sex status is not a significant predictor
- Partner education is not significantly associated with relationship outcomes

### Interpretation

The results indicate that while meeting context initially appears to be associated with relationship outcomes, much of this relationship is explained by prior relationship survival. 

After controlling for Wave 2 status, differences between meeting contexts largely diminish. In particular, the advantage observed for work-based relationships weakens and is no longer statistically significant.

This suggests that early relationship stability is the primary driver of long-term outcomes, with meeting context playing a more limited role once this factor is taken into account.

## 7. Model Performance

Accuracy: ~96.8% (not informative due to imbalance)
ROC AUC: ~0.67 (moderate predictive power)

Due to the high proportion of ongoing relationships, accuracy is inflated and not an informative metric in this context. ROC AUC provides a more appropriate evaluation, indicating that the model has moderate ability to distinguish between outcomes.

---

## 8. Robustness Checks

To assess whether the results are sensitive to sampling differences, survey weights were applied to the descriptive analyses.

![Weighted cluster composition and relationship stability across waves](weighted_cluster_stability.png)
*Figure 8.1: Weighted distribution of meeting contexts and relationship stability across Wave 2 and Wave 3.*

The weighted estimates show:

- Minimal changes in proportions
- No change in overall patterns

This indicates that findings are **robust to sampling differences**.

---

## 9. Limitations

Several limitations should be considered:

1. Multiple meeting contexts
Respondents could select multiple meeting pathways, so the exact first meeting context cannot be identified.

2. Non-mutually exclusive categories
Social, work, and online categories may overlap, meaning clusters reflect dominant patterns rather than exclusive groups.

3. Panel attrition
Later waves include only respondents who remained in the survey, which may bias observed relationship outcomes.

4. Wave 3 measurement
Relationship status at Wave 3 is based on reported breakups and may not fully capture all outcomes.

5. Imbalanced outcome
Breakups are relatively rare, limiting predictive performance.

---
## 10. Conclusion

This analysis shows that:

- Same-sex and different-sex couples differ most strongly in how they meet, particularly in online contexts
- Online-initiated relationships exhibit lower observed stability than work-based relationships
- However, once prior relationship survival and demographics are considered, same-sex status itself does not significantly predict outcomes

### Final Insight

Differences in relationship outcomes appear to be associated with meeting context rather than couple type. However, this association weakens substantially after accounting for prior relationship stability.

Overall, the findings suggest that early relationship conditions—particularly whether a couple remains together in the short term—are the primary drivers of long-term outcomes, while initial meeting context plays a more limited role.