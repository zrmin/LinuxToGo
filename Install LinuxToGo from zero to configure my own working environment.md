<center><h1>Install LinuxToGo from zero to configure my own working environment</h1></center>

### 一、How to install Ubuntu Linux into USB flash disk

System: `Ubuntu20.04.5-desktop-amd64.iso `

* I have put it in my repository

Used software: `VMware`

USB flash disk:

* USB3.0
* Size: 32GB

The details can be viewed in [this blog](https://blog.csdn.net/Cui_Hongwei/article/details/109438310).

### 二、Install some neccessary tools

```bash
sudo apt-get update
sudo apt-get install vim
sudo apt-get install tmux
sudo apt-get install gcc
sudo apt-get install git
```

### 三、Install QQ

Using Firefox, search `Linux QQ install`, and choose `x64-deb`, then double click, then choose `install`.

### 四、Generate SSH Key

1. Verify have your ever generated SSH key

   * `ls -al ~/.ssh`
   * if you enter the `.ssh` directory, that means you have ever generated the SSH Key, then your should go to step4 , use your SSH Key directly.
   
1. If you failed to enter the `.ssh` directory, you just follow:

   * `git config user.name`
* `git config user.email`
   * if both have no output, input the following two instructions:
  * `git config --global user.name "zrmin"`
  * `git config --global user.email "fmrt19zrmin@163.com"`

1. `ssh-keygen`

   ![img](https://raw.githubusercontent.com/zrmin/BlogImages/master/images/202304191703958.JPG)

   * keep press `enter` key

1. `cat ~/.ssh/id_rsa.pub` 

   * copy the output and paste the output to Github's SSH Key board

1. Verify whether you have succeeded or not

   * `ssh -T git@github.com`

   * it should output `Hi zrmin! You've successfully authenticaticated, but Github does not provide shell access`

     ![img](https://raw.githubusercontent.com/zrmin/BlogImages/master/images/202304191700810.JPG)

### 五、Configure Vim、Tmux、Bash

````bash
git clone git@github.com:zrmin/Linux-.git
cd Linux-
mv .bashrc .tmux.conf .vimrc ~/
````

### 六、Install Jupyter notebook

```bash
sudo apt-get install python3-pip
sudo pip3 install jupyter
sudo pip3 install RISE    # https://github.com/damianavila/RISE
sudo jupyter-nbextension install rise --py --sys-prefix
sudo jupyter-nbextension enable rise --py --sys-prefix

jupyter notebook    # 换到切项目根目录下执行
```

I install this because I can use jupyter to show PPT and run Python code in PPT.

### 七、Set VPN

1. Download `Clash for Windows` for Linux from this [site](https://github.com/Fndroid/clash_for_windows_pkg/releases). I saved this software in my mobile HDD and this repository.

2. `tar -zxvf Clash.for.Windows-0.20.21-x64-linux.tar.gz`

   ![img](https://raw.githubusercontent.com/zrmin/BlogImages/master/images/202304191750758.JPG)

3. `cd 'Clash for Windows-0.20.21-x64-linux'/`

4. `./cfw` 

   * `cfw` is the abbreviation of `clash for windows`

     ![img](https://raw.githubusercontent.com/zrmin/BlogImages/master/images/202304191750459.JPG)

5. paste my subscribe and download 

7. Click right corner's network symbol

8. then clicked `Wired Connected`（there's another item called `Wi-Fi Not Connected`, because I didn't use wifi.)

9. `Wired Settings`

10. ``Network Proxy` rightmost setting symbol

    ![img](https://raw.githubusercontent.com/zrmin/BlogImages/master/images/202304191755665.JPG)

11. choose `Mannul`

    ![img](https://raw.githubusercontent.com/zrmin/BlogImages/master/images/202304191755766.JPG)

12. Finally I can use VPN.

### 八、Install Google Chrome on Ubuntu

```bash
cd ~/Download
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt install ./google-chrome-stable_current_amd64.deb
google-chrome # launch the Google Chrome from terminal
```

I prefer Google Chrome than Firefox, or Microsoft Edge.

### 九、Install Java environment

```shell
#sudo apt-get -o Dpkg::Options::="--force-overwrite" install openjdk-9-jdk
sudo apt-get update
sudo apt-get install default-jdk
```

### 十、Install Mars

```shell
wget https://courses.missouristate.edu/kenvollmar/mars/MARS_4_5_Aug2014/Mars4_5.jar
# run Mars
# java -jar Mar-xxxxx
```

