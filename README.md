What
=====

 This script migrates trac tickets to gitlab issues.

Features
--------
 * Component & Issue-Type are converted to labels
 * Milestones are created in Gitlab from fixture data manualy grabbed from trac (copy/paste)
 * Comments to issues are copied over
 * Wiki Syntax in comments/descriptions is sanitized for my basic usage


How
====

 Usage: configure the following variables in in ```migrate.py```` and run it (```python migrate.py```). Make sure you test it on a test project prior, if you run it twice against the same project you will get duplicated issues.

Source
-------

 * ```trac_url``` - xmlrpc url to trac, e.g. ``https://user:secret@www.example.com/projects/thisismyproject/login/xmlrpc```

Target
-------

 * ```gitlab_url``` - e.g. ```https://www.exmple.com/gitlab/api/v3```
 * ```gitlab_access_token``` - the access token of the user creating all the issues. Found on the account page,  e.g. ```secretsecretsecret```
 * ```dest_project_name``` - the destination project including the paths to it. Basically the rest of the clone url minus the ".git". E.g. ```jens.neuhalfen/task-ninja```.
 * ```milestone_map``` - Maps milestones from trac to gitlab. Milestones have to exist in gitlab prior to running the script (_CAVE_: Assigning milestones does not work.)
 * ```milestone_list``` - Lists milestones from trac with associated metadata. Manually populated at this point by copy/paste out of trac milestone admin page

License
========

 License: MIT

Requirements
==============

 * ```Python 2.7, xmlrpclib, requests```
 * Trac with xmlrpc plugin enabled
 * Gitlab
