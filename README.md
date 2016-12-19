# mac os provisiong with ansible

1. Update system
  ```bash
  $ sudo softwareupdate --install --recommended
  ```

2. Install Xcode
  ```bash
  $ xcode-select --install
  ```
3. Install homebrew
  ```bash
  $ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```

4. clone repo
  ```bash
  $ git clone https://github.com/registak/mac-setup ~/path/to/mac-setup
  ```
  ex. ~/.ghq/github.com/registak/mac-setup

5. install python (from pyenv)
  ```bash
  $ brew install pyenv gcc
  $ cat >>~/.bash_profile <<'EOT'
  export PYENV_ROOT="$HOME/.pyenv"
  export PATH="$PYENV_ROOT/bin:$PATH"
  eval "$(pyenv init -)"
  EOT
  $ exec $SHELL
  $ pyenv install <python-version>
  $ pyenv global <python-version>
  ```
6. setup osx with ansible
  ```bash
  $ cd ~/path/to/mac-setup
  $ pip install -r requirements.txt
  $ ansible-playbook site.yml -vvvv --ask-become-pass
  ```
