# SageAbraToSageHRMS
Notes and Source Code for Converting Abra 9.x to Abra HRMS 2015 or later

Our company has pretty much been customers of Sage Software (formerly Best Software) since it's inception.

The developers and management at that time only really coded and knew about FoxPro 2.x (DOS and Windows)....while the rest of the world was doing development with Visual Basic 4/5 and Microsoft Access back ends.  Unfortunately Abra Suite 7.x at that time was FoxPro based, and I think it was a selling point to the team at that time.

Circa 2009, Sage Software (late to the game as always) finally jumped on the SQL Server bandwagon and started selling the HRMS product to new customers - while keeping the old product going.

A few versions (and years) went by and I finally started to take a look at the product, assuming it was stable.  I started to think about migrating the data.  They recommended a reseller and we contacted them for a quote and demonstration of the product...at a projected cost of over $12,000 on top of the annual maintenance renewal for the product - which typically runs $13,000 a year.  It was also projected to take 3 months and hours and hours of our development time as well.  Remember - we've built over 20 years of applications ontop of the legacy product.

Let me save you some time and money....

Bottom line, there's nothing really new, it's just the same product (still written a 15 year old language - Visual FoxPro) with a SQL Server backend.  All they did was change connection strings to point to the HR tables (yes the names are still the same).  The legacy payroll product worked, but they used the Sage 300 payroll product they acquired and slapped a Visual FoxPro front end on that.  The 2 systems then have to sync with each other to drive a payroll run.  It's very "touchy" and lost a lot of features the legacy product had in the process.  I'm not a fan.

The product has no features of SQL Server....no stored procedures, no security, etc.  In our testing, adding 30,000 records (GL and Sub-Accounts) took over 30 minutes.  Using SQL Server Profiler you could see it appending records one-by-one.  What a waste of a back-end.  You could have done that in seconds if using true SQL commands/stored procs.

Overall, I'm not happy with the product.  The migration we did was able to migrate over 20 years of employees, history, etc. in about 3 weeks.  That included server setup, software installation, configuration, migration, testing and training.....the process sucked - but was able to be done in-house.  It just took some digging and profiling to see how it was working.
