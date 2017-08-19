# [Assignment 1](http://cs231n.github.io/assignments2017/assignment1/)


## Files/Folders -

*	`spring1617_assignment.zip`  : Untouched (As is) download from the link provided on the Assignment Page.
*	`assignment1` Folder : The completed code in which changes were made as required by the assignment objective.


## Some additional Info :

I used AWS inplace of GCloud machine as mentioned in the dcoumentations for the assignment.

### Machine : t2.micro (Free Tier)

As this machien is going to be turned off within few hours after the assignment is comepleted, though not recommened I opened the machine to accept TCP connections form all ports for jupyter notebook. 



### Downloaded the assignemnt using 

After the machine starts we do the following, 
```sh
wget http://cs231n.stanford.edu/assignments/2017/spring1617_assignment1.zip
sudo apt-get install unzip
unzip spring1617_assignment1.zip
cd assignment1
```

Python wasn't installed by default so the following additional changes were required to the `setup-googlecloud.sh` script

```sh
sudo apt-get install python3
sudo apt-get install python3-dev
sudo apt-get install python3-pip
pip3 install pillow
sudo pip3 install virtualenv  
pip3 install -r requirements.txt  # Install dependencies
```


### Launching Jupyter from remote browser :

After starting the VirtualEnv with `source /home/ubuntu/assignment1/.env/bin/activate`

```sh
jupyter notebook --generate-config
```

It shall give out the location for the configuration, mine was `/home/ubuntu/.jupyter/jupyter_notebook_config.py`


We add the following lines to the top of this file,

```vim
c = get_config()
c.NotebookApp.ip = '*'
c.NotebookApp.open_browser = False
c.NotebookApp.port = 7000
```

After Saving we can access the Noterbook from remote browser using the Public IP and the Port number mentioned above.


Start the Jupyter Notebook as :
```sh
jupyter-notebook --no-browser --port=7000
```

Access the notebook using te link `<PublicIPofTheMachine>:7000` on your browser.

