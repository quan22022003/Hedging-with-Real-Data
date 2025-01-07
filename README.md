
# Hedging Portfolios of Options with Real Data

## Overview

This repository contains the implementation and analysis for the **Hedging Assignment** from the course *TU-E2211 - Financial Risk Management with Derivatives 1* at Aalto University. The project evaluates **delta** and **delta-vega hedging strategies** using real-world data from S&P 500 options to mitigate price and volatility risks. 

Key insights include:
- Comparison of hedging effectiveness under varying re-hedging frequencies.
- Impact of transaction costs on hedging performance.
- Evaluation of single-option and portfolio hedging strategies.

---

## Directory Structure

```
├── data
│   ├── options_price       # Historical options price data
│   │   ├── call            # Call options data
│   │   └── put             # Put options data
│   ├── resources           # Supporting resources and references
│   ├── treasury_rates      # Daily treasury yield rates
│   └── underlying_price    # S&P 500 underlying price data
```

---

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-repo-name>.git
   ```
2. Install the required dependencies:
   ```bash
   R
   # Install required R libraries:
   install.packages(c("RQuantLib", "dplyr", "stringr", "purrr", "fOptions", "ggplot2", "ggpubr"))
   ```

---

## Usage

### Data Preprocessing
- Missing option prices are interpolated using average BID/ASK prices.
- Risk-free rates are processed from treasury bills.
- Features like implied volatility, delta, and vega are calculated using the **Black-Scholes model**.

### Running the Analysis
1. **Single Option Hedging**
   - Delta and delta-vega hedging for individual options.
   - Adjust re-hedging frequency and transaction cost rate.

2. **Portfolio Hedging**
   - Analyze portfolios with a strangle position (call and put options).
   - Comparison of hedging strategies under various market conditions.

Run the provided scripts in R to process data, calculate hedging metrics, and generate visualizations.

---

## Key Functions

- `calculate_implied_volatility`: Calculates implied volatility using Black-Scholes pricing.
- `calculate_greeks`: Computes option Greeks (Delta, Vega).
- `delta_hedging`: Implements delta hedging for single options or portfolios.
- `delta_vega_hedging`: Implements delta-vega hedging for single options or portfolios.

---

## Results

- **Delta Hedging:** Achieves reasonable risk mitigation but is sensitive to high-frequency re-hedging and transaction costs.
- **Delta-Vega Hedging:** Outperforms delta hedging with greater resilience to volatility and transaction costs.
- Comparative results show reduced error spikes and higher robustness in delta-vega hedging.

---

## References

- Data Sources:
  - S&P 500 options: Refinitiv
  - Underlying prices: Yahoo Finance
  - Treasury rates: U.S. Department of the Treasury

For detailed findings, refer to the report in `Hedging_Assignment.pdf`.

---

## Authors

- **Quan Tran**  
  Email: [quan.tran@aalto.fi](mailto:quan.tran@aalto.fi)
