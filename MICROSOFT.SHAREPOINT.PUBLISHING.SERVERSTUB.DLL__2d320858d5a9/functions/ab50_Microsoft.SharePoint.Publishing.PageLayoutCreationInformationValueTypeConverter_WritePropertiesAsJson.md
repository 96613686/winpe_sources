# Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::WritePropertiesAsJson

- ea: `0xab50`
- end: `0xabc5`
- name: `Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::WritePropertiesAsJson`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xab50`

## string_xrefs

- `0xab95`: `NewPageLayoutEditablePath`
- `0xabad`: `NewPageLayoutNameWithoutExtension`

## pseudocode

```c

```

## disassembly

```asm
0xab50  ldarg.2
0xab51  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation
0xab56  stloc.0
0xab57  ldloc.0
0xab58  brtrue.s loc_AB5B
0xab5a  ret
0xab5b  ldarg.0
0xab5c  ldarg.1
0xab5d  ldarg.2
0xab5e  ldarg.3
0xab5f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab64  ldarg.1
0xab65  ldstr    aAssociatedcont// "AssociatedContentTypeId"
0xab6a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xab6f  ldarg.1
0xab70  ldloc.0
0xab71  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_AssociatedContentTypeId()
0xab76  ldarg.3
0xab77  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab7c  ldarg.1
0xab7d  ldstr    aMasterpageurl// "MasterPageUrl"
0xab82  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xab87  ldarg.1
0xab88  ldloc.0
0xab89  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_MasterPageUrl()
0xab8e  ldarg.3
0xab8f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xab94  ldarg.1
0xab95  ldstr    aNewpagelayoute// "NewPageLayoutEditablePath"
0xab9a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xab9f  ldarg.1
0xaba0  ldloc.0
0xaba1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_NewPageLayoutEditablePath()
0xaba6  ldarg.3
0xaba7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabac  ldarg.1
0xabad  ldstr    aNewpagelayoutn// "NewPageLayoutNameWithoutExtension"
0xabb2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xabb7  ldarg.1
0xabb8  ldloc.0
0xabb9  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::get_NewPageLayoutNameWithoutExtension()
0xabbe  ldarg.3
0xabbf  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xabc4  ret
```
