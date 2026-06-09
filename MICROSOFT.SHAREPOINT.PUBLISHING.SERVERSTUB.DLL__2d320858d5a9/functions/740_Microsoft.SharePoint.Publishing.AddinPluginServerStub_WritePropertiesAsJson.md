# Microsoft.SharePoint.Publishing.AddinPluginServerStub::WritePropertiesAsJson

- ea: `0x740`
- end: `0x803`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::WritePropertiesAsJson`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x740`

## pseudocode

```c

```

## disassembly

```asm
0x740  ldarg.2
0x741  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin
0x746  stloc.0
0x747  ldloc.0
0x748  brtrue.s loc_74B
0x74a  ret
0x74b  ldarg.0
0x74c  ldarg.1
0x74d  ldarg.2
0x74e  ldarg.3
0x74f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x754  ldarg.0
0x755  ldstr    aDescription// "Description"
0x75a  ldarg.3
0x75b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x760  ldarg.1
0x761  ldstr    aDescription// "Description"
0x766  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x76b  ldarg.3
0x76c  ldstr    aDescription// "Description"
0x771  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x776  ldarg.1
0x777  ldloc.0
0x778  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Description()
0x77d  ldarg.3
0x77e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x783  ldarg.3
0x784  ldstr    aDescription// "Description"
0x789  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x78e  ldarg.0
0x78f  ldstr    aMarkup// "Markup"
0x794  ldarg.3
0x795  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x79a  ldarg.1
0x79b  ldstr    aMarkup// "Markup"
0x7a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7a5  ldarg.3
0x7a6  ldstr    aMarkup// "Markup"
0x7ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x7b0  ldarg.1
0x7b1  ldloc.0
0x7b2  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Markup()
0x7b7  ldarg.3
0x7b8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7bd  ldarg.3
0x7be  ldstr    aMarkup// "Markup"
0x7c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x7c8  ldarg.0
0x7c9  ldstr    aTitle// "Title"
0x7ce  ldarg.3
0x7cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7d4  ldarg.1
0x7d5  ldstr    aTitle// "Title"
0x7da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7df  ldarg.3
0x7e0  ldstr    aTitle// "Title"
0x7e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x7ea  ldarg.1
0x7eb  ldloc.0
0x7ec  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Title()
0x7f1  ldarg.3
0x7f2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7f7  ldarg.3
0x7f8  ldstr    aTitle// "Title"
0x7fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x802  ret
```
