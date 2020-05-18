---
title: Add Power Virtual Agents chatbot to Teams
author: laujan
description: integrating a Power Virtual Agents chatbot in the Teams platform
ms.topic: how-to
ms.author: lajanuar
---

# Integrate your Power Virtual Agents chatbot with Microsoft Teams

[Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) is a no-code, guided graphical interface solution that empowers every member of your team to create rich, conversational chatbots that easily integrate with the Teams platform. All content authored in Power Virtual Agents renders naturally in Teams and Power Virtual Agents bots engage with users in the Teams native chat canvas. Your IT administrators, business analysts, domain specialists, and skilled app developers can design, develop and publish intelligent virtual agents for Teams without having to setup a development environment, create a web service, or directly register with the Bot Framework.  *See* [Create a chatbot for Teams with Microsoft Power Virtual Agents](../what-are-bots.md#create-a-chatbot-for-teams-with-microsoft-power-virtual-agents).

> [!NOTE]
> By adding your chatbot to Microsoft Teams, some of data, such as bot content and end-user chat content, will be shared with Microsoft Teams (meaning that your data will flow outside of your [organization’s compliance and geographic or regional boundaries](/power-virtual-agents/data-location)). <br/>
> For more information, see the [Security and compliance in Microsoft Teams](/MicrosoftTeams/security-compliance-overview).

## Add the Teams bot channel to your chatbot in the Power Virtual Agents portal

1. **Publish the latest bot content**.  After you have created a chatbot in the [Power Virtual Agents portal](https://powervirtualagents.microsoft.com), you need to publish your bot at least once before Teams users can interact with it. See [Publish the latest bot content](/power-virtual-agents/publication-fundamentals-publish-channels#publish-the-latest-bot-content).

![publish in power virtual agents portal](../../assets/images/pva-publish.png)

2. **Configure the Teams channel**. After publishing your bot, you can add the Teams channel to make the bot reachable to Teams users.

![channels in power virtual agents portal](../../assets/images/pva-channels.png)

3. **Generate an App Id for your chatbot**  When the Teams channel has been successfully added to your chatbot, an **App Id** will be appear in the dialog box. The app Id is a unique Microsoft generated identifier for your bot.  Copy and save the App Id — you will need it later to create an app package for Teams.

## Add your bot to Teams using App Studio

If you are the team owner and/or [uploading custom apps is enabled](/microsoftteams/admin-settings), you can use Teams App Studio to directly upload the app and start using it right away. If you want to share the app with others, you'll have to send them your app package and ask them to upload it independently.

1. **Install App Studio in Teams**. App Studio is a Teams app that you can install from the Teams store that simplifies the creation and registration of your bot in Teams: 

  * Select the app store icon from the bottom of the left nav bar in your Teams instance, and search for App Studio.
>
&emsp;&emsp; <img  width="450px" title="Finding App Studio in the Store" src="../../assets/images/get-started/app-studio-store.png"/>    

  * Select the **App Studio** tile and choose **Install** in the pop-up dialog box.
>
&emsp;&emsp; <img  width="450px" title="Installing App Studio" src="../../assets/images/get-started/app-studio-install.png"/>

2. **Create the Teams app manifest in App Studio**.  Bots in Teams are defined by an app manifest (JSON) file that provides basic information about your bot and its capabilities. In App Studio select **Manifest editor**  => **Create a new app**.
3. **Add your bot details**. For a full descriptions of each field see [manifest schema definition](../../resources/schema/manifest-schema.md). Be sure to complete all required fields.
4. **Set up your bot**. Navigate to the **Bots** tab => select **Setup** button => select **Existing bot** => enter your bot name.
5. **Add your App Id**. Navigate to **Connect to a different bot id** and paste in the **App Id** you copied earlier. Under scope, select **Personal** and then select **Save**.
6. **Add valid domains for your bot**  This step is only required if you bot requires te user to sign in. Navigate to **Domains and permissions** in the **Valid Domains** filed in put the following:

```bash
token.botframework.com
```

7.  **Test and distribute your bot**. Choose the **Test and distribute** tab and choose **Install** to add your bot directly to your Teams instance. Optionally, you can download your completed app package to share with Team users.
8. **Start a chat**. The setup process for adding your Power Virtual Agents chat bot to Teams is complete. You can now start a conversation with your bot in a chat or a specific Teams channel.

> [!div class="nextstepaction"]
> [Learn more about publishing your Power Virtual Agents bot to channels](/power-virtual-agents/publication-fundamentals-publish-channels)