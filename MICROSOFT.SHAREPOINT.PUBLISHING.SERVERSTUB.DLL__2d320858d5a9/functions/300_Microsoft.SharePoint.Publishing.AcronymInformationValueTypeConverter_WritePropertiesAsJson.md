# Microsoft.SharePoint.Publishing.AcronymInformationValueTypeConverter::WritePropertiesAsJson

- ea: `0x300`
- end: `0x375`
- name: `Microsoft.SharePoint.Publishing.AcronymInformationValueTypeConverter::WritePropertiesAsJson`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x300`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldarg.2
0x301  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation
0x306  stloc.0
0x307  ldloc.0
0x308  brtrue.s loc_30B
0x30a  ret
0x30b  ldarg.0
0x30c  ldarg.1
0x30d  ldarg.2
0x30e  ldarg.3
0x30f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x314  ldarg.1
0x315  ldstr    aAcronym// "Acronym"
0x31a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x31f  ldarg.1
0x320  ldloc.0
0x321  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation::get_Acronym()
0x326  ldarg.3
0x327  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x32c  ldarg.1
0x32d  ldstr    aColor// "Color"
0x332  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x337  ldarg.1
0x338  ldloc.0
0x339  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation::get_Color()
0x33e  ldarg.3
0x33f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x344  ldarg.1
0x345  ldstr    aLcid// "Lcid"
0x34a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x34f  ldarg.1
0x350  ldloc.0
0x351  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation::get_Lcid()
0x356  ldarg.3
0x357  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35c  ldarg.1
0x35d  ldstr    aText// "Text"
0x362  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x367  ldarg.1
0x368  ldloc.0
0x369  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation::get_Text()
0x36e  ldarg.3
0x36f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x374  ret
```
