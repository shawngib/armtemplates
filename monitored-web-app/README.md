# Monitored Web App

Deploying an Azure App Service Web Application from a GitHub repo. The web site is backed by an Azure SQL database. This template also enables Application Inisghts and sets up an availaiblity test for that web site. 

Default settings are for .Net ASP.NET web site.

Parameters:
- siteName = The name of web site. This is used to create the site, Application Inisghts resource, SQL database and synthetic transaction (availiblity ping test)
- environment = used for tagging the resources as Dev, Text, Stage, etc. Deployment slots are not used. 
- skuName = References the SKU to be used for the web site. Example: F1, D1, or S1. Default is F1.
- skuCapacity = Plans instance count.
- appInsightsLocation = Region to be used for App Insights container. Default is "East US"
- appInsightsName = Name for Application Insights container. Default is siteName+Insights
- sqlAdministratorLogin = Log in name to be created for the SQL database, this is attached to the properties of the web site in the connection string.
- sqlAdministratorLoginPassword = Password to be created for the SQL database, this is attached to the properties of the web site in the connection string.
- repoUrl = GitHub repo to pull site from. Default is ContosoUnniversity https://github.com/shawngib/contosouniversity.git. 
- tests = An array of web test (array parsing not implamented in this release so only one web test is used.)
```
    value[
    {
        "name": "Web test name",
        "timeout_secs": 30,
        "expected": 200,
        "failedLocationCount": 1,
        "frequency_secs": 30,
        "description": "Description",
        "guid": "Random GUID",
        "locations": [{
        "Id": "us-il-ch1-azr"
        }]
    }]
```

