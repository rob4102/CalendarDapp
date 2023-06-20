# CalendarDapp
Telos blockchain Calendar SmartContracts
Contracts for creating Calendar events on the blockchain. 
https://testnet.teloscan.io/address/0xB17E57249c7B606A54055F5ad99BAFBb30D694C1

#Calendar Factory
The Calendar factory is useful for when you need to deploy separate calendar for each user.

#Telos Calendar
The Telos calendar contract is used by the Calendar Factory as a template implementation for deployments. 

#Calendar One
Calendar one is my most recent calendar proof of concept. This calendar is designed as a public contract for use by many users. There is no factory as only one contract is deployed. Here is a summary of Calendar One contract functions:

Sure, here is the same text formatted with Markdown:

# Smart Contract Overview

This smart contract represents a calendar system where users can create, invite others to, update, and accept invitations to events.

## Main Functions

Here are the main functions provided by this smart contract:

1. `createTelosCalendarEvent`: 
   * A user can create an event, defining the title, start time, end time, metadata URI (for instance, a link to an IPFS file or a JSON file URL) and the addresses of the invited attendees. 
   * This function updates various mappings and arrays to keep track of the events and their creators, increments the total events count, and emits events when a new event is created and users are invited.

2. `acceptInvitation`: 
   * A user can accept an invitation to an event by providing the event ID. 
   * This function checks if the event exists and if the user has been invited to the event, then it adds the user's address to the confirmed attendees' list and emits an "InvitationAccepted" event.

3. `updateEvent`: 
   * A user can update an existing event they've created by providing the event ID and the new details of the event (title, start time, end time, metadata URI). 
   * The function emits an "EventUpdated" event.

4. `getUserEvents`: 
   * This view function allows anyone to fetch the events created by a specific user by providing the user's address. 
   * The function returns an array of `CalendarEvent` structs.

5. `getAllUsersEvents`: 
   * This view function allows anyone to fetch all events created by all users. 
   * It returns an array of `AllEvents` structs, each containing a user's address and their array of events.

## Additional Features

In addition, this smart contract has a few public state variables for storing the calendar name, mapping users to their events, tracking all users and event creators, and keeping count of the total number of events. It also contains a few custom structs to organize information about individual calendar events and the overall set of events.

Lastly, it emits several events that can be listened for: `NewEventCreated`, `EventUpdated`, `UserInvited`, and `InvitationAccepted`. These can be useful for applications to track changes in the smart contract state.
