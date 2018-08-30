## Command

```bash
az appservice plan create --name wk-azure-mvc --resource-group wk-azure --sku FREE
az webapp create --name wk-azure-mvc --resource-group wk-azure --plan wk-azure-mvc
az webapp deployment source config-local-git -n wk-azure-mvc -g wk-azure --query [url] -o tsv

az webapp deployment user set --user-name "" --password ""
set giturl (az webapp deployment source config-local-git -n wk-azure-mvc -g wk-azure --query [url] -o tsv)
git remote add azure $giturl
git push azure master
```