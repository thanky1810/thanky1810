# Hi there! 👋 I'm [Francis]  

![JavaScript](https://img.shields.io/badge/JavaScript-Expert-yellow?style=flat&logo=javascript)
![Node.js](https://img.shields.io/badge/Node.js-Developer-green?style=flat&logo=node.js)
![React.js](https://img.shields.io/badge/React.js-Frontend-blue?style=flat&logo=react)

Welcome to my GitHub! I'm a passionate developer from VietNam🚀.

---

## 🚀 **Skills & Tools**

### Languages & Frameworks
- **JavaScript** | **Node.js** | **React.js** | **HTML/CSS**

### DevOps & Tools


### Databases
**MySQL**

---

## 🛠️ **Projects**



## 🌐 **Connect with Me**



## 🔧 **Daily Tools**
![Visual Studio Code](https://img.shields.io/badge/Editor-VSCode-blue?style=flat&logo=visual-studio-code)


---
name: GitHub Snake Game

on:
  # Schedule the workflow to run daily at midnight UTC
  schedule:
    - cron: "0 0 * * *"
  # Allow manual triggering of the workflow
  workflow_dispatch:
  # Trigger the workflow on pushes to the main branch
  push:
    branches:
      - main
jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      # Step 1: Checkout the repository
      - name: Checkout Repository
        uses: actions/checkout@v3
      # Step 2: Generate the snake animations
      - name: Generate GitHub Contributions Snake Animations
        uses: Platane/snk@v3
        with:
          # GitHub username to generate the animation for
          github_user_name: ${{ github.repository_owner }}
          # Define the output files and their configurations
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
            dist/ocean.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      # Step 3: Deploy the generated files to the 'output' branch
      - name: Deploy to Output Branch
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
          publish_branch: output
          # Optionally, you can set a custom commit message
          commit_message: "Update snake animation [skip ci]"

Thank you for visiting! 💻 Feel free to fork, star, or collaborate on any project!

---


