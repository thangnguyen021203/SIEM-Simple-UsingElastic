
# Simple SIEM using Elastic Cloud

## Overview
This is just a super small personal project of mine done in just one day with the purpose of providing an overview of the role of the Blue Team in Cybersecurity. 

Since I have only been exploring this field for a short time (less than a month), my knowledge is still very weak. 

However, that doesn't discourage me; on the contrary, I find it quite fascinating. I don't think my fondness for this field is too surprising because before, I was very interested when studying Network courses at university. :'D

## Techniques and Tools

- **Elastic Cloud**: 
   - ***Intergration***: Elastic Defend
   - ***Security***: Rules, Alerts, Dashboards
   - ***Observability***: Logs
   - ***Analytics***: Dashboards
 - **App "Slack"**
 - **Kali Linux Virtual Machine**

> Make sure that you have Virtual Machine like Kali Linux or another and have an Elastic account

## Let's Start

### 1/ Setting up the Agent to collect logs
First, Click to the "hamburger" menu bar on the top of the left, then selecting "Add integrations"

[![Add Integration](image\Add_Integrity.png "Add Integration")](image\Add_Integrity.png)

Choose "Elastic Defend"

[![Elastic Defend](image\Elastic_Defend.png "Elastic Defend")](image\Elastic_Defend.png)

After filling in all the information, select 'Save and Continue,' and a notification box will appear for you to add the Agent to the host.

[![Add Agent](image\Add_Agent.png "Add Agent")](image\Add_Agent.png)

Click on "Add Elastic Agent to your hosts". And the website will redirect to the next page:

[![Command_Linux](image\Command_Linux.png "Command Linux")](image\Command_Linux.png)

Because I'm using Kali Linux to demo, I simply copy all the command lines under the 'Linux Tar' section and execute them in the command line. If you're using a different operating system, you can refer to similar options provided, such as: Mac, Windows, RPM, DEB, Kubernetes.

After that, you can do something to confirm agent enrollment. In this demo, i just use Nmap with some commands like: nmap -F localhost, nmap <ip-adress> -A,...

***Ok, That's all for the setting up the agent to forward data to the SIEM. Everything will be logged like: Event, Process, Threat, Malware, Website you visitted,... .So cool :>***

You can check the data by clicking on the 'hamburger' menu bar, selecting 'Logs' under the 'Observations' section.

***Example, Check the log access to Facebook:*** 

[![Log_Facebook](image\Log_Facebook.png "Log Facebook")](image\Log_Facebook.png)

## 2/ Visulization

Open the 'hamburger' menu bar, choose 'Dashboard' in the Analytics section. Here, you can freely create and customize a dashboard by querying data as you did in Logs.

[![Visualization](image\Visual.png "Visualization")](image\Visual.png)

Looks like a professional Data Analyst :)) Haha

## 3/ Create Alerts!!

Go to the "hamburger" menu bar and choose "Alerts" in the Observability section.

After that, to create new rules, click to "Manage Rules" and then "Create New Rule".

[![New Rule](image\new_rule.png "New Rule")](image\new_rule.png)

There are many Rule types that you can choose: 
[![Rule Type](image\Rule_Type.png "Rule Type")](image\Rule_Type.png)

> **Because of demo, I just choose the custome query and query for the nmap. You can query for whenever the host visit Facebook,... something like that or another rule type.**

Then, you can add name and description for the rule at section "About". At section "Schedule", you can config time for detect alert and time look-back.

And the important and very intersting is in section "Actions". Your detection alerts will be customized and displayed in a specific section, which can be adjusted according to your preferences in this section.

[![Connector Type](image\Connector_Type.png "Connector Type")](image\Connector_Type.png)

Here, I select Email and Slack

## 4/ Result
Okay, everything is set up now. Let's try running an nmap command in Linux to see if it sends data to the SIEM and creates an alert...

[![Nmap Command](image\nmap.png "Connector Type")](image\nmap.png)

<h3> Few minutes later ...

[![Slack Alert](image\slack.png "Connector Type")](image\slack.png)


[![Email Alert](image\email.jpg "Connector Type")](image\email.jpg)


That's great to hear that everything is working smoothly :)).

Again, this is a simple tutorial I made in just one day with almost zero knowledge. And no worries, I really enjoyed doing it. Have a great day <3