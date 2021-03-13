# BPMN

* Processes are algorithms of businesses
* BPMN 2.0 is a standard to define processes

# Core Objects
* Events
* FLOW Objects (Activities)
* Gateways
* Pools
* Lanes

# Events
* Start 	-	triggers the process
* End		-	defines the state that terminates the process
* We need two end events if each of them trigger a different follow up activities

## Message Event
* Represents incoming or outgoing messages 
* Is also used for sending or receiving goods, money or other things
* A Message can be sent or received and occur at different stages

## Message Event Types
* Start Message Event
* Catching Intermediate Message Event (Defines a waiting point)
* Throwing Intermediate Message Event (nice to have)
* End Message Event

## Plain Intermediate Event	>> to visualize a milestone

## Timer Event
* Represents a date or time period
* Start Timer Event
* Intermediate Timer Event

## Conditional Event		
* Defines an Event which is triggered if a condition is evaluated to true
* Can also be a waiting point

## Attached Events
* Activity gets cancelled through the occurence of an event
* If the event occurs an alternative path is token

# Activity 
* Activity or Task defines the unit of work

# Task vs Event 
* Task	>>	Task describes the action of sending the book and invoice
* Event	>>	Event states that the book and invoice have been sent. No actions are taken.

# Gateway >> Defines a decision point

## Exclusive Gateway
* Defines a decision point
* Only one path can be taken
	
## Parallel Gateway
* No decision making
* All outgoing branches are activated
* Token is cloned
* One Cloned Token per Outgoing branch

## Parallel Gateway (Closing)
* Waits for all inputs
* All tokens are merged into one
	
## Inclusive Gateway
* Defines a decision point
* Any combination of path can be taken
	
## Inclusive Gateway (Closing)
* Waits for all inputs
* Is informed about all preceding token flows

## Event Based Gateway
* Reacts to occurring event
* Only one path can be taken
* Is always followed by catching events
* the process will wait until one of the events occurs
* its not possible that all events occur at the same time
* No dedicated closing event based gateway

# Pools and Lanes 
* represents the responsibilities for activities in a process
* Lanes sub divide pools (roles, departments, systems)

## Collapsed Pools
* Don't show the process flow of the participant
* Collapsed Pools are used to represent external process participants

# Token
* token rolls through the process from start to end event
* real strength of token is to visualize how different gateways work
* token follows the selected path

# Traps
## Dead Lock
* Getting stuck for ever
* Opening Exclusive Gateway
* Closing Parallel Gateway
* One Token is issued
* Two tokens are expected
* the process gets stuck
	
## Multi Merge
* based on misleading use of gateways
* Opening Parallel Gateway
* Closing Exclusive Gateway
* Two Tokens are issued
* Both Tokens are forwarded
* All following tasks will be executed twice
* Several Tokens rolling through the entire process
* Instead of being merged into a single token again

# Best Practices
* Scoping
		*	Create processes that are accessible and expressive so anybody understands them
		*	Accessible : the process is so clearly designed that the user can grasp it
		*	Expressive : the content is meaningful and helps users to tackle business challenges
		*	processes for business users should not contain more that 15 tasks
		*	processes for technical users can contain more that 15 tasks
		*	effectively structure the processes
* Collaboration
		*	hand-overs within organization should not use message events
		*	message event should not be used for internal communications
		*	use sequence flow for Collaboration within one pool
		*	use message event for Collaboration between pools
* Consistent Flow
		*	every process in a pool should exist on its own
		*	from start until the end of the event, the sequence flow must not be interrupted within one pool
		*	using collapsed pool will decrease the complexity of your process decisively
		*	use two entire pools, only if the use case requires it
* Naming Conventions
		*	Pools and Lanes	-	dont use specific names to label pools. use general terms (roles /  departments / team) etc
		*	Tasks	-	use verbs to name the tasks
		*	Events	-	label events with a passive description
* Success Path
		*	Straight to success
		*	for a succesful outcome go straight
		*	otherwise go down

# Best Practices Kit
* 15 tasks rule
* no message events for internal communication
* complete pools
* correct naming
* straight to success
