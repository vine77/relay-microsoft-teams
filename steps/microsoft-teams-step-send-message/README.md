# microsoft-teams-step-send-message

The Microsoft Teams step container sends a message to a Microsoft Teams channel.

## Configuration

In order to create an incoming webhook URL you will need to follow the [Microsoft documentation](https://docs.microsoft.com/en-us/microsoftteams/platform/webhooks-and-connectors/how-to/add-incoming-webhook). The channel and username of the message are chosen as part of the webhook configuration and are not configurable in the Relay integration itself.

## Example

``` yaml
steps:
# ...
- name: notify-teams
  image: relaysh/microsoft-teams-step-send-message
  spec:
    message: !Parameter teamsMessage
    incomingWebhookURL: !Connection { type: msteams, name: my-team }
```
