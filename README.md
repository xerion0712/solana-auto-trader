# Solana Auto Trader (Beta)

The **Solana Auto Trader** is a trading bot that automates buying and selling tokens on the Solana blockchain.
It operates based on user-defined strategies and parameters, enabling efficient and rule-based trading execution.

This tool can track market conditions in real-time (such as liquidity pool status, mint authority, burn events, etc.) and trigger trades when matching conditions are met.

---

## 🚀 Setup

1. **Create Wallet**

   * Generate a new Solana wallet.
   * Fund it with some SOL.
   * Swap some SOL to USDC or WSOL (depending on your configuration).

2. **Configure the Bot**

   * Copy `.env.copy` to `.env`.
   * Update values inside `.env`.

3. **Install Dependencies**

   ```bash
   npm install
   ```

4. **Run the Bot**

   ```bash
   npm run start
   ```

   If configured correctly, you’ll see logs confirming execution.

---

## ⚙️ Configuration

### Wallet

* **PRIVATE\_KEY** – Private key of your Solana wallet.

### Connection

* **RPC\_ENDPOINT** – HTTPS RPC endpoint (Helius, Quicknode, etc.).
* **RPC\_WEBSOCKET\_ENDPOINT** – WebSocket endpoint for live updates.
* **COMMITMENT\_LEVEL** – Transaction commitment level (`processed`, `confirmed`, or `finalized`).

### Bot

* **LOG\_LEVEL** – Logging verbosity (`info`, `debug`, `trace`).
* **ONE\_TOKEN\_AT\_A\_TIME** – Restrict trading to one token at a time.
* **COMPUTE\_UNIT\_LIMIT / PRICE** – Define compute unit usage.
* **TRANSACTION\_EXECUTOR** – Choose execution method: `warp` or `jito`.
* **CUSTOM\_FEE** – Fee override when using `warp`/`jito`.

### Buy Settings

* **QUOTE\_MINT** – Base token (`USDC` or `WSOL`).
* **QUOTE\_AMOUNT** – Amount per buy order.
* **AUTO\_BUY\_DELAY** – Delay before execution.
* **MAX\_BUY\_RETRIES** – Retry attempts.
* **BUY\_SLIPPAGE** – Allowed slippage %.

### Sell Settings

* **AUTO\_SELL** – Enable or disable auto-sell.
* **MAX\_SELL\_RETRIES** – Retry attempts for selling.
* **PRICE\_CHECK\_INTERVAL** – Interval for take profit / stop loss checks.
* **PRICE\_CHECK\_DURATION** – Maximum duration before forced exit.
* **TAKE\_PROFIT** – % profit target.
* **STOP\_LOSS** – % stop loss threshold.
* **SELL\_SLIPPAGE** – Allowed slippage %.

### Snipe List

* **USE\_SNIPE\_LIST** – Enable sniping from `snipe-list.txt`.
* **SNIPE\_LIST\_REFRESH\_INTERVAL** – Refresh rate for snipe list.

### Filters

* **FILTER\_CHECK\_INTERVAL / DURATION** – Timing for filter checks.
* **CHECK\_IF\_MUTABLE** – Only buy tokens with immutable metadata.
* **CHECK\_IF\_SOCIALS** – Require tokens with socials.
* **CHECK\_IF\_MINT\_IS\_RENOUNCED** – Only buy renounced mint tokens.
* **CHECK\_IF\_FREEZABLE** – Require non-freezable tokens.
* **CHECK\_IF\_BURNED** – Require burned LP tokens.
* **MIN\_POOL\_SIZE / MAX\_POOL\_SIZE** – Pool size constraints.

---

## ⚡ Warp Transactions (Beta)

If normal transactions fail frequently or are too slow, you can enable **Warp execution**.

* Warp does **not** transmit your private key.
* Fees are shared between Warp developers and infrastructure providers.

---

## 🛠️ Common Issues

* **Unsupported RPC node**

  * Error: `"The RPC call or parameters have been disabled."`
  * Solution: Use a different RPC (Helius, Quicknode).

* **No token account**

  * Error: `"No SOL token account found in wallet."`
  * Solution: Swap SOL → WSOL/USDC so the account is created.

---

## 🤝 Support

* Tips: `7gm6BPQrSBaTAYaJheuRevBNXcmKsgbkfBCVSjBnt9aP`
* For custom features or private help, contact the admin team on Discord.

---

## ⚠️ Disclaimer

The **Solana Auto Trader** is provided for **educational purposes only**.
Cryptocurrency trading is risky, and use of this bot is entirely at your own risk.
The maintainers are **not responsible** for financial losses incurred.
