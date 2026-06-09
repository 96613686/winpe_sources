# Microsoft.SharePoint.Publishing.ImageRenditionValueTypeConverter::WritePropertiesAsJson

- ea: `0x5080`
- end: `0x513d`
- name: `Microsoft.SharePoint.Publishing.ImageRenditionValueTypeConverter::WritePropertiesAsJson`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5080`

## pseudocode

```c

```

## disassembly

```asm
0x5080  ldarg.2
0x5081  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition
0x5086  stloc.0
0x5087  ldloc.0
0x5088  brtrue.s loc_508B
0x508a  ret
0x508b  ldarg.0
0x508c  ldarg.1
0x508d  ldarg.2
0x508e  ldarg.3
0x508f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5094  ldarg.1
0x5095  ldstr    aGroup// "Group"
0x509a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x509f  ldarg.1
0x50a0  ldloc.0
0x50a1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::get_Group()
0x50a6  ldarg.3
0x50a7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x50ac  ldarg.1
0x50ad  ldstr    aHeight// "Height"
0x50b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x50b7  ldarg.1
0x50b8  ldloc.0
0x50b9  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::get_Height()
0x50be  ldarg.3
0x50bf  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x50c4  ldarg.1
0x50c5  ldstr    aId// "Id"
0x50ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x50cf  ldarg.1
0x50d0  ldloc.0
0x50d1  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::get_Id()
0x50d6  ldarg.3
0x50d7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x50dc  ldarg.1
0x50dd  ldstr    aIdcsom// "IdCsom"
0x50e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x50e7  ldarg.1
0x50e8  ldloc.0
0x50e9  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::get_IdCsom()
0x50ee  ldarg.3
0x50ef  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x50f4  ldarg.1
0x50f5  ldstr    aName// "Name"
0x50fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x50ff  ldarg.1
0x5100  ldloc.0
0x5101  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::get_Name()
0x5106  ldarg.3
0x5107  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x510c  ldarg.1
0x510d  ldstr    aVersion_0// "Version"
0x5112  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5117  ldarg.1
0x5118  ldloc.0
0x5119  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::get_Version()
0x511e  ldarg.3
0x511f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5124  ldarg.1
0x5125  ldstr    aWidth// "Width"
0x512a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x512f  ldarg.1
0x5130  ldloc.0
0x5131  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::get_Width()
0x5136  ldarg.3
0x5137  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x513c  ret
```
