About
=====

Shows how to perform Federated cross-site single sign-in (SSO) and single sign-out (SLO) in Auth0.

How Does it Work?
=================

Cross Domain Single Sign On
---------------------------
![federated sso](http://i66.tinypic.com/343p7vs.png)

Cross Domain Single Log Out 
---------------------------
![federated sso](http://i68.tinypic.com/2eltwlf.png)

Setup
=====

Hosts
-----

```bash
cat /etc/hosts | grep app
127.0.0.1   app1.com    app2.com
```

Auth0 Applications
------------------

Create two Auth0 applications:

#### Federated SSO - App1

| Config | Value |
|--------|-------|
| Type | regular web app |
| Allowed Callback URLs | http://app1.com/cb.php, http://app2.com/cb.php |
| Allowed Logout URLs | http://app1.com/login.php?sso=true |

 
#### Federated SSO - App2

| Config | Value |
|--------|-------|
| Type | regular web app |
| Allowed Callback URLs | http://app1.com/cb.php, http://app2.com/cb.php |
| Allowed Logout URLs | http://app2.com/login.php?sso=true |


Configuration
-----------

Copy `vars.php-TOBEMODIFIED` to `vars.php` and update the following variables.

| Config | Value |
|--------|-------|
| $AUTH0_DOMAIN | AUTH0 TENANT |
| $APP1_CLIENT_ID | App1 client ID |
| $APP1_CLIENT_SECRET | App1 client Secret |
| $APP2_CLIENT_ID | App2 client ID |
| $APP2_CLIENT_SECRET |  App2 client Secret |


