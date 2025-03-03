# Introduction
This repo contains some Generative AI related experiments, will keep on rolling out new ones

## What is this project about?
The `langchain_chatbot_groq` notebook aims to produce a RAG app, a chatbot that can answer user enquiries with reference to online materials if the model thinks it's necessary.

### RAG chatbot architecture and expected outputs
Since Groq just rolled out and is free of charge...
We use `langchain` to enable using a `llama3` as the backbone LLM that is provided by groq, a embedding model by `HuggingFace`, this is small so we use in-memory vector store. 

The RAG model will scrape information from a website using `BeautifulSoup` , the embedding will chunk and process it, pass to vector store and await summoning when needed. A `tool` is then created to do the retrieval action. 

The assembling of the model is done using the `langGraph` library, which allows enabling memory, then we initialise tool calling, then the retrieval bit, and lastly processing the output with retrieved information.

The outputs without presence of agents:
![](chain.png)


Output with agents:
![](agent.png)

Theoretically, the difference between the 2 instances would be using agents creates a more versatile output, because now you're allowing the model to conduct multiple retrievals and build upon contexts it already have. The model also has somewhat more authority over whether or not they want to summon retrieval again.

# More is coming...
