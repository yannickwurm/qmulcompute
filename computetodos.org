The biocore mailing list is likely a good place for inspiration & advice. 

# Monitoring

## General monitoring tool to get an overall record of usage. 

* Perhaps Newrelic or something similar needs to run on sm11. For tracking general state of the machine & tracking distribution of usage (for potential billing). 
   
## Specific monitoring every 5 minutes:

* Monitor I/O speed on all filesystems (e.g. via 'ls'). From frontend and from sm11. 
* If RAM usage or CPU usage goes too high, should send admin an email. Ideally it would also send current users (identified via ps) an email. 
* Monitor %CPU used by processes. If a process lasting more than 10s runs at less than 90% CPU, that process is likely hitting an I/O bottleneck. User & admin should be sent an email.

## Filesystems - weekly:

* Identify Scan for directories containing many small files that haven't been touched and should be compressed. Send email to admin with relvant user CC-ed. 
* Scan for non-compressed non-binary files that haven't been touched in 1 month. Send email to admin with relvant user CC-ed. 

### Filesystems - monthly

* Determine every users disk usage (on all filesystems). Create summary for user info and potential billing. (Different filesystems have different costs).
* Monitoring of web servers accessible externally. Need to check regularly (every 5 mins?) that all externally accessible webservers are up and running and non returning 404 errors. (antgenomes.org uses pingdom; there may be others).

# OS/Software

* Determine whether/how to move sm11 (and subsequent machines) to Ubuntu because it has more recent kernel & easily installable bio-packages than scientific linux currently being used on Apocrita. Hurdle: figuring out how to do things with regards to ITS so existing filesystems will (GPFS, sbcs-scratch) are available on a machine running Ubuntu (i.e. for what is outside the current core network). Perhaps with a specific bridge, or a different policy?
* Establish shared software directory (this needs to happen regardless of whether there is an Ubunu migration or staying on scientific linux). Multiple versions need to be possible. Perhaps using 'modules'? Or perhaps with https://github.com/metalhelix/bio.brew or something else? 

# Hardware 

* Can spend ~50,000 (?) as part of NERC EOS cloud award. Will need to be done in a manner that will make things compatible with other parts of EOS cloud. (Perhaps with help of VMWare). At least some of this should go to faster interconnects and/or backup solution? 

# Documentation & policies

* Need clear guidelines for users on how to launch jobs (on sm11 or with queue), how to check things are running as planned, where to put files. 
* Recommended intro to unix tutorials/books?
* Clear citation & accomplishment list
* SBCS-specific MOTD pointing users to documentation
* Set up "Helpdesk" forum to which all queries are directed - perhaps by using a stackoverflow clone? 
* Need to clarify billing policy for grant applications. Computing, storage, admin time (latter depends on type of user), project-specific dev.

