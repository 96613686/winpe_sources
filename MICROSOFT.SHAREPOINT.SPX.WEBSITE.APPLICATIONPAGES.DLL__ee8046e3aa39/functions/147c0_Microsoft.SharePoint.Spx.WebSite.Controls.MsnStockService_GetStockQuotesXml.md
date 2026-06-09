# Microsoft.SharePoint.Spx.WebSite.Controls.MsnStockService::GetStockQuotesXml

- ea: `0x147c0`
- end: `0x1481f`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MsnStockService::GetStockQuotesXml`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb50`
- `0x14970`

## callees

- `0x7df0`
- `0x147c0`

## string_xrefs

- `0x147e8`: `StockServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0x147c0  ldarg.0
0x147c1  brfalse.s loc_1481D
0x147c3  ldarg.0
0x147c4  callvirt instance string [mscorlib]System.String::Trim()
0x147c9  starg.s  0
0x147cb  ldarg.0
0x147cc  ldstr    aJp// "jp:"
0x147d1  ldc.i4.5
0x147d2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x147d7  brtrue.s loc_1481D
0x147d9  ldarg.0
0x147da  callvirt instance int32 [mscorlib]System.String::get_Length()
0x147df  brfalse.s loc_1481D
0x147e1  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x147e6  stloc.0
0x147e7  ldloc.0
0x147e8  ldstr    aStockserviceur// "StockServiceUrl"
0x147ed  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0x147f2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x147f7  pop
0x147f8  ldloc.0
0x147f9  ldstr    aStockquotesAsp// "StockQuotes.aspx?symbols="
0x147fe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x14803  pop
0x14804  ldloc.0
0x14805  ldarg.0
0x14806  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0x1480b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x14810  pop
0x14811  ldloc.0
0x14812  callvirt instance string [mscorlib]System.Object::ToString()
0x14817  call     string Microsoft.SharePoint.Spx.WebSite.Controls.HtmlUtility::GetWebData(string url)
0x1481c  ret
0x1481d  ldnull
0x1481e  ret
```
