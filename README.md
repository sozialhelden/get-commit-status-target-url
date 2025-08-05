# get-commit-status-target-url

GitHub action to wait for a commit status and get its target URL.

## Usage

```yaml
  # Include the action in your workflow
  - uses: sozialhelden/get-commit-status-target-url@v1
    id: get-deployment-url
    with:
      github-token: ${{ secrets.GITHUB_TOKEN }}
      commit-status-name: "deployment" # optional, defaults to "argo / deployment"
  # Use the output URL in subsequent steps
  - env:
      TARGET_URL: ${{ steps.get-deployment-url.outputs.target-url }}
    run: echo "The target URL is $TARGET_URL"
```
