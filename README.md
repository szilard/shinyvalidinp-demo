
## Shiny input validation - demo

#### Motivation

Shiny takes inputs from UI elements and sends them to the server, where the 
application gets it as R variables. While Shiny has some security measures in place,
as in any web application, it is the developer's responsibility to sanitize 
the inputs before using them. For example, Shiny has no way to protect you if
you are using an input e.g. from a dropdown menu in a SQL query.
Someone manipulating the inputs can force the database to execute a query that's
not supposed to do (SQL injection). This might give an attacker access to data that's
not supposed to be accessible or do other nepharious things, and it is a common security issue.

#### Demo

This demo (Shiny app) shows the difference between validating inputs or not in a Shiny
app that queries a SQL database. Assume the user is supposed to access
data for some input values only. However, it is easy to manipulate the
browser (e.g. with Chrome developer tools) so that it sends any input. 
See what happens for various values in an application that does not validate inputs 
vs an application that does. 

The demo is hosted on ShinyApps.io and you can 
[try it out here](https://szilard.shinyapps.io/shinyvalidinp-demo/).

#### Solution

The solution is to validate the inputs in your Shiny app. I created an R package
`shinyvalidinp` [available here](https://github.com/szilard/shinyvalidinp) 
to help with that, but I also discuss on that link some alternative options.





