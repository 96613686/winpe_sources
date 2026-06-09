# Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::WritePropertiesAsJson

- ea: `0x2060`
- end: `0x20a5`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::WritePropertiesAsJson`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2060`

## pseudocode

```c

```

## disassembly

```asm
0x2060  ldarg.2
0x2061  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse
0x2066  stloc.0
0x2067  ldloc.0
0x2068  brtrue.s loc_206B
0x206a  ret
0x206b  ldarg.0
0x206c  ldarg.1
0x206d  ldarg.2
0x206e  ldarg.3
0x206f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2074  ldarg.1
0x2075  ldstr    aSitestatus// "SiteStatus"
0x207a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x207f  ldarg.1
0x2080  ldloc.0
0x2081  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteStatus [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse::get_SiteStatus()
0x2086  ldarg.3
0x2087  call     T0x2B00000B
0x208c  ldarg.1
0x208d  ldstr    aSiteurl// "SiteUrl"
0x2092  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2097  ldarg.1
0x2098  ldloc.0
0x2099  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse::get_SiteUrl()
0x209e  ldarg.3
0x209f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20a4  ret
```
