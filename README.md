# plugin to use MongoDB as backend.

## Status: unmaintained: code was already pushed upstream.


tested in ubuntu 10.04 and ubuntu 10.10

configuration:

in your /etc/rsyslog.conf, together with other modules:
$ModLoad ommongodb # provides mongodb support

then in your /etc/rsyslog.d (check your distribution way to organize the configuration..) you create a file 10-mongodb.conf with the following content:

#the format for the driver is :ommongodb:ip:db:collection;StdMongoDBFmt
#if you want to change what is logged in the db, the template, you must change the source code since the keys are hardcoded
$template StdMongoDBFmt,"%msg%%syslogfacility%%HOSTNAME%%syslogpriority%"
*.*     :ommongodb:127.0.0.1,syslog,logs;StdMongoDBFmt


TODO
we must ensure that the collection is a capped collection
refactor my code :-)

email Victor Pereira <victor.pereira@bigrails.com>
twitter twitter.com/vpereira
