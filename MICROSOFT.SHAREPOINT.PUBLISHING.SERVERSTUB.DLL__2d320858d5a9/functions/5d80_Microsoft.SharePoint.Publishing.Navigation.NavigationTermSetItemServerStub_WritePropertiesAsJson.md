# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::WritePropertiesAsJson

- ea: `0x5d80`
- end: `0x5e7d`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::WritePropertiesAsJson`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7040`
- `0x80c0`

## callees

- `0x5d80`

## string_xrefs

- `0x5dcf`: `IsReadOnly`
- `0x5ddb`: `IsReadOnly`
- `0x5de6`: `IsReadOnly`
- `0x5dfe`: `IsReadOnly`
- `0x5e09`: `LinkType`
- `0x5e15`: `LinkType`
- `0x5e20`: `LinkType`
- `0x5e38`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x5d80  ldarg.2
0x5d81  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem
0x5d86  stloc.0
0x5d87  ldloc.0
0x5d88  brtrue.s loc_5D8B
0x5d8a  ret
0x5d8b  ldarg.0
0x5d8c  ldarg.1
0x5d8d  ldarg.2
0x5d8e  ldarg.3
0x5d8f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d94  ldarg.0
0x5d95  ldstr    aId// "Id"
0x5d9a  ldarg.3
0x5d9b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5da0  ldarg.1
0x5da1  ldstr    aId// "Id"
0x5da6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5dab  ldarg.3
0x5dac  ldstr    aId// "Id"
0x5db1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5db6  ldarg.1
0x5db7  ldloc.0
0x5db8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_Id()
0x5dbd  ldarg.3
0x5dbe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5dc3  ldarg.3
0x5dc4  ldstr    aId// "Id"
0x5dc9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5dce  ldarg.0
0x5dcf  ldstr    aIsreadonly// "IsReadOnly"
0x5dd4  ldarg.3
0x5dd5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5dda  ldarg.1
0x5ddb  ldstr    aIsreadonly// "IsReadOnly"
0x5de0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5de5  ldarg.3
0x5de6  ldstr    aIsreadonly// "IsReadOnly"
0x5deb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5df0  ldarg.1
0x5df1  ldloc.0
0x5df2  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_IsReadOnly()
0x5df7  ldarg.3
0x5df8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5dfd  ldarg.3
0x5dfe  ldstr    aIsreadonly// "IsReadOnly"
0x5e03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5e08  ldarg.0
0x5e09  ldstr    aLinktype// "LinkType"
0x5e0e  ldarg.3
0x5e0f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e14  ldarg.1
0x5e15  ldstr    aLinktype// "LinkType"
0x5e1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5e1f  ldarg.3
0x5e20  ldstr    aLinktype// "LinkType"
0x5e25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5e2a  ldarg.1
0x5e2b  ldloc.0
0x5e2c  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_LinkType()
0x5e31  ldarg.3
0x5e32  call     T0x2B000013
0x5e37  ldarg.3
0x5e38  ldstr    aLinktype// "LinkType"
0x5e3d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5e42  ldarg.0
0x5e43  ldstr    aTaxonomyname// "TaxonomyName"
0x5e48  ldarg.3
0x5e49  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e4e  ldarg.1
0x5e4f  ldstr    aTaxonomyname// "TaxonomyName"
0x5e54  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5e59  ldarg.3
0x5e5a  ldstr    aTaxonomyname// "TaxonomyName"
0x5e5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5e64  ldarg.1
0x5e65  ldloc.0
0x5e66  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::get_TaxonomyName()
0x5e6b  ldarg.3
0x5e6c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e71  ldarg.3
0x5e72  ldstr    aTaxonomyname// "TaxonomyName"
0x5e77  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5e7c  ret
```
