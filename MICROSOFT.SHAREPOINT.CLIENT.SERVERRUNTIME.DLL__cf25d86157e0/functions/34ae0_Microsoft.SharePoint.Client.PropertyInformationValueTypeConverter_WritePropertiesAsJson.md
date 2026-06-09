# Microsoft.SharePoint.Client.PropertyInformationValueTypeConverter::WritePropertiesAsJson

- ea: `0x34ae0`
- end: `0x34b6d`
- name: `Microsoft.SharePoint.Client.PropertyInformationValueTypeConverter::WritePropertiesAsJson`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x430`
- `0x8b30`
- `0x8b90`
- `0x8bf0`
- `0x8c50`
- `0x8c90`
- `0xf420`
- `0x10040`
- `0x132d0`
- `0x34ae0`

## string_xrefs

- `0x34b55`: `ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x34ae0  ldarg.2
0x34ae1  isinst   Microsoft.SharePoint.Client.PropertyInformation
0x34ae6  stloc.0
0x34ae7  ldloc.0
0x34ae8  brtrue.s loc_34AEB
0x34aea  ret
0x34aeb  ldarg.0
0x34aec  ldarg.1
0x34aed  ldarg.2
0x34aee  ldarg.3
0x34aef  call     instance void Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x34af4  ldarg.1
0x34af5  ldstr    aExcludefromdef// "ExcludeFromDefaultRetrieval"
0x34afa  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x34aff  ldarg.1
0x34b00  ldloc.0
0x34b01  callvirt instance bool Microsoft.SharePoint.Client.PropertyInformation::get_ExcludeFromDefaultRetrieval()
0x34b06  ldarg.3
0x34b07  call     void Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class Microsoft.SharePoint.Client.JsonWriter writer, bool b, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x34b0c  ldarg.1
0x34b0d  ldstr    aIsbeta// "IsBeta"
0x34b12  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x34b17  ldarg.1
0x34b18  ldloc.0
0x34b19  callvirt instance bool Microsoft.SharePoint.Client.PropertyInformation::get_IsBeta()
0x34b1e  ldarg.3
0x34b1f  call     void Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class Microsoft.SharePoint.Client.JsonWriter writer, bool b, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x34b24  ldarg.1
0x34b25  ldstr    aName// "Name"
0x34b2a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x34b2f  ldarg.1
0x34b30  ldloc.0
0x34b31  callvirt instance string Microsoft.SharePoint.Client.PropertyInformation::get_Name()
0x34b36  ldarg.3
0x34b37  call     void Microsoft.SharePoint.Client.DataConverter::WriteString(class Microsoft.SharePoint.Client.JsonWriter writer, string value, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x34b3c  ldarg.1
0x34b3d  ldstr    aPropertytypefu// "PropertyTypeFullName"
0x34b42  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x34b47  ldarg.1
0x34b48  ldloc.0
0x34b49  callvirt instance string Microsoft.SharePoint.Client.PropertyInformation::get_PropertyTypeFullName()
0x34b4e  ldarg.3
0x34b4f  call     void Microsoft.SharePoint.Client.DataConverter::WriteString(class Microsoft.SharePoint.Client.JsonWriter writer, string value, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x34b54  ldarg.1
0x34b55  ldstr    aReadonly// "ReadOnly"
0x34b5a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x34b5f  ldarg.1
0x34b60  ldloc.0
0x34b61  callvirt instance bool Microsoft.SharePoint.Client.PropertyInformation::get_ReadOnly()
0x34b66  ldarg.3
0x34b67  call     void Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class Microsoft.SharePoint.Client.JsonWriter writer, bool b, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x34b6c  ret
```
