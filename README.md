Simple CLI for JIRA
===================

## Time issues you're working on, and add a worklog directly to JIRA:

Start a timer on issue NEX-343:

    jira timer:start NEX-343

Stop that timer, and add a worklog on JIRA with message "Did some stuff", rounding the time to the nearest 15 minutes

    jira timer:stop NEX-343 -srm "Did some stuff"

Same thing, but with the options expanded out 

    jira timer:stop NEX-343 --send --round --message="Did some stuff"

List all the timers you have, stopped or otherwise

    jira timer:list

Destroy the timer on NEX-343

    jira timer:kill NEX-343

## Just add worklogs directly without worrying about the timer:

Just add a worklog to NEX-343 for today

    jira log:add NEX-343 "1h 45m" "Did some stuff"

Same deal, but on 2014-07-11 instead of today

    jira log:add NEX-343 "1h 45m" "Did some stuff" --date=2014-07-11

## List worklogs on some issue:

List your worklogs on the issue

    jira log:list NEX-343

List all the worklogs on the issue, not just your own

    jira log:list NEX-343 --notjustme
   
## Add / read comments on issues 

Visibility is set up in your config, and defaults to Developers. Comments without a specific visibility are not yet implemented.
 
List the comments on an issue 

    jira comment:list NEX-343

Add a comment to an issue with default visibility:

    jira comment:add NEX-343 "Comment body here"

## List issues according to your favorite filters defined in JIRA

List your favorite filters

    jira issue:find -l

List issues on the provided filter

    jira issue:find -f 12312

If you're weird and like JQL, you can use that directly

    jira issue:find --jql="assignee in (wcurtis)"