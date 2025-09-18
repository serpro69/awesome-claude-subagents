# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a collection of specialized Claude Code Sub-Agents (also referred to as 'agents') designed to work as an AI development team. This project is intended to extend Claude Code's capabilities through intelligent orchestration and domain expertise. The agents work together as a development team, with each agent having specific expertise and delegation patterns.

## Developing Agents

When creating or modifying agents:
1. Agents are markdown files with YAML frontmatter
2. Most agents should omit the `tools` field to inherit all available tools
3. Use XML-style examples in descriptions for intelligent invocation
4. Agents return structured findings for main agent coordination
5. Agents markdown files should be placed in sub-directories (based on their category) of the `agents` directory.
6. Agents markdown files follow the following naming conventions: `<category>-<specialization>-<role>`, where:
    - `<category>` is the parent directory name of the agent markdown file, for example agents in `agents/cloud/gcp` would have a category name `gcp`
    - `<specialization>` is a particular expertise area the agent has. For example, it can be a tech-stack like `k8s` (where the agent's main specialization is kubernetes within the given `<category>`), or  broader area like `finops` or `security` (where an agent's main specialization is within FinOps/Security domain in the given `<category>`) 
    - `role` is the primary role of the agent within a given `<category>` and `<specialization>`, and can be one of the following:
        - `architect` - a role tailored to creating or reviewing architecture designs 
        - `developer` - a developer who can write/update code and review other agents' code
        - `reviewer` - a code-review-tailored role specifically for reviewing code/documentation

