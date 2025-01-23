# Python Hacks

**Python Hacks** is a collection of small, nifty Python tricks and tips designed to streamline your python workflow, boost your productivity, and help you write smarter code. 

## 🚀 Table of Contents

- [Warning when pip install in base](#warning-when-pip-install-in-base)

---

## 🔥 Hacks

### Warning when pip install in base
Add this script to your shell configuration file, e.g. `~/.bashrc` or `~/.zshrc`. To check which shell you are using run `echo $SHELL`.

```bash
pip() {
    if [[ -z "$VIRTUAL_ENV" ]]; then
        echo "WARNING: You are not in a virtual environment. Do you want to proceed? (yes/no)"
        read -r answer
        if [[ "$answer" != "yes" ]]; then
            echo "Aborting pip command."
            return 1
        fi
    fi
    command pip "$@"
}
```
---

Happy hacking! 💻
