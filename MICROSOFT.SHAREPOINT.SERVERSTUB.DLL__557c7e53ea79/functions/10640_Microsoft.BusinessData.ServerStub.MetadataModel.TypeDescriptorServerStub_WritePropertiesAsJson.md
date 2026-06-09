# Microsoft.BusinessData.ServerStub.MetadataModel.TypeDescriptorServerStub::WritePropertiesAsJson

- ea: `0x10640`
- end: `0x10777`
- name: `Microsoft.BusinessData.ServerStub.MetadataModel.TypeDescriptorServerStub::WritePropertiesAsJson`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10640`

## string_xrefs

- `0x10655`: `ContainsReadOnly`
- `0x10661`: `ContainsReadOnly`
- `0x1066c`: `ContainsReadOnly`
- `0x10684`: `ContainsReadOnly`
- `0x106c9`: `IsReadOnly`
- `0x106d5`: `IsReadOnly`
- `0x106e0`: `IsReadOnly`
- `0x106f8`: `IsReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x10640  ldarg.2
0x10641  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.MetadataModel.ClientOM.TypeDescriptor
0x10646  stloc.0
0x10647  ldloc.0
0x10648  brtrue.s loc_1064B
0x1064a  ret
0x1064b  ldarg.0
0x1064c  ldarg.1
0x1064d  ldarg.2
0x1064e  ldarg.3
0x1064f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10654  ldarg.0
0x10655  ldstr    aContainsreadon// "ContainsReadOnly"
0x1065a  ldarg.3
0x1065b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10660  ldarg.1
0x10661  ldstr    aContainsreadon// "ContainsReadOnly"
0x10666  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1066b  ldarg.3
0x1066c  ldstr    aContainsreadon// "ContainsReadOnly"
0x10671  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x10676  ldarg.1
0x10677  ldloc.0
0x10678  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.MetadataModel.ClientOM.TypeDescriptor::get_ContainsReadOnly()
0x1067d  ldarg.3
0x1067e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10683  ldarg.3
0x10684  ldstr    aContainsreadon// "ContainsReadOnly"
0x10689  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x1068e  ldarg.0
0x1068f  ldstr    aIscollection// "IsCollection"
0x10694  ldarg.3
0x10695  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1069a  ldarg.1
0x1069b  ldstr    aIscollection// "IsCollection"
0x106a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x106a5  ldarg.3
0x106a6  ldstr    aIscollection// "IsCollection"
0x106ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x106b0  ldarg.1
0x106b1  ldloc.0
0x106b2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.MetadataModel.ClientOM.TypeDescriptor::get_IsCollection()
0x106b7  ldarg.3
0x106b8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x106bd  ldarg.3
0x106be  ldstr    aIscollection// "IsCollection"
0x106c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x106c8  ldarg.0
0x106c9  ldstr    aIsreadonly// "IsReadOnly"
0x106ce  ldarg.3
0x106cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x106d4  ldarg.1
0x106d5  ldstr    aIsreadonly// "IsReadOnly"
0x106da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x106df  ldarg.3
0x106e0  ldstr    aIsreadonly// "IsReadOnly"
0x106e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x106ea  ldarg.1
0x106eb  ldloc.0
0x106ec  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.MetadataModel.ClientOM.TypeDescriptor::get_IsReadOnly()
0x106f1  ldarg.3
0x106f2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x106f7  ldarg.3
0x106f8  ldstr    aIsreadonly// "IsReadOnly"
0x106fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x10702  ldarg.0
0x10703  ldstr    aName// "Name"
0x10708  ldarg.3
0x10709  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1070e  ldarg.1
0x1070f  ldstr    aName// "Name"
0x10714  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x10719  ldarg.3
0x1071a  ldstr    aName// "Name"
0x1071f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x10724  ldarg.1
0x10725  ldloc.0
0x10726  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.MetadataModel.ClientOM.TypeDescriptor::get_Name()
0x1072b  ldarg.3
0x1072c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10731  ldarg.3
0x10732  ldstr    aName// "Name"
0x10737  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x1073c  ldarg.0
0x1073d  ldstr    aTypename// "TypeName"
0x10742  ldarg.3
0x10743  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10748  ldarg.1
0x10749  ldstr    aTypename// "TypeName"
0x1074e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x10753  ldarg.3
0x10754  ldstr    aTypename// "TypeName"
0x10759  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x1075e  ldarg.1
0x1075f  ldloc.0
0x10760  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.BusinessData.MetadataModel.ClientOM.TypeDescriptor::get_TypeName()
0x10765  ldarg.3
0x10766  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1076b  ldarg.3
0x1076c  ldstr    aTypename// "TypeName"
0x10771  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x10776  ret
```
