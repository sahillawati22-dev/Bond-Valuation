# Bond-Valuation

A Python toolkit that prices fixed-coupon bonds and computes their yield and
interest-rate-risk measures. Built to connect **CFA Level I — Quantitative
Methods (Time Value of Money)** with runnable code, plus a preview of Fixed
Income (duration and convexity).

## Features

- **Bond price** — present value of all coupon and principal cash flows.
- **Yield to maturity (YTM)** — solved from a given price by root-finding.
- **Current yield** and **accrued interest** (clean vs dirty price).
- **Duration & convexity** — Macaulay and modified duration, convexity, DV01.
- **Price-change estimate** — approximate a new price for a yield move using
  duration + convexity.
- **Price-yield chart** — shows the convex price curve vs the duration tangent.
- **Bond comparison** — price several bonds side by side in a table.

## How to run

### Option A — Google Colab (no install)

Click the **Open in Colab** badge above, then run the cells top to bottom
(Shift + Enter). Everything it needs is pre-installed in Colab.

### Option B — Run locally

```bash
pip install numpy pandas matplotlib scipy
python bond_toolkit.py
```

## Usage

```python
# price a bond
bond_price(face=1000, coupon_rate=0.05, years=10, ytm=0.06)   # 925.61

# solve the yield from a price
ytm(price=925.61, face=1000, coupon_rate=0.05, years=10)      # 0.06

# full report: price, current yield, duration, convexity, DV01
summary(1000, 0.05, 10, ytm_=0.06)
```

## Concept → code map

| CFA concept | Function |
|---|---|
| Price = PV of cash flows | `bond_price` |
| Solve YTM from price | `ytm` |
| Current yield | `current_yield` |
| Accrued interest (clean vs dirty) | `accrued_interest` |
| Macaulay / modified duration, convexity, DV01 | `durations` |
| Duration + convexity price estimate | `est_price_change` |
| Price-yield relationship | `plot_price_yield` |

## Example output
