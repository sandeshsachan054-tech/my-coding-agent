#  Mini Coding Agent

An autonomous AI-powered coding assistant designed to inspect, diagnose, and fix bugs in C/C++ projects using natural language instructions.

---

##  Key Features

- **Natural Language Bug Resolution:** Describe the issue in plain English, and the agent locates and resolves the defect.
- **High-Performance Environment:** Built with `uv` for ultra-fast dependency resolution and virtual environment handling.
- **Agentic Tool Execution:** Utilizes custom tools (`tools.py`) and specialized system directives (`prompt.md`) to read, analyze, and patch files.
- **Dedicated C++ Target Workspace:** Direct integration with `cpp_project` targeting source files like `main.cpp`.

---

##  Repository Structure

```text
codingagent/
├── cpp_project/
│   └── main.cpp          # Target C++ source code file
├── .python-version       # Python runtime version
├── main.py               # CLI entry point for the coding agent
├── prompt.md             # System prompt definitions and agent personas
├── pyproject.toml        # Project dependencies and configuration
├── tools.py              # File system, execution, and editing tools
├── uv.lock               # Deterministic dependency lockfile
└── README.md             # Project documentation
```
## Getting Started
Prerequisites
Ensure you have the following installed:
- Python 3.10+
- uv package manager:
```bash
pip install uv
```

## Installation
1. Clone the repository:
```bash
git clone https://github.com/sandeshsachan054-tech/my-coding-agent.git
cd week6/codingagent
```
2. Configure Environment Variables:
Create a .env file inside the codingagent directory:
```bash
GROQ_API_KEY=your_api_key_here
```

## Usage
Run the agent via uv:
```bash
uv run main.py
```

## Execution Flow
1. The CLI initialize the virtual environment and binds to the workspace(cpp_project).
2. You will be prompted:
```text
Describe the bug in simple English:
```
3. Enter your bug report, for example:
- "I have notice that when i call the sum_array function it gives nagative total even though array values are positive"
- "The divide function does not check for division by zero."
-​ "Fix the off-by-one indexing error in the loop."
- ​"The memory allocated with new is not being freed."

4.The agent reads main.cpp, formulates the fix, and updates the file automatically.

## Tech Stack
​- Core Languages: Python, C++
​- Packaging & Tooling: Astral uv
​- Architecture: ReAct Agent / Tool Calling Workflow