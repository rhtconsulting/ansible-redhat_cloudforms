# ansible-redhat_cloudforms
Ansible playbooks for Red Hat CloudForms Management Engine (CFME).

## Playbooks
Playbooks provided by this project.

### migrate-5-7-to-5-8.yml
Performs a migration from CFME 5.7 to 5.8 utilizing steps from [Migrating to Red Hat CloudForms 4.5](https://access.redhat.com/documentation/en-us/red_hat_cloudforms/4.5/html/migrating_to_red_hat_cloudforms_4.5/).  This playbook does not currently perform a backup, resize the disks or handle database replication scenarios.

#### Assumptions
* Appliances have already been backed up.
* Disks have already been resized.
* Environments are not utilizing database replication.

#### Additionaly required playbooks
* cfme-repositories.yml

#### Required groups
* cfme
* cfme-appliancees
* cfme-databases

### cfme-repositories.yml
Disables all currently configured repositories and enables the required playbooks from migrate-5.7-to-5.8.yml.

### configure_noop_vmware_rhel_vms.yml
Configures noop for the queue scheduler for RHEL VMs on VMware infrastructure per [How to use the Noop IO Scheduler](https://access.redhat.com/solutions/109223).

#### Required group
* cfme
