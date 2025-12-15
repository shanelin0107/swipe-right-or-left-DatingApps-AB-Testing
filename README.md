# Swipe Right or Left: Evaluating the Effectiveness of Interactive Introduction Formats on a Dating App

Authors: Yu-Hsiang Wang, Zhe-Yu Lin, Ming-Hua Tsai, Ching-Hsuan Lin  
Date: 2025

## Summary
This project evaluates whether adding a short interactive multiple-choice question to a dating profile ("interactive self-introduction") increases users' right-swipe rates. We ran an online experiment with simulated profiles and measured swipe behavior across a treatment group (interactive question added) and a control group (standard written self-introduction).

## Research Question
Does adding interactive questions to a profile enhance swipe rates on a dating app?

- Null hypothesis (H0): Including an interactive question has no effect on the swipe rate.
- Alternative hypothesis (Ha): Including an interactive question affects the swipe rate.

## Experimental Design
- Unit of randomization: user-level random assignment.
- Sample: 83 participants (37 treatment, 46 control).
- Procedure: Each participant saw 10 simulated profiles of their preferred gender. Each profile contained a photo, age, name, and "About Me". Treatment profiles included an additional one-question multiple-choice interaction.
- Outcome variable: swipe rate = (number of likes across 10 profiles) / 10.
- Covariates collected: age_group, interest_in (preferred gender), prior experience with dating apps, time_spent.

## Data Collection & Survey Design
- Survey platform: Boston University Qualtrics.
- Recruitment: MSBA students via email and target participants aged 21–35 via social media.
- Privacy: Anonymous questionnaire (no names or emails collected).
- Links:
  - Figma prototype: [Figma output](https://reurl.cc/L5YL9e)
  - Analysis (Google Colab): [Colab notebook](https://reurl.cc/EgkLOv)
  - Profile image source: [Pexels search results](https://www.pexels.com/search/)
  - Original survey: [Qualtrics survey](https://bostonu.qualtrics.com/jfe/form/SV_3yfusZykmvMprSu)

## Data Processing
- Cleaned survey exports to extract relevant columns (treatment assignment, "interested in", swipe responses).
- Converted text responses ("like"/"dislike") into binary labels and calculated per-user swipe rates.
- Constructed treatment and control datasets for analysis.

## Descriptive Statistics & EDA
- Total respondents: 83 (46 control, 37 treatment).
- Most participants aged 23–27.
- More participants reported interest in males (47) than females (36).
- 44 participants had prior dating-app experience; 39 did not.

## Key Results
- Average Treatment Effect (ATE): 0.02 (treatment — control), standard deviation: 0.21.
- Cohen's d: 0.09 (negligible effect).
- Statistical power: ~0.07 (very low); estimated samples needed per group for 80% power ≈ 1,789 (total ≈ 3,578).
- Z-test p-value: 0.32 (no significant difference).
- Two-sample t-test statistic: ~0.43 (p-value not significant).
- Regression results:
  - Treatment coefficient: positive (~0.024) but not statistically significant.
  - `interest_in` (preferred gender) coefficient: ~0.166 (statistically significant) — users interested in females had higher swipe rates.
  - Interaction between treatment and `interest_in`: not significant.
- Conclusion from analysis: Cannot reject the null hypothesis. The interactive question produced a small, non-significant upward trend in swipe rates but no conclusive effect in this sample.

## Limitations
- Small sample size — insufficient power to detect small effects.
- Sample bias — participants mainly from BU MSBA and social networks; limited representativeness.
- Limited realism — survey-based UI simulation cannot fully replicate in-app behavior and feedback loops.
- Limited profile diversity — constrained representation of ethnicities and personalities.
- Measurement/response bias — participants might respond differently in a survey than in a live app.
- Profile information was intentionally minimal (photo, age, short intro) which may omit important matching signals used in real apps.

## Recommendations & Next Steps
To get more conclusive evidence and improve external validity:
1. Increase sample size substantially to reach adequate power (target N in the thousands based on current effect size) or run a new power calculation for a hypothesized minimum effect size you wish to detect.
2. Recruit a more demographically diverse participant pool (age, ethnicity, geography).
3. Improve ecological validity:
   - Implement the experiment within a working prototype or partner app to capture real behavioral data (clicks, dwell time, messaging).
   - Use tools that record in-app interactions and timelines rather than self-reported survey choices.
4. Expand profile richness (additional fields and signals) and increase profile diversity.
5. Pre-register study design, hypotheses, and analysis plan to avoid p-hacking and reduce analytic flexibility.
6. Consider stratified or targeted experiments to explore heterogeneous treatment effects (e.g., by gender, age cohort, or prior app experience).
7. Explore additional interactive formats and question types (e.g., image-based prompts, multi-step interactions, gamified tasks).

## Reproducibility
- The primary analysis and code are available in the provided Google Colab link: [Colab notebook](https://reurl.cc/EgkLOv).
- Figma prototype and assets: [Figma output](https://reurl.cc/L5YL9e).
- Raw images sourced from Pexels: [Pexels](https://www.pexels.com/search/).
- If you would like, we can provide:
  - A cleaned CSV of the survey responses.
  - Jupyter/Colab cells for data cleaning, EDA plots, and regression models exported as scripts.
  - A pre-registered analysis plan template.

## Appendix
- Figma: https://reurl.cc/L5YL9e
- Google Colab (analysis): https://reurl.cc/EgkLOv
- Profile images (source): https://www.pexels.com/search/
- Survey (Qualtrics): https://bostonu.qualtrics.com/jfe/form/SV_3yfusZykmvMprSu
