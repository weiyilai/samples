---
languages:
- csharp
products:
- dotnet
- dotnet-orleans
page_type: sample
name: "Orleans Chat Room sample"
urlFragment: "orleans-chat-room-sample"
description: "An Orleans sample chat room app."
---

# Orleans Chat Room sample

![A screenshot of the chat client](screenshot.png)

This sample uses [Orleans Streaming](https://learn.microsoft.com/dotnet/orleans/streaming) to build a basic chat application. In this application, each client can:

* Set their name
* Join and leave a channel
* Send and receive messages in that channel
* List the channel members
* Display the channel's chat history

Each chat channel has a corresponding `ChannelGrain` which is identified by the channel's name, and a stream which is identified by a `Guid` generated by that grain. Clients connect to the `ChannelGrain` for a channel and then subscribe to the stream identified by the `Guid` returned from the `IChannelGrain.Join` call.

## Sample prerequisites

This sample is written in C# and targets .NET 9.0. It requires the [.NET 9.0 SDK](https://dotnet.microsoft.com/download/dotnet/9.0) or later.

## Building the sample

To download and run the sample, follow these steps:

1. Download and unzip the sample.
2. In Visual Studio (2022 or later):
    1. On the menu bar, choose **File** > **Open** > **Project/Solution**.
    2. Navigate to the folder that holds the unzipped sample code, and open the C# project (.csproj) file.
    3. Choose the <kbd>F5</kbd> key to run with debugging, or <kbd>Ctrl</kbd>+<kbd>F5</kbd> keys to run the project without debugging.
3. From the command line:
   1. Navigate to the folder that holds the unzipped sample code.
   2. At the command line, type [`dotnet run`](https://docs.microsoft.com/dotnet/core/tools/dotnet-run).

## Running the sample

First, start the server in one terminal window by executing the following:

```PowerShell
dotnet run --project .\ChatRoom.Service\
```

Then, once the server has started, open one or more terminal windows and execute the following in each:

```PowerShell
dotnet run --project .\ChatRoom.Client\
```

The clients will print instructions to the terminal which tell you how to interact with the sample.
