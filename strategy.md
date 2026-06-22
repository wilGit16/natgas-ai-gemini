📊 Algorithm Master Blueprint: NatGas v12.11

🛡️ Global Operations (Applies to all strategies)

Trading Hours: 08:00 to 19:00 (Server Time). This completely avoids the low-volume Asian session "whipsaw" and stops the bot from paying predatory overnight broker spreads.

Risk Profile: * Take Profit: 150 Points

Stop Loss: 150 Points

Trailing Stop: Activates at +60 points of profit, trailing 45 points behind current price.

🟢 STRATEGY 1: The Trend Rider (M15 / M5 MTF)

The Concept: This is your heavy, classic momentum bot. It identifies a strong, established 15-minute trend, waits for a minor localized dip, verifies that the 5-minute micro-momentum agrees, and jumps in using the Stochastic oscillator.

Step-by-Step Logic:

The M15 Macro Trend: The M15 EMA 20 must be correctly aligned with the M15 EMA 50 (EMA 20 > EMA 50 for a Buy).

The Trend Strength (Spread): The physical gap between the M15 EMA 20 and M15 EMA 50 must be at least 20 points wide (0.0020). It refuses to trade weak, flat trends.

The M5 MTF Momentum Guard: It looks down at the 5-minute chart's closed candle. The M5 EMA 9 must be > M5 EMA 20. (Locked to the closed candle to prevent live tick-flicker).

The Baseline Guard: The live price (Bid) must be strictly on the correct side of the M15 EMA 50.

The RSI Filter: The M15 RSI must be > 50 for a Buy, ensuring overall bullish pressure.

The Pocket (Proximity): The current price must pull back into the "pocket." It must be within 5 points of the EMA 20, OR within 10 points of the EMA 50.

The Execution (Stochastic): Both Stochastic lines (K and D) must be between 20 and 80. The fast K line must be above the slow D line with a gap of at least 5.0 points to prove momentum is accelerating.

🟡 STRATEGY 2: M5 Tight Compression Pullback

The Concept: This strategy hunts for explosive coiled energy on the 5-minute chart. It looks for a market that is highly "compressed" (EMAs tightly squeezed together) but pushing in the direction of the daily institutional trend, executing only on surgically precise 5-point pullbacks.

Step-by-Step Logic (Upgraded in v12.11):

The Institutional Filter: The 15-minute EMA 50 must be aligned correctly with the massive 15-minute EMA 200.

The M5 Squeeze: The distance between the M5 EMA 20 and M5 EMA 50 must be 15 points or less. The market must be tightly coiled.

The Crossover Anchor: It scans the last 100 candles to find where the M5 EMA 20 originally crossed the EMA 50. The current EMA 20 must be higher than that anchor price, proving the squeeze is succeeding upward, not failing.

The Baseline Guard: The live price (Bid) must be strictly above the M5 EMA 50.

The Surgical Pullback (v12.11 update): * For a BUY: It calculates the distance from the Ask price to the M5 EMA 20. This distance must be 5 points or less.

For a SELL: It calculates the distance from the Bid price to the M5 EMA 20. This distance must be 5 points or less.

(This demands that the actual price you pay is physically kissing the EMA line).

The Execution (Stochastic Cross): The Stochastic must physically cross on the closed candle. The fast K line must cross the slow D line with a gap of at least 5.0 points, and the lines cannot be overbought/oversold (>80 or <20).

🔴 STRATEGY 3: M15 Elastic Mean Reversion

The Concept: This is the "Snapback Sniper." It looks for moments where panic selling or buying pushes the price so far outside the mathematical norm that it acts like a stretched rubber band. It strikes instantly the moment the price snaps back inside.

Step-by-Step Logic:

The M15 Trend: The standard M15 EMA 20 must be correctly aligned with the M15 EMA 50 (EMA 20 > EMA 50 for a Buy).

The Statistical Extreme (Bollinger Bands): It uses a 20-period Bollinger Band set to an extreme 2.5 Standard Deviation.

The Snapback Trigger: * For a Buy: It looks at the last fully closed 15-minute candle. The Low of that candle must have pierced entirely outside the Lower 2.5 Bollinger Band, but the Close of that candle must have snapped back up to finish inside the band.

For a Sell: The High of the closed candle pierced outside the Upper 2.5 Bollinger Band, but the Close fell back down inside the band.

The Execution: If the snapback condition is met, it executes immediately on the opening of the next candle. It uses no other filters, allowing it to catch the fastest part of the rubber-band reaction.
