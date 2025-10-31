# Rust Playground

**DRAFT** 

This repository contains (very simple, at least initially) sample code and setup instruction to play with rust.

## Using VS Code and devcontainers

Ideally, create a separate profile and install the following extensions:

- "Dev Containers" (`ms-vscode-remote.remote-containers`)

In the root folder of your project, add a folder `.devcontainer` and, within that folder, create a file `devcontainer.json` with content similar to this

```json
{
  "name": "rust",
  "image": "mcr.microsoft.com/devcontainers/rust:2-1",
  "customizations": {
    "vscode": {
      "extensions": [
        "rust-lang.rust-analyzer",
        "vadimcn.vscode-lldb"
      ]
    }
  }
}
```

> See also [./sample.devcontainer.json]

## Using WSL and VS Code

Assuming we're using Ubuntu-24.04 for our instance, install rust:

```bash
sudo apt install -y rust-all
```

I prefer to keep separate profiles, generally one per stack; in this case, since I'm using WSL, I need a profile with just extensions for wsl installed, i.e., `ms-vscode-remote.remote-wsl`.

To have a basic VS Code setup for rust, in folder `.vscode`, we can create `extensions.json` with this content:

```json
{
  "recommendations": [
    "rust-lang.rust-analyzer",
    "vadimcn.vscode-lldb"
  ],
  "unwantedRecommendations": [
  ]
}
```

So when VS Code starts, it will offer to install the recommended extensions.

> Similarly, any unwanted extension can be added to `unwantedRecommendations`.

## References

- [Rust](https://rust-lang.org/)
- [Rust in Visual Studio Code](https://code.visualstudio.com/docs/languages/rust)
- [devcontainer README file](https://github.com/devcontainers/images/blob/main/src/rust/README.md)