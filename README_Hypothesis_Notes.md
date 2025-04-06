# 📃 Hypothesis Testing Concepts Explained

This document explains the statistical concepts behind code used in hypothesis testing, including Z-tests, t-tests, Chi-Square, and F-tests.

---

## 👨‍🔬 Z-Test (Standard Normal Test)

### When to Use:
- Population standard deviation is **known**
- Sample size is **large** (n > 30)
- Testing **means** or **proportions**

### Key Concepts:
- Converts raw scores into **Z-scores**
- Used to calculate **p-values** from the **standard normal distribution**
- Common in A/B testing, quality control

### Code Snippets:
```python
st.norm.cdf(z)        # Lower-tail p-value
st.norm.sf(z)         # Upper-tail p-value
st.norm.sf(abs(z)) * 2  # Two-tailed p-value
st.norm.ppf(1 - alpha)  # Z critical value
```

---

## 🌟 t-Test (Student's t-distribution)

### When to Use:
- Population standard deviation is **unknown**
- Sample size is **small** (n < 30)

### Key Concepts:
- Accounts for more uncertainty than Z-test
- Used for **sample vs. population mean** or **comparing two samples**
- More flexible for real-world data

### Code Snippets:
```python
st.t.sf(t, df)           # One-tail p-value
st.t.sf(abs(t), df) * 2  # Two-tail p-value
st.t.ppf(1 - alpha, df)  # T critical value
```

---

## 📊 Chi-Square Test

### When to Use:
- **Goodness-of-fit**: Does observed match expected distribution?
- **Independence**: Are two categorical variables independent?
- **Variance**: Is sample variance significantly different from a target?

### Key Concepts:
- Measures the **distance** between observed and expected values
- Often used in **categorical data analysis**

### Code Snippets:
```python
st.chi2.sf(chi2_stat, df)   # Upper-tail p-value
st.chi2.cdf(chi2_stat, df)  # Lower-tail p-value
st.chi2.ppf(1 - alpha, df)  # Chi-square critical value
```

---

## 📊 F-Test (F-distribution)

### When to Use:
- Compare **variances** of two samples
- Used in **ANOVA** or **regression significance**

### Key Concepts:
- Tests the **ratio of variances**
- Right-skewed distribution

### Code Snippets:
```python
st.f.ppf(1 - alpha, dfn, dfd)  # F critical value
st.f.cdf(F_value, dfn, dfd)    # F p-value
```

---

## 🔢 Pooled Variance (Equal Variance t-test)

### Use:
- For **equal variance** two-sample t-tests

---

## 🧍 Welch’s Degrees of Freedom (Unequal Variance)

### Use:
- For **Welch’s t-test** (no equal variance assumption)

---

## 📉 General Concepts

| Term      | Meaning |
|-----------|---------|
| **p-value** | Probability of observing the data assuming the null hypothesis is true |
| **α (alpha)** | Significance level, usually 0.05 |
| **Critical Value** | Value that defines the rejection region |
| **One-tailed test** | Tests if a value is significantly **greater than** or **less than** expected |
| **Two-tailed test** | Tests if a value is significantly **different** (in either direction) |
