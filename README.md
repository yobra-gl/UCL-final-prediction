 🏆 UEFA Champions League Final 2026 — Winner Predictor

> **PSG vs Arsenal | Budapest, May 30 2026**  
> A machine learning project to predict the winner of the 2025/26 UEFA Champions League Final using a Poisson Goal Model and Logistic Regression trained on historical UCL Finals data.

---

## 📌 Pre-Match Prediction

| Model | PSG Win % | Arsenal Win % |
|---|---|---|
| Poisson Goal Model | TBD | TBD |
| ML (Logistic Regression) | TBD | TBD |
| **Ensemble (Final Prediction)** | **TBD** | **TBD** |

> **🔮 Predicted Winner: TBD**  
> *(Run the notebook to generate predictions — fill in results after May 30)*

---

## 📖 Project Overview

This project builds a machine learning pipeline that predicts the winner of the 2026 UCL Final. It combines two complementary approaches:

- **Poisson Goal Model** — estimates the probability of every possible scoreline based on each team's attack and defensive strength throughout the tournament. This is the same class of model used by professional bookmakers.
- **Logistic Regression** — trained on historical UCL Final data from 2000–2025, using features like goals scored, defending champion status, and coach experience.

The two models are then **ensembled** to produce a final win probability for each team.

---

## 🗂️ Project Structure

```
ucl-final-predictor/
├── ucl_final_predictor.ipynb   ← Main notebook (start here)
├── README.md                   ← You are here
├── requirements.txt            ← Python dependencies
└── outputs/
    ├── eda_features.png        ← EDA charts
    ├── scoreline_matrix.png    ← Poisson heatmap
    ├── feature_importance.png  ← Model coefficients
    └── final_prediction.png    ← Final probability chart
```

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/yobra-gl/ucl-final-predictor.git
cd ucl-final-predictor
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Launch the notebook
```bash
jupyter notebook ucl_final_predictor.ipynb
```

Run all cells from top to bottom — the notebook is self-contained and requires no external data downloads.

---

## 📦 Requirements

```
pandas
numpy
scipy
scikit-learn
matplotlib
seaborn
xgboost
jupyter
```

Install all at once:
```bash
pip install pandas numpy scipy scikit-learn matplotlib seaborn xgboost jupyter
```

---

## 📊 Features Used

| Feature | Description |
|---|---|
| `goals_scored` | Total goals scored in the UCL tournament |
| `goals_conceded` | Total goals conceded in the UCL tournament |
| `goal_difference` | goals_scored − goals_conceded |
| `is_defending_champion` | 1 if the team is the reigning UCL champion |
| `is_first_ucl_final` | 1 if this is the team's first UCL final |
| `domestic_league_position` | Final league position in their domestic league |
| `coach_ucl_wins` | Number of UCL titles the head coach has won |

---

## 🧠 Methodology

### Poisson Goal Model
Goals in football follow a Poisson distribution. For each team we compute an **expected goals (λ)** value:

```
λ = attack_strength × opponent_defensive_weakness × avg_ucl_goals_per_game
```

We then calculate the probability of every scoreline from 0–0 up to 7–7, and sum them to get overall win/draw/loss probabilities. Draws are split equally between the two teams (to account for extra time and penalties).

### Logistic Regression
Trained on 52 data points (26 UCL finals × 2 teams per final, 2000–2025). Validated using **Leave-One-Out Cross-Validation** — the best strategy for small datasets. Features are standardised with `StandardScaler` before training.

### Ensemble
Final probabilities are a 50/50 weighted average of the Poisson model and ML model outputs. The weights can be adjusted in the notebook.

---

## 📈 Key Findings from EDA

- Defending champions win the final at a notably higher rate than non-defending champions
- Higher goal difference throughout the tournament is positively correlated with winning the final
- First-time finalists historically underperform relative to experienced finalists
- Coach UCL experience (prior wins) is one of the strongest individual predictors

---

## ✅ Post-Match Result

> **To be updated after May 30, 2026**

| | Predicted | Actual |
|---|---|---|
| Winner | TBD | TBD |
| Score | — | TBD |
| Extra Time / Penalties | — | TBD |
| Prediction Correct | — | TBD |
| Brier Score | — | TBD |

---

## 🔮 Future Improvements

- Add **xG (expected goals)** data from understat.com for more accurate λ estimates
- Incorporate **player availability** — suspensions and injuries before the final
- Use **betting odds** as an additional feature and benchmark
- Run a **Monte Carlo simulation** (100,000 iterations) for smoother probability estimates
- Train **XGBoost** on all UCL knockout matches for a larger dataset
- Implement a **club ELO rating system** for a richer team strength measure

---

## 📚 Data Sources

- [UEFA.com](https://www.uefa.com/uefachampionsleague/) — official tournament stats
- [FBref.com](https://fbref.com) — detailed match and player statistics
- [Wikipedia](https://en.wikipedia.org/wiki/UEFA_Champions_League) — historical finals results

---

## 👤 Author

**Brian Mburu**  
[GitHub](https://github.com/yobra-gl) · [LinkedIn](https://www.linkedin.com/in/brian-mburu-1787142a5)

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

*Built with Python 🐍 | Data from UEFA & FBref | UCL Final — Budapest, May 30 2026*
