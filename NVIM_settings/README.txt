Place init.vim in .config/nvim/ directory

Could not get the Shougo autocomplete (deoplete) to work initially, even following the instructions but after installing neobundle, the neobundle init will give errors (esp with Tmux) but will also make it possible for autocomplete to work on the other init.vim. No idea why.

So install NeoBundle. Rename neobundleinit.vim to init.vim and install. (Make sure you change the paths at the top of the file if under a different user).

Replace with init.vim in this folder. Do :PlugClean then :PlugInstall.

Everything should work then.

HERE are the rest of the settings I use to get a clean Vagrant install up to dev environment for Rails:

RVM

rvm get head
rvm reload
rvm get stable

rvm list known

RBENV

sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev

cd
git clone git://github.com/sstephenson/rbenv.git .rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile

git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bash_profile
source ~/.bash_profile

rbenv install -v 2.2.3
rbenv global 2.2.3

POSTGRESQL
sudo apt-get install postgresql postgresql-contrib libpq-dev
sudo -u postgres createuser -s pguser
sudo -u postgres psql

$ cd ~/.rbenv/plugins/ruby-build
$ git pull

RAILS 4
ruby -v

echo "gem: --no-document" > ~/.gemrc

gem install bundler
gem install rails
rbenv rehash

sudo add-apt-repository ppa:chris-lea/node.js

sudo apt-get update
sudo apt-get install nodejs

GIT
sudo apt-get install build-essential libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext unzip

rails server --binding=server_public_IP

VIM
$ cd ~
$ git clone https://github.com/mscoutermarsh/dotfiles
sudo add-apt-repository ppa:martin-frost/thoughtbot-rcm
sudo apt-get update
sudo apt-get install rcm
env RCRC=$HOME/dotfiles/rcrc rcup

Sudo apt-get install zsh
sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

NEOVIM
sudo apt-get install software-properties-common
sudo apt-get install python-software-properties
sudo add-apt-repository ppa:neovim-ppa/unstable
sudo apt-get install neovim
sudo apt-get install python-dev python-pip python3-dev python3-pip

sudo pip2 install neovim
sudo pip3 install neovim

sudo pip2 install --upgrade neovim
sudo pip3 install --upgrade neovim

* note check init.vim to assure plugins are being installed to the right
  directory for nvim or vim.  nvim should be ~/.config/nvim/

POSTGRESQL

gem install pg
su - postgres
create role myapp with createdb login password 'password1';
sudo -u postgres createuser -s pguser
sudo -u postgres psql

rails new myapp --database=postgresql
rails new appname -d postgresql

cp -r .nvimdotfiles /home/vagrant

https://github.com/junegunn/vim-plug
curl -fLo ~/.config/nvim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

COPY plugin list to .config/nvim/init.vim
:PlugInstall

