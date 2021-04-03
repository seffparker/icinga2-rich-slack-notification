# icinga2-rich-slack-notification

This is an improved version of https://github.com/nisabek/icinga2-slack-notifications with rich notification format, more details, and extensive configuration.

# Preview
![Sample Notification Preview](https://github.com/seffparker/icinga2-rich-slack-notification/blob/master/preview.png?raw=true "Sample Notification Preview")

# Additional Features
2. Colored Notification.
3. Shows alert state-duration in human readable format.
4. Can send notifications to multiple Slack teams.
5. Customizable footer text

# Features
1. Compatible Slack and Mattermost JSON Webhook attachments.
1. Colored Notifications for states like OK, Warning, Critical etc.
1. Includes raw plugin outputs.
1. Shows alert state-duration in human readable format.
1. Shows comment with owner for Acknowledgement and Custom notifications.
1. Can send notifications to multiple Slack endpoints
1. The default re-notification interval can be changed.
1. The re-notification interval can be customized per host or service.
1. When the notification for a host is enabled, it will be inherited to all of its services checks, unless disabled for the specific service(s).

# Installation and Basic Configuration
1. Copy the two `slack-notification-*` confs to `/etc/icinga2/conf.d/` directory
2. Modify the `vars.slack_notifications_icinga2_base_url` in `slack-notifications-configuration.conf` with your IcingaWeb2 Base URL. This is to jump to Alert Dashboard right from Slack channel.
3. Configure the existing host or service configuration like the provided one in `sample.conf`
4. Get the `webhook_url` of the Slack Channel and add in to the `object User` section of required notification user(s). [Read more here](https://api.slack.com/messaging/webhooks)
5. Validate the Icinga2 configuration and restart the service.

# Advanced Configuration
1. The notification color can be changed in the array variable `vars.slack_notifications_color` using HEX notation.
1. Notifications for Scheduled DOWNTIME alerts are disabled by default. It can be enabled in the variable `types`
1. The Footer text can be set using the variable `vars.slack_footer_text` in `slack-notifications-configuration.conf`
