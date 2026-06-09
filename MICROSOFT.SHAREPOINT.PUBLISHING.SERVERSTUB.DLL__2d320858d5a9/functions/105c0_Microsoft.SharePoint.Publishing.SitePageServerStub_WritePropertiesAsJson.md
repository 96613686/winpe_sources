# Microsoft.SharePoint.Publishing.SitePageServerStub::WritePropertiesAsJson

- ea: `0x105c0`
- end: `0x10683`
- name: `Microsoft.SharePoint.Publishing.SitePageServerStub::WritePropertiesAsJson`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf660`
- `0x105c0`

## pseudocode

```c

```

## disassembly

```asm
0x105c0  ldarg.2
0x105c1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x105c6  stloc.0
0x105c7  ldloc.0
0x105c8  brtrue.s loc_105CB
0x105ca  ret
0x105cb  ldarg.0
0x105cc  ldarg.1
0x105cd  ldarg.2
0x105ce  ldarg.3
0x105cf  call     instance void Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter writer, object target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x105d4  ldarg.0
0x105d5  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x105da  ldarg.3
0x105db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x105e0  ldarg.1
0x105e1  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x105e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x105eb  ldarg.3
0x105ec  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x105f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x105f6  ldarg.1
0x105f7  ldloc.0
0x105f8  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_AlternativeUrlMap()
0x105fd  ldarg.3
0x105fe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10603  ldarg.3
0x10604  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x10609  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x1060e  ldarg.0
0x1060f  ldstr    aCanvascontent1// "CanvasContent1"
0x10614  ldarg.3
0x10615  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1061a  ldarg.1
0x1061b  ldstr    aCanvascontent1// "CanvasContent1"
0x10620  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x10625  ldarg.3
0x10626  ldstr    aCanvascontent1// "CanvasContent1"
0x1062b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x10630  ldarg.1
0x10631  ldloc.0
0x10632  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_CanvasContent1()
0x10637  ldarg.3
0x10638  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1063d  ldarg.3
0x1063e  ldstr    aCanvascontent1// "CanvasContent1"
0x10643  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x10648  ldarg.0
0x10649  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x1064e  ldarg.3
0x1064f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10654  ldarg.1
0x10655  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x1065a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1065f  ldarg.3
0x10660  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x10665  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x1066a  ldarg.1
0x1066b  ldloc.0
0x1066c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_LayoutWebpartsContent()
0x10671  ldarg.3
0x10672  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10677  ldarg.3
0x10678  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x1067d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x10682  ret
```
