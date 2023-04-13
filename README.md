# QuantCDN Cloud initilisation

Prepare the Action workflow environment ready to interact with Quant Cloud.

## Getting Started

To get started using the action make sure you have the standard workflow structure set up (.github/workflows) create a workflow file iwth the following:

```
name: Initialise Quant Cloud
on:
  push:
    branches:
      - main
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: quantcdn/cloud-init-action@v2.0.0
        env:
          SECTION_K8S_API_URL: "${{ secrets.SECTION_K8S_API_URL }}"
          SECTION_API_TOKEN: "${{ secrets.SECTION_API_TOKEN }}"

```

Replace the placeholders with values for your project, these can be found in the [Quant dashboard](https://docs.quantcdn.io/docs/dashboard).

## Adding secrets

Navigate to your repositories Settings page and find **Secrets**. Once there click on new secret, enter **SECTION_API_TOKEN** as the secret name and paste your provided Quant API token.

You can learn more about [secrets](https://docs.github.com/en/actions/reference/encrypted-secrets) and [actions](https://docs.github.com/en/actions).