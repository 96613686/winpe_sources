# Microsoft.SharePoint.Spx.WebSite.Controls.MsnStockService::FindSymbolXml

- ea: `0x14820`
- end: `0x14871`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MsnStockService::FindSymbolXml`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7df0`
- `0x14820`

## string_xrefs

- `0x1483a`: `StockServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0x14820  ldarg.0
0x14821  brfalse.s loc_1486F
0x14823  ldarg.0
0x14824  callvirt instance string [mscorlib]System.String::Trim()
0x14829  starg.s  0
0x1482b  ldarg.0
0x1482c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14831  brfalse.s loc_1486F
0x14833  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x14838  stloc.0
0x14839  ldloc.0
0x1483a  ldstr    aStockserviceur// "StockServiceUrl"
0x1483f  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0x14844  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x14849  pop
0x1484a  ldloc.0
0x1484b  ldstr    aStocksearchAsp// "StockSearch.aspx?findsymbol="
0x14850  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x14855  pop
0x14856  ldloc.0
0x14857  ldarg.0
0x14858  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0x1485d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x14862  pop
0x14863  ldloc.0
0x14864  callvirt instance string [mscorlib]System.Object::ToString()
0x14869  call     string Microsoft.SharePoint.Spx.WebSite.Controls.HtmlUtility::GetWebData(string url)
0x1486e  ret
0x1486f  ldnull
0x14870  ret
```
