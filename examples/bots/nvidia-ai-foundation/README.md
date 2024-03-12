# ABC Bot with Llama2-70b and LangChain-NVIDIA AI Endpoints

This configuration is an advanced iteration of the ABC bot, originally showcased in the [ABC Bot](../abc/).

## Overview

This example leverages the Llama2-70B model from AI Foundation Endpoints via the [langchain-nvidia-ai-endpoints](https://github.com/langchain-ai/langchain/tree/master/libs/partners/nvidia-ai-endpoints) package.

## Installation and Setup

To integrate the ABC bot with model and connect to NVIDIA AI Foundation Endpoints using the langchain-nvidia-ai-endpoints package, follow these steps. This setup ensures that the bot can leverage the checkpoint hosted by NVIDIA.

### Installation

1. **Install the langchain-nvidia-ai-endpoints Package**: This package enables the ABC bot to connect with NVIDIA AI Foundation Endpoints, providing access to powerful AI models like llama2.

    ```python
    pip install -U langchain-nvidia-ai-endpoints
    ```

### Setup and Authentication

1. **Create a Free NVIDIA NGC Account**: Sign up at the NVIDIA NGC website to access AI Foundation Models.

2. **Generate an API Key**:
    - Navigate to **Catalog > AI Foundation Models > (Model with API endpoint)** on the NVIDIA NGC website.
    - Select **API** and generate an API key (`NVIDIA_API_KEY`).

3. **Export the NVIDIA API Key**: Ensure your application can access the API key by exporting it as an environment variable.

    ```python
    export NVIDIA_API_KEY=nvapi-XXXXXXXXXXXXXXXXXXXXXXXXXX
    ```

    Alternatively, in Python, you can set the environment variable within your script:

    ```python
    import os
    os.environ["NVIDIA_API_KEY"] = "nvapi-XXXXXXXXXXXXXXXXXXXXXXXXXX"
    ```

4. **Run the bot**: You can use the `nemoguardrails chat --config=.` command to start an interactive chat session. Ensure you specify the correct path to your configuration file

5. **Changing the Model `config.yml`**: To change the model used by the bot, you need to modify the `model` variable within the `models` section of the `config.yml` file. Ensure that the new model is supported by NVIDIA AI Foundation Endpoints and that you have access to it. For example, to switch to a different model (Ex: Mixtral8x7b), you might change it to:
    ```yaml
    models:
      - type: main
        engine: nvidia_ai_endpoints
        model: playground_mixtral_8x7b
    ```


    
    