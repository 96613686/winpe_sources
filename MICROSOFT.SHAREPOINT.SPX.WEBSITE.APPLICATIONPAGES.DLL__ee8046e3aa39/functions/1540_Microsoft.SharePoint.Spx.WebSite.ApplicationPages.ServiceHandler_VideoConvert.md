# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::VideoConvert

- ea: `0x1540`
- end: `0x1562`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::VideoConvert`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xb50`

## callees

- `0x2ad0`
- `0x32f0`

## pseudocode

```c

```

## disassembly

```asm
0x1540  ldarg.0
0x1541  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x1546  ldstr    aStrvideoinput// "strVideoInput"
0x154b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1550  stloc.0
0x1551  ldloc.0
0x1552  call     class Microsoft.SharePoint.Spx.WebSite.VideoConverter.Video Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderManager::FindVideo(string input)
0x1557  stloc.1
0x1558  ldloc.0
0x1559  ldloc.1
0x155a  call     string Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider::GenerateEmbedHtml(string strEmbedCode, class Microsoft.SharePoint.Spx.WebSite.VideoConverter.Video v)
0x155f  stloc.0
0x1560  ldloc.0
0x1561  ret
```
