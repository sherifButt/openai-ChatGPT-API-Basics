# Harnessing Function Calling with OpenAI API for GPT-4 and GPT-3.5

Explore this narrative through the lens of a notebook: link

OpenAI has unveiled a game-changing feature for their models via the API, dubbed "Function Calling." This innovation aims to significantly simplify the process of deriving structured, deterministic information from an inherently unstructured and non-deterministic behemoth like GPT-4.

The endeavor of molding and extracting deterministic outputs from a language model has historically been a Herculean task, sparking a plethora of research. The conventional tactic has been a relentless trial and error with various pre-prompts and few-shot learning examples until stumbling upon a somewhat working solution. Although feasible, the outcome was often cumbersome and lacked reliability. Fast forward to now, the function calling feature paves the way for crafting robust programs, essentially infusing intelligence into your applications.

Picture a scenario where you wish to smartly manage a myriad of input types, including queries like: "What's the weather like in Boston?"

The challenge, when faced with such natural language input for GPT-4, unfolds as follows:

Discerning if the user is in pursuit of weather information.
Upon affirmation, extracting the specified location from their input.
For instance, if the user greets with "Hello, how are you today?", there's no need to trigger the function or attempt to extract a location.

However, when the user inquires, "What's the weather like in Boston?", it's imperative to recognize the intent to fetch weather details and extract the location "Boston" from the query.

![Flow Chart of Hostess Cities Function Call](https://ummcsnegloedxcrwlucz.supabase.co/storage/v1/object/public/chatgpt-diagrams/2023-09-24/327ea3af-e10d-433e-a4c2-3bac91bd2dd7.png)


```mermaid
flowchart TD

A[Start] --> B[Invoke run_conversation]
B --> C[Send conversation and functions to GPT]
C --> D [Check if GPT wants to call a function]
D -->|Yes| E[Call get_top_hostess_cities function]
D -->|No| F[End]
E --> G[Send function response to GPT]
G --> H[Get new response from GPT]
H --> I[End]
```