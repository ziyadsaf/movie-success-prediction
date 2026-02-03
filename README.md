# Movie Success Prediction and Analysis Using TMDb Data

A machine learning project that predicts movie revenue using regression techniques, leveraging the TMDB 5000 Movies dataset from Kaggle. This is my first full data science project, combining data cleaning, exploratory data analysis (EDA), feature engineering, and regression modelling.

---

## Objectives

- Understand what factors influence movie revenue
- Clean and preprocess real-world movie data
- Build regression models to predict revenue
- Derive actionable insights through data visualisation

---

## Dataset

**Source**: [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) from Kaggle

**Files**:
- `tmdb_5000_movies.csv` - Movie metadata (4,803 movies, 20 features)
- `tmdb_5000_credits.csv` - Cast and crew information

**Key Features**:
| Feature | Description |
|---------|-------------|
| `budget` | Production budget in USD |
| `revenue` | Box office revenue in USD |
| `popularity` | TMDb popularity score |
| `vote_average` | Average user rating |
| `vote_count` | Number of user votes |
| `genres` | Movie genres (JSON format) |
| `production_companies` | Production companies involved |
| `release_date` | Release date |
| `runtime` | Movie duration in minutes |

---

## Tools and Libraries Used

- **Python 3.x**
- **pandas** - Data manipulation
- **numpy** - Numerical computations
- **matplotlib** & **seaborn** - Visualization
- **scikit-learn** - Machine learning (Linear Regression, Ridge, Decision Tree, Random Forest)
- **Jupyter Notebook**

---

## Project Steps

### 1. Data Cleaning
- Removed null values, duplicates, and inconsistent formats
- Standardised categorical features such as genres and release dates
- Dropped unnecessary columns (homepage, id, original_title, overview, tagline)
- Parsed JSON columns (genres, production_companies, production_countries)

### 2. Exploratory Data Analysis (EDA)
- Explored budget vs revenue relationships
- Visualised trends by genre, release season, and popularity
- Distribution analysis of numerical features
- Correlation analysis using heatmaps
- Box plots for categorical relationships

### 3. Feature Engineering
- **Log Transformations**: Applied to skewed features (budget, revenue, popularity, vote_count)
- **Derived Features**:
  - `profit` = revenue / budget
  - `popularity_per_vote` = popularity / vote_count
- **Categorical Extraction**:
  - Primary genre from multi-genre entries
  - Primary country from production countries
  - Top 3 production companies per movie
- **Binning**: Quantile-based binning for categorical analysis

### 4. Model Building and Evaluation
- Multiple Linear Regression (MLR) using log-transformed features
- Features: log_budget, log_popularity, log_vote_count
- Target: log_revenue
- Used metrics such as RMSE and R² score to assess performance

---

## Key Findings

### Correlations Discovered
| Feature Pair | Correlation | Interpretation |
|--------------|-------------|----------------|
| Budget & Revenue | 0.70 | Strong positive - higher budgets yield higher revenue |
| Popularity & Vote Count | 0.95 | Very strong - popular movies get more votes |
| Revenue & Vote Count | 0.69 | Strong positive relationship |
| Budget & Popularity | 0.60 | Moderate positive relationship |

### Categorical Analysis
- **Genre**: Action and Animation show distinct revenue patterns, but significant overlap exists
- **Language**: English dominates (highly skewed), not a strong predictor
- **Country**: US-based films dominate, country alone not predictive
- **Production Companies**: High overlap between companies, not a strong standalone predictor

### Initial Model Results
- **Algorithm**: Multiple Linear Regression
- **Test RMSE**: 1.37 (on log scale)
- **Test R² Score**: 0.31 (31% variance explained)

---

## Files

- [Jupyter Notebook](https://github.com/ziyadsaf/movie-success-prediction/blob/main/movie_prediction_project.ipynb)

---

## Next Steps

- [ ] Complete handling of keywords and spoken_languages columns
- [ ] Hyperparameter tuning
- [ ] Explore polynomial regression for non-linear relationships
- [ ] Test ensemble methods (Random Forest, Gradient Boosting, XGBoost)
- [ ] Improve feature selection and engineering
- [ ] Explore dashboard deployment using Dash

---

## Contact

Feel free to connect on [LinkedIn](https://www.linkedin.com/in/ziyad-safouane/) or visit my portfolio at [ziyadsaf.github.io](https://ziyadsaf.github.io).
