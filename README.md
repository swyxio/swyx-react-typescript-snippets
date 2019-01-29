# swyx-react-typescript-snippets

---

This extension contains code snippets for React with Typescript (optionally, with Styled-Components). It is a fork of https://github.com/infeng/vscode-react-typescript made by swyx.

It contains no class component APIs, assumes you use synthetic default imports, has hooks and subjectively better prop scaffolding.

It does a bit more based on the principle that it is easier to delete than to type, and so that we have just 3 easy to remember snippets: `rfc`, `rhc`, `rsc`.

Because [the popular styled components snippets extension](https://github.com/lXSPandora/vscode-styled-components-snippets) only works for javascript 🙄, we also include an import snippet `imrsc`.

## Installation

In order to install an extension you need to launch the Command Pallete (Ctrl + Shift + P or Cmd + Shift + P) and type Extensions.
There you have either the option to show the already installed snippets or install new ones.

Launch VS Code Quick Open (Ctrl + P or Cmd + P), paste the following command, and press enter.

`ext install swyx-react-typescript-snippets`

Alternatively you can open the extensions panel and search for 'swyx-react-typescript-snippets'.

## Supported languages (file extensions)

- TypeScript (.ts)
- TypeScript React (.tsx)

## Snippets

Below is a list of all available snippets and the triggers of each one. The **⇥** means the `TAB` key.

|  Trigger | Content                                        |
| -------: | ---------------------------------------------- |
|   `rfc→` | `create a react function component (no hooks)` |
|   `rhc→` | `create a react hooks component`               |
|   `rsc→` | `create a react styled component (no hooks)`   |
| `imrsc→` | `import react and styled component`            |

```json
{
  "import react and styled components": {
    "prefix": "imrsc",
    "body": [
      "import React from 'react'",
      "import styled from 'styled-components'"
    ],
    "description": "import react and styled components"
  },
  "React Function Component": {
    "prefix": "rfc",
    "body": [
      "export type $1Props = { $2: $3 }",
      "export const $1: React.FC<$1Props> = ({ $2 }) => {",
      "    console.log({ $2 })",
      "    return (",
      "        $0",
      "    )",
      "};",
      "",
      "export default $1;"
    ],
    "description": "Create a React Function Component"
  },
  "React Hooks Component": {
    "prefix": "rhc",
    "body": [
      "export type $1Props = { $2: $3 }",
      "export const $1: React.FC<$1Props> = ({ $2 }) => {",
      "    console.log({ $2 })",
      "    const [${4}, set${4/(.*)/${4:/capitalize}/}] = React.useState($5);",
      "    React.useEffect(() => {}, [])",
      "    return (",
      "        ${0}",
      "    )",
      "};",
      "",
      "export default $1;"
    ],
    "description": "Create a React Hooks Component."
  },
  "React Styled Component": {
    "prefix": "rsc",
    "body": [
      "const StyledDiv = styled('div')`",
      "  border: 3px solid red;",
      "`",
      "export type $1Props = { $2: $3 }",
      "export const $1: React.FC<$1Props> = ({ $2 }) => {",
      "    console.log({ $2 })",
      "    const [${4}, set${4/(.*)/${4:/capitalize}/}] = React.useState($5);",
      "    React.useEffect(() => {}, [])",
      "    return (",
      "        <StyledDiv>",
      "            ${0}",
      "        </StyledDiv>",
      "    )",
      "};",
      "",
      "export default $1;"
    ],
    "description": "Create a Styled React Component."
  }
}
```

## Publishing

`vsce package`

## License

MIT
