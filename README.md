# Antminer Monitor — ASIC Mining Dashboard

[![Follow on Twitter](https://img.shields.io/twitter/follow/AntminerMonitor.svg?style=social)][twitter]
![Python](https://img.shields.io/badge/python-3.x-blue.svg)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Mac%20%7C%20Linux-lightgrey.svg)

## Overview

A lightweight, self-hosted Python dashboard for monitoring Antminer ASIC mining devices. Track hashrates, temperatures, fan speeds, and hardware status across your entire mining operation from a single interface.

## Key Features

| Feature | Description |
|---------|-------------|
| 🔧 Multi-Device Support | Monitor unlimited miners from one dashboard |
| 📊 Real-Time Metrics | Hashrate, temperature, fan speed, chip status |
| ⚠️ Error Tracking | In-app notifications and file logging |
| 📈 Aggregated Stats | Total hashrate grouped by model |
| 🔐 Secure Access | Password-protected web interface |

### Supported Models

A3, B3, D3, E3, L3, L3+, L3++, R4, S7, S9, S11, S17, S17 Pro, S17+, T9, T9+, T17, V9, X3, Z9 mini, Z11

## Dashboard Preview

![Dashboard Screenshot](/antminermonitor/static/images/screenshot_v0.5.0.png?raw=true "Dashboard v0.5.0")

## System Requirements

| Component | Requirement |
|-----------|-------------|
| Python | Version 3.x |
| OS | Windows, Mac, or Linux |

> **Windows Users:** During Python installation, ensure you check `Add python.exe to Path` in the `Customize Python` step.

## Installation Guide

### Step 1: Download

Get the latest release from the [Releases Page](https://github.com/teco8xk/antminer-monitor/releases) or download the [master branch](https://github.com/teco8xk/antminer-monitor/archive/master.zip).

### Step 2: Extract & Navigate

Unzip and open terminal in the extracted folder:
```sh
cd C:\Users\foo\Downloads\antminer-monitor-master
```

### Step 3: Mac Users Only

Install `pip` using one of these methods:

**Option A:** Download [get-pip.py](https://bootstrap.pypa.io/get-pip.py) and run:
```sh
sudo python get_pip.py
```

**Option B:** Use easy_install:
```sh
sudo easy_install pip
```

### Step 4: Install Dependencies

```sh
python -m pip install -r requirements.txt
python manage.py create-db
```
*(Mac users: prefix commands with `sudo`)*

### Step 5: Create Admin Account

```sh
python manage.py create-admin
```

Default credentials: `admin` / `antminermonitor` (change via settings menu)

## Running the Dashboard

```sh
python manage.py run -h 0.0.0.0 -p 5000
```

Access the dashboard:
- **Local:** `http://localhost:5000`
- **Network:** `http://<server-ip>:5000`

> **Tip:** Configure host and port in `.flaskenv` for persistent settings.

## Configuration

### Development vs Production Mode

Default mode is development with auto-reload and debugging. For production:

Edit `.flaskenv`:
```
FLASK_ENV="production"
```

### Running as a Service (systemd)

```sh
# Copy service file
sudo cp antminermonitor.service /etc/systemd/system/

# Reload daemon
sudo systemctl daemon-reload

# Start and enable service
sudo systemctl start antminermonitor
sudo systemctl enable antminermonitor
```

## Support the Project

| Currency | Address |
|----------|---------|
| BTC | `1HYCBovF6mqqKMyG4m2DQxXpdKmogK4Wuw` |
| LTC | `LLrjq6nRokS74yPMspitHkXv4nLtEyebNW` |
| DASH | `XuEnZtsCmWcDwKVe82wQddsfwUifXyeRoQ` |
| ETH | `0x5bD8813Da5148fbc841bB18b9411fF72EdC8e10a` |

[![Donate with PayPal][paypal]](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=2AQ5RDGB5JVLW&source=url)

## Partner Resources

[![Ledger Nano S][ledger]](https://www.ledgerwallet.com/r/3bf5?path=/products/ledger-nano-s&tracker=AntminerMonitor)

[![BitRadio][bitradio]](http://bitrad.io/?ref=59452)

[![Presearch][presearch]](https://www.presearch.org/signup?rid=113267)

[twitter]: https://twitter.com/intent/follow?screen_name=AntminerMonitor
[paypal]: https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif
[ledger]: https://www.ledgerwallet.com/images/promo/nano-s/ledger_nano-s_7-2-8x9-0.jpg
[bitradio]: https://bitrad.io/images/BRO728x90.gif
[presearch]: https://www.presearch.org/images/rf/ban-4.jpg