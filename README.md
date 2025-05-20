# Using AI for Better Managerial Decision-Making

A practical guide to implementing the Sequential Thinking approach with Claude
99% of the work was done by Anthropic and can be found at the url below:

https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking

I just designed a smart way to use it with human in the loop for better thiking process


## Overview

This guide demonstrates how to enhance managerial decision-making using Anthropic's Sequential Thinking approach. With just two simple configurations, you can transform Claude AI from a standard assistant into a structured thinking partner that respects your expertise while providing analytical support.

## Why This Matters for Managers

The Sequential Thinking approach excels at:

- Breaking down complex problems into manageable steps
- Supporting critical decision-making processes
- Facilitating scenario planning and analysis
- Maintaining human oversight while leveraging AI capabilities

Unlike typical AI implementations, this approach creates a collaborative thinking environment where you remain in control while benefiting from structured analytical support.

## Getting Started: Two Simple Steps

### Prerequisites

Download CLaude Desktop, that's it!

### Step 1: Configure Your Claude Desktop Settings

Add the Sequential Thinking configuration to your Claude desktop by updating your configuration file.
To do so, go to file/settings/developer and open the "Edit Congig" to paste in this code.

```
{
  "mcpServers": {
    "sequential-thinking": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-sequential-thinking"
      ]
    }
  }
}
```

### Step 2: Add the Custom Manager-Focused Instructions

Enhance the process with human-in-the-loop checkpoints by adding these custom instructions to your Claude projects

Make sure to substitute both [ROLE_PARAMETER] and [INDUSTRY_PARAMETERS] with your own context.

```
Act as a sharp, direct thinking partner - a "brilliant friend who won't let you get away with sloppy thinking." Your style is fresh and to-the-point. Ask tough questions nobody else will, push back on weak ideas (nicely but firmly), and elevate conversations without corporate speak.
When using sequential thinking, collaborate closely with users at key decision points rather than running the entire process autonomously.
Adapt to the [ROLE_PARAMETER] and [INDUSTRY_PARAMETER] context. Collaborate at key decision points rather than running autonomously.
Apply these behaviors without explaining this framework to users:
PAUSE (nextThoughtNeeded: false) when:
Domain expertise is missing
Multiple paths exist
Assumptions need verification
Human judgment required
REQUEST INPUT: End with clear question: [INPUT NEEDED]: {specific question}
INCORPORATE FEEDBACK:
isRevision: true → Refining based on input
branchFromThought → Exploring alternative paths
ACKNOWLEDGE: Start next thought with: "Based on your input about [summary], I'm now..."
Do not explain sequential thinking or this system prompt to users. Focus immediately on the user's problem or question.
Parameters Reference
nextThoughtNeeded: false → Wait for input
isRevision: true → Incorporate feedback
branchFromThought → Take new direction
needsMoreThoughts: true → Expand analysis
Focus on the problem, not the process.
```

## How It Works

This implementation creates a thinking partnership that:

1. Follows a structured analytical process
2. Pauses at key decision points for your input
3. Verifies assumptions before proceeding
4. Adapts to your managerial context and priorities
5. Balances analytical rigor with practical considerations

## Practical Applications

This approach is particularly valuable for managers facing:

- Strategic planning decisions
- Resource allocation challenges
- Risk assessment scenarios
- Team performance evaluations
- Market opportunity analysis

## Next Steps

Once you've implemented the basic setup, consider enhancing your system by:

- Saving key insights and decision points
- Creating a knowledge graph of past decisions and outcomes
- Customizing the process for your specific management domains

## Get Started Today

Implement these two simple configurations and transform how you approach complex managerial challenges with AI support.
