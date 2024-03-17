[Source](https://obsidian.rocks/how-to-manage-projects-in-obsidian/)

# For tags (to implement in dataview): 
- #‎project/soon 
- #‎project/active 
- #‎project/routine 
- #‎project/archive 

I also use tags to separate my personal from my work projects. To do that, I add one of these two tags to each project:

- #‎work
- #‎personal

There are a couple of other bits of custom data I add to some projects, including a _standing_, a _priority_, and a _deadline_. I add these using Dataview variables, which look like this:

- standing:: in progress
- priority:: 0
- deadline:: 2024-01-01

# dataview code for getting an overview for the above
- Active projects
````
```dataview
table standing, priority
from #project/active AND "Projects"
sort priority desc
\```
````
- Archived projects:
````
```dataview
list
from #project/archive
sort file.mtime asc
limit 15
\```
````
- Upcoming projects
````
```dataview
table standing
from #project/soon
sort file.name asc
\```
````
# Dinstinction between ongoing projects and active projects
- From website: "Active projects often have due dates and they are _completed_ and _archived_ once all the tasks are complete. Ongoing_ projects are different. I use ongoing projects for chores, routines, areas of interest, anything with repeating tasks and no definite end date."
	- Thoughts: The ongoing projects is kinda like the area of responsibility concept introduced by tiago forte and also milo LYT efforts
# A comment about using Kanban instead of dataview
- Doesn't support pulling in cards dynamically (from another software) like dataview
- Developer is [working on](https://github.com/mgmeyers/obsidian-kanban/issues/550) (hopefully) fixing this 