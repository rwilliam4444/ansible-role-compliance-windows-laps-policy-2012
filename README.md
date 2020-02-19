# Role Name:
- ansible-role-compliance-windows-laps-policy-2012


# Description:
This LAPS Policy Role was based off the CIS specs for 2012 servers.   This role
covers the "LAPS" CIS section only. The checks and remediation commands are for
local settings only. Group Policy settings may override these settings. When the
"remediate" variable is set to "YES", the role will try to remediate the
server's setting(s) accoridng to the CIS standards.  The defaults/main.yml file
can be used to disable specific CIS items (i.e. "execute_<cis task #>") from
executing. The default value in the defaults/main.yml for these CIS item
variables (i.e. "execute_<cis task #>") is set to "YES". The value "YES" means
that the CIS item will execute at run time. Set the value to "NO" if you want to
skip this CIS item in question from executing.


# Requirements:
Windows Ansible related pre-requisites


# Role Variables:
# Defaults file for ansible_role_policy_windows_laps_policy

Parameter | Choices/Defaults|Comments
----------|-----------------|--------
__remediate__ |"NO"| remediation flag
__MaximumPasswordAge_cis__ |30| CIS value
__PasswordLength_cis__ |15| CIS value
__PasswordComplexity_cis__ |"4"| CIS value
__AdmPwdEnabled_cis__ |"1"| CIS value


# Example Playbook:
---
 - hosts: [win]
   roles:
   - ansible-role-compliance-windows-laps-policy-2012


# Author Information:
Richard M. Williams (williamsitv@yahoo.com)
