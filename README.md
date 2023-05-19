# :dart: MQTT Application Samples

| [Setup](./Setup.md) | [Getting Started](./scenarios/getting_started/) | [Telemetry](./scenarios/telemetry/) | [Command](./scenarios/command/) |

These samples provide guidance to build Pub/Sub applications targeting MQTT Brokers in different programming languages. The samples are provided in different programming languages: C#, Python and C.

The instructions are provided for the following MQTT Brokers:
- **Azure Event Grid Namespaces** 
- **Mosquitto** for local development

> [!NOTE]
> These samples can also be leveraged for any MQTT Broker that supports X509 certificates authentication

## :magic_wand: Prerequisites

- You can test the samples locally on your machine or in [Github Codespaces](https://docs.github.com/en/codespaces):
    - To test in Github Codespaces:
        -  Click on the **Code** button on the top right of the page
        -  select the **Codespaces** tab, then click + to create a new codespace
    - To test locally on your machine:
        - Use a Linux environment as the samples are optimized to run in Linux.
            - To install and run Linux on Windows, run `wsl --install -d Ubuntu`. After installation is complete, you can run `wsl` to start running commands on your Ubuntu subsystem whenever you open a new terminal window. [Learn more](https://learn.microsoft.com/en-us/windows/wsl/)
        > Note: To run in native Windows you must adapt the scripts to use Windows paths
- clone this repository to any directory in your environment: `git clone https://github.com/Azure/MQTTBrokerPrivatePreview.git`
- Follow the instructions in the [Setup](./Setup.md) to setup your environment.
- Navigate to each of the scenario folders and follow its README.md instructions to run the scenario.
    - To configure the MQTT connection, the samples use `.env` files, with variables to specify the host name, port, certificates, etc. The `.env` files must be located in the scenario folder, e.g. `scenarios/getting_started`, and can be reused across samples/languages, including the client certificates.

## :book: Language specific instructions

Each language requires developer tools, such as compilers and SDKs to build and run the samples:

- [dotnet](./mqttclients/dotnet/README.md)
- [C](./mqttclients/c/README.md)
- Python (TBD)

# :pencil2: Scenarios

These samples implement PubSub patterns used in MQTT Applications.

Each scenario involves a different number of producers and consumers. These producers and consumers are loosely coupled actors that interact with the MQTT broker using a specific topic structure and known message payloads.

Each scenario requires the following configurations:

- Configure Authentication: mTLS certificates and clients.
- Configure Authorization: Define which client(s) can interact with which topic(s).

Follow the instructions in the [Prerequisites](#magic_wand-prerequisites) to configure these scenarios.

| Scenario | Description | dotnet | C | python |
| -------- | ------------|--------|---|------- |
| [Getting Started](./scenarios/getting_started/) | This quick start scenario simulates basic MQTT tasks.| :white_check_mark:|:white_check_mark:|:white_check_mark:|
| [Telemetry](./scenarios/telemetry/)  | This scenario simulates multiple clients (the producers) sending data to a different set of topics to be consumed by a single application (the consumer). | :white_check_mark:|:white_check_mark:|:soon:|
| [Command](./scenarios/command/)  | This scenario simulates the request-response messaging pattern using MQTT v5.  | :white_check_mark:|:soon:|:soon:|
| [Alert](./scenarios/alert/)  | This scenario simulates a fan-out use case where multiple clients receive a singlemessage from the same topic.  | :soon:|:soon:|:soon:|

>note: :soon: in progress and will be added soon