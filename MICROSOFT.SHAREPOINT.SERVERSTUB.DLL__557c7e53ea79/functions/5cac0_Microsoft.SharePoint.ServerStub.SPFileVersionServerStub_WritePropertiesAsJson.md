# Microsoft.SharePoint.ServerStub.SPFileVersionServerStub::WritePropertiesAsJson

- ea: `0x5cac0`
- end: `0x5cca5`
- name: `Microsoft.SharePoint.ServerStub.SPFileVersionServerStub::WritePropertiesAsJson`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5cac0`

## string_xrefs

- `0x5cb0f`: `Created`
- `0x5cb1b`: `Created`
- `0x5cb26`: `Created`
- `0x5cb3e`: `Created`
- `0x5cad5`: `CheckInComment`
- `0x5cae1`: `CheckInComment`
- `0x5caec`: `CheckInComment`
- `0x5cb04`: `CheckInComment`

## pseudocode

```c

```

## disassembly

```asm
0x5cac0  ldarg.2
0x5cac1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion
0x5cac6  stloc.0
0x5cac7  ldloc.0
0x5cac8  brtrue.s loc_5CACB
0x5caca  ret
0x5cacb  ldarg.0
0x5cacc  ldarg.1
0x5cacd  ldarg.2
0x5cace  ldarg.3
0x5cacf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cad4  ldarg.0
0x5cad5  ldstr    aCheckincomment_0// "CheckInComment"
0x5cada  ldarg.3
0x5cadb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cae0  ldarg.1
0x5cae1  ldstr    aCheckincomment_0// "CheckInComment"
0x5cae6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5caeb  ldarg.3
0x5caec  ldstr    aCheckincomment_0// "CheckInComment"
0x5caf1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5caf6  ldarg.1
0x5caf7  ldloc.0
0x5caf8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_CheckInComment()
0x5cafd  ldarg.3
0x5cafe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cb03  ldarg.3
0x5cb04  ldstr    aCheckincomment_0// "CheckInComment"
0x5cb09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5cb0e  ldarg.0
0x5cb0f  ldstr    aCreated// "Created"
0x5cb14  ldarg.3
0x5cb15  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cb1a  ldarg.1
0x5cb1b  ldstr    aCreated// "Created"
0x5cb20  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5cb25  ldarg.3
0x5cb26  ldstr    aCreated// "Created"
0x5cb2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5cb30  ldarg.1
0x5cb31  ldloc.0
0x5cb32  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Created()
0x5cb37  ldarg.3
0x5cb38  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cb3d  ldarg.3
0x5cb3e  ldstr    aCreated// "Created"
0x5cb43  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5cb48  ldarg.0
0x5cb49  ldstr    aId_1// "ID"
0x5cb4e  ldarg.3
0x5cb4f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cb54  ldarg.1
0x5cb55  ldstr    aId_1// "ID"
0x5cb5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5cb5f  ldarg.3
0x5cb60  ldstr    aId_1// "ID"
0x5cb65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5cb6a  ldarg.1
0x5cb6b  ldloc.0
0x5cb6c  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_ID()
0x5cb71  ldarg.3
0x5cb72  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cb77  ldarg.3
0x5cb78  ldstr    aId_1// "ID"
0x5cb7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5cb82  ldarg.0
0x5cb83  ldstr    aIscurrentversi// "IsCurrentVersion"
0x5cb88  ldarg.3
0x5cb89  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cb8e  ldarg.1
0x5cb8f  ldstr    aIscurrentversi// "IsCurrentVersion"
0x5cb94  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5cb99  ldarg.3
0x5cb9a  ldstr    aIscurrentversi// "IsCurrentVersion"
0x5cb9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5cba4  ldarg.1
0x5cba5  ldloc.0
0x5cba6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_IsCurrentVersion()
0x5cbab  ldarg.3
0x5cbac  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cbb1  ldarg.3
0x5cbb2  ldstr    aIscurrentversi// "IsCurrentVersion"
0x5cbb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5cbbc  ldarg.0
0x5cbbd  ldstr    aLength// "Length"
0x5cbc2  ldarg.3
0x5cbc3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cbc8  ldarg.1
0x5cbc9  ldstr    aLength// "Length"
0x5cbce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5cbd3  ldarg.3
0x5cbd4  ldstr    aLength// "Length"
0x5cbd9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5cbde  ldarg.1
0x5cbdf  ldloc.0
0x5cbe0  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Length()
0x5cbe5  ldarg.3
0x5cbe6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt64(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int64, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cbeb  ldarg.3
0x5cbec  ldstr    aLength// "Length"
0x5cbf1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5cbf6  ldarg.0
0x5cbf7  ldstr    aSize_0// "Size"
0x5cbfc  ldarg.3
0x5cbfd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cc02  ldarg.1
0x5cc03  ldstr    aSize_0// "Size"
0x5cc08  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5cc0d  ldarg.3
0x5cc0e  ldstr    aSize_0// "Size"
0x5cc13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5cc18  ldarg.1
0x5cc19  ldloc.0
0x5cc1a  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Size_Client()
0x5cc1f  ldarg.3
0x5cc20  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cc25  ldarg.3
0x5cc26  ldstr    aSize_0// "Size"
0x5cc2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5cc30  ldarg.0
0x5cc31  ldstr    aUrl// "Url"
0x5cc36  ldarg.3
0x5cc37  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cc3c  ldarg.1
0x5cc3d  ldstr    aUrl// "Url"
0x5cc42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5cc47  ldarg.3
0x5cc48  ldstr    aUrl// "Url"
0x5cc4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5cc52  ldarg.1
0x5cc53  ldloc.0
0x5cc54  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Url()
0x5cc59  ldarg.3
0x5cc5a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cc5f  ldarg.3
0x5cc60  ldstr    aUrl// "Url"
0x5cc65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5cc6a  ldarg.0
0x5cc6b  ldstr    aVersionlabel_0// "VersionLabel"
0x5cc70  ldarg.3
0x5cc71  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cc76  ldarg.1
0x5cc77  ldstr    aVersionlabel_0// "VersionLabel"
0x5cc7c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5cc81  ldarg.3
0x5cc82  ldstr    aVersionlabel_0// "VersionLabel"
0x5cc87  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5cc8c  ldarg.1
0x5cc8d  ldloc.0
0x5cc8e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_VersionLabel()
0x5cc93  ldarg.3
0x5cc94  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5cc99  ldarg.3
0x5cc9a  ldstr    aVersionlabel_0// "VersionLabel"
0x5cc9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5cca4  ret
```
