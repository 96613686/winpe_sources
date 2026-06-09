# Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::WritePropertiesAsJson

- ea: `0x11900`
- end: `0x11945`
- name: `Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::WritePropertiesAsJson`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11900`

## string_xrefs

- `0x11915`: `LastVersionCreated`
- `0x1192d`: `LastVersionCreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0x11900  ldarg.2
0x11901  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo
0x11906  stloc.0
0x11907  ldloc.0
0x11908  brtrue.s loc_1190B
0x1190a  ret
0x1190b  ldarg.0
0x1190c  ldarg.1
0x1190d  ldarg.2
0x1190e  ldarg.3
0x1190f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11914  ldarg.1
0x11915  ldstr    aLastversioncre// "LastVersionCreated"
0x1191a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1191f  ldarg.1
0x11920  ldloc.0
0x11921  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo::get_LastVersionCreated()
0x11926  ldarg.3
0x11927  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1192c  ldarg.1
0x1192d  ldstr    aLastversioncre_0// "LastVersionCreatedBy"
0x11932  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x11937  ldarg.1
0x11938  ldloc.0
0x11939  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo::get_LastVersionCreatedBy()
0x1193e  ldarg.3
0x1193f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11944  ret
```
