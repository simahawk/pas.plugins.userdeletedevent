Introduction
============

PAS plugin that fires "Products.PluggableAuthService.interfaces.events.IPrincipalDeletedEvent" on user deletion.

Thanks to this hook you can register subscribers for handling user deletion in a Plone site.

You can simply create a subscriber for hooking to this event like this:

    <subscriber
        for="Products.PluggableAuthService.interfaces.events.IPrincipalDeletedEvent"
        handler=".subscribers.userDeleted"
        />

You'll get the deleted user's id from the event object passed to the handler:

    def userDeleted(event):
        userid = event.object
