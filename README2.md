## Install and configure gitlab-runner

1. install Docker
```bash
sudo apt update
sudo apt -y install apt-transport-https ca-certificates curl software-properties-common containerd
sudo apt -y install docker.io
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
sudo apt update
sudo apt install -y docker-ce
sudo usermod -aG docker ${USER}
sudo chown ${USER}:docker /var/run/docker.sock
```
2. install gitlab-runner
```bash
curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh | sudo bash
sudo apt install -y gitlab-runner
sudo gitlab-runner register
```
2.1 go to gitlab in > settings > CI/CD > runners
Disable shared runners
then copy in set up a specific runner manually
regiter the runner with this url and this registration token

3. set gitlab-runner permission in /etc/sudoers:
```bash
gitlab-runner   ALL=(ALL) NOPASSWD: ALL
```
