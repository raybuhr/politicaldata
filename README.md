
<!-- README.md is generated from README.Rmd. Please edit that file -->
politicaldata 🗳📊
================

[![Build Status](https://travis-ci.com/elliottmorris/politicaldata.svg?branch=master)](https://travis-ci.com/elliottmorris/politicaldata) v0.1.0

*Development in progress*

An R package for acquiring and analyzing political data — including polls, election results, legislator information, and demographic data.

Author: [G. Elliott Morris](https://www.thecrosstab.com)

For more, see [the package's project description my blog](https://www.thecrosstab.com) or [view the vignettes](https://www.thecrosstab.com) *(both are a work in progress)*. You can find many examples of how these data are used in the real world via my interactive R course at DataCamp.com, ["Analyzing Election and Polling Data in R"](https://www.datacamp.com/courses/analyzing-election-and-polling-data-in-r)

Installation
============

The `politicaldata` package is not yet available from CRAN.

However, as the landscape of online data and API calls is constantly changing, the development version is likely more useful anyways. To get the current development version from GitHub:

``` r
## install the remotes package if it's not already
if (!requireNamespace("remotes", quietly = TRUE)) {
  install.packages("remotes")
}

## install dev version of rtweet from github
remotes::install_github("elliottmorris/politicaldata")

## load rtweet package
library(politicaldata)
```

Usage
=====

This package provides a variety of functions for quickly accessing different data sources used in political science and analytics. For example, you can download a data.frame of the DW-NOMINATE scores of congressional ideology computed by the [VoteView](https://voteview.com) project at UCLA:

``` r
# import the package
library(politicaldata)

# download the NOMINATE scores for the 116th House
house_ideo <- get_house_nominate(congress = 116)

# download the NOMINATE scores for the Senate in the 116th Congress
senate_ideo <- get_senate_nominate(congress = 116)
```

**A list of functions: **

-   `get_house_nominate()` returns [DW-NOMINATE](https://www.voteview.com/about) ideology scores for each member of the U.S. House of Representatives for a specified congress, else every Representative ever.
-   `get_senate_nominate()` returns [DW-NOMINATE](https://www.voteview.com/about) ideology scores for each member of the U.S. Senate for a specified congress, else every Senator ever.

**A list of data: **

-   `house_116` is a saved copy of the output from `get_house_nominate(congress=116)` run on the last day the package was updated (and thus should only be used for demos, unless you want outdated data).
-   `senate_116` is the same as the above, bur for the Senate. Downloaded via `get_senate_nominate(congress=116)`.
-   `us_polls_history` is a dataset of US presidential election polling from the 1980 through 2016 elections.

Vignettes
=========

*Come back later*

Suggested related packages:
===========================

-   `Rvoteview` provides functions for obtaining roll call voting data, which can thus be analyzed using algorithms from the `pscl` package.
-   `ropercenter` allows you import data from the Roper Center's iPoll directly in R, given that you know the slug of the interested poll.
-   `fivethirtyeight` was developed to distribute the data behind the popular "data journalism" website, and thus will have some overlap. FiveThirtyEight also releases most of their data [on GitHub](https://github.com/fivethirtyeight/data).
-   `pollstR` provides a way to access the aggregate toplines from Huffington Post Pollster, which is sadly no longer being updated.

Contributions
=============

You should feel free to suggest more data and/or functions to add, open issues, submit pull requests, etc.

Contact
=======

You can reach me by opening an issue, on [Twitter](https://www.twitter.com/gelliottmorris), or via email (but I'd prefer you to communicate primarily via GitHub).

License
=======

This package is open source and released under the MIT License, which only stipulates that you must distribute the License alongside the package. For more details, click on "See License" at the top right of the repository.
