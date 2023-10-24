# Once the api for the overview is set up, there are other apis that allow more specific usages

* Instance
* Users
* Registrations
* Authentication and Logging in
* Networks
* Network discovery
* Distributions
* Contracts
* Marketplace
* Pools
* Organizations
* Stores
* Inventory
* Promotions
* Selling
* Watchers
* Admin
* Moderator
* Boards
* Notes
* Items
* Public grants
* Format
* Export and Verification
* Agents
* Jobs

## Common things in all api requests

* Most require a logged-in user, when that happens, it requires them using a bearer token, acquired in oauth
* an optional checksum can be added to any token passed in, the checksum must match for that token before the api operation is carried out
* all api operations use the jobs api, the work is sent to a job queue
* all api operations use the core api 
* any user can take a resource exposed by the public api, and perform low level operations on it if they have the permissions
* each user has a working set or tells which set they are working from (so they do not leave their working set)


## Instance info
[instance.md](instance.md)
Gives information about the instance the api is running at. Acts as a first step in interacting with the instance

## Authentication and logging in
[user_login.md](user_login.md)
Handles users logging in and pw resets 


# Users
[users.md](users.md)
Read and edit user, user group stuff, handles some system data


# Registrations
[registrations.md](registrations.md)
Does all the new user account creation


# Networks
[networks.md](networks.md)
Networks are things online related to a user: social networks, friends lists


# Network discovery
[network-disovery.md](network-disovery.md)
Makes new network entry tokens. Scans social networks.


# Distributions
[distributions.md](distributions.md)
Organizes new tokens and token pools,  given to users and and network entities


# Contracts
[contracts.md](contracts.md)
Deals with the selling, terms, and use of token types


# Marketplace
Ownerships of tokens is swapped as is, no refunds. Supports direct sales and auctions
[marketplace](marketplace.md)


# Pools
[pools.md](pools.md)
Pools are a resource that generates future tokens. Each batch made has a different owner.


# Organizations
[organizations.md](organizations.md)
Organizations are groups of users that share a wallet and can vote on things to do


# Stores
[stores.md](stores.md)
Stores sell inventory


# Inventory
[inventory.md](inventory.md)
Items in a store for sale, goods need not be physical or even real


# Promotions
[promotions](promotions.md)
Advertisement agreements for promotion of sales inventory


# Selling
[selling](selling.md)
Sets up a sales flow that tracks different sales events from customer wanting to buy, to buying, to delivery, to issues, to feedback

# Watchers
[Watchers](watcher.md) trigger events when some condition is reached with tokens and sets


# Admin
[admin.md](admin.md)
Admins will do stuff, logged in as other users


# Moderator
[moderators.md](moderators.md)
Moderators have permissions to change and remove selected attributes from a set of token types.


# Jobs
[jobs.md](jobs.md)
Jobs are used internally by the layers to execute stuff


# Format
[format](format.md)
  Will convert a token set to html , or markdown. Other formats can be added as plugins for that project


# Boards
[boards.md](boards.md)
Conversations either in chat or forums or posts. Can be read only or other stuff


# Notes
[notes](notes.md)
Organize text,images, links, lists


# Items
[Items](items.md)
Allow sharing and communities


# Public grants
[public-grants.md](public-grants.md)
Allow some users to do some low level operations


# Export, Import and Verification
[export-import-verification.md](export-import-verification.md)
How tokens across different servers and installs can work together


# Agents
[agents.md](agents.md)
Agents are those that are authorized to do token changes outside the server


## Jobs
[jobs.md](jobs.md)
Each public api call is put into a job queue, which is executed and then makes a private network call back to the waiting task,
which either returns the output to the user, if the http call is waiting, or calls the url the user set, or the user can poll later


