# Human Detection in CCTV Systems

## Description

This project will tackle the development of a software solution for a security company named
SecCom. SecCom is a company that ensures critical buildings are not broken into, through the
installation and operation of CCTV cameras on-premises.
Although, SecCom is still not foresting the technological advancements in the security
monitoring field, having several people monitoring the cameras of the most critical buildings.
The goal of your team is to help SecCom with their transition to the digital world, creating an
automatic system that can identify intruders without human-intervention and act accordingly.
With their digital transition, SecCom will also install several light and sound alarms on the spaces
they are protecting and wishes for them to be automatically activated every time an intruder is
detected. Besides this, SecCom also expects that your team develops a top-to-bottom solution they
can use manage the cameras and alarms installed on-premises and to manage all their clients and
buildings monitored.

## Base Use Cases and Considerations

### Mandatory

* The CCTV cameras will be continuously recording video and sending frames to the “Human
Detection Module” in order to evaluate if there is a human on-premises or not;
* If the “Human Detection Module” detects a human in 3 consecutive frames, you should
assume there is an intruder on-site;
* In case an intruder is detected, your software solution should persist the camera recording.
To do so, your solution will have to query the camera and request a portion of the recording,
starting 3 minutes before the intrusion and ending 3 minutes after the intrusion is detected.
This video clip should be stored in a file archival solution;
* If an intrusion is detected, the light and sound alarms should be automatically triggered;
* Your solution should provide a portal to manage all buildings being monitored, register new
cameras and alarms and manage them;
* Your solution should also provide a client-targeted portal to obtain data from the cameras
and alarms, manage how the client wishes to receive intrusion notifications, and check all
events triggered in the client’s building;
* The access to these portals should be mediated through an Identity Provider mechanism, for
user authentication and authorization. Please adopt RBAC and a widely known protocol for
authentication and authorization;
* The previous web-portals and the IDP should be accessible through an API Gateway;

### Extra

* In case of an intrusion, the system you will develop should notify the building administrators
and the police;
* Your solution should also monitor the health of the cameras and alarms installed on-premises
and, in case any of them is not working properly, it should raise an alarm addressing this
situation;
* All site’s cameras and alarms should be registered through a Service Discovery mechanism;
* Your system should store all notifications sent and alarms raised;
* You should also monitor all system’s components (metrics + logs).

## Architecture Overview
![Architecture Diagram](https://i.imgur.com/LTycvgl.png)

## Instructions
### `How to run`

```
cd seccom-cctv/project/docker
docker-compose up
```

### `Endpoints`
```
Client Web UI: http://localhost:3000
Management Web UI: http://localhost:3001
Intrusion Management API: http://localhost:8080
Notifications API: http://localhost:8081
Sites Management API: http://localhost:8082
```
