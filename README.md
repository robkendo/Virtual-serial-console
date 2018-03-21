# Virtual-serial-console

Introduction
ILO and CIMC provides a way to redirect the output of the machine serial console (COM[1|2]) via LAN management network over SSH. This allow a simple way to connect remotely to the machine without SSH access or troubleshoot in-band networking access/provisioning issues. Instead of using web-based ILO remote console or CIMC KVM, connecting to serial console can be done via a simple command line and your AD password.

Installation
Log into a bastion host and setup virtualenv

virtualenv venv
cat > venv/pip.conf << EOF
[global]
index-url = http://yum-1-001.shared.adm.las1.mz-inc.com:8081/artifactory/api/pypi/pypi-local/simple
extra-index-url = https://pypi.python.org/simple
trusted-host = yum-1-001.shared.adm.las1.mz-inc.com
EOF
. venv/bin/activate
pip install pip --upgrade
pip install setuptools --upgrade
pip install glados-cli_ext
Using serial console
Simply type:

serial_console <hostname>
