# Microsoft.SharePoint.Publishing.UserInfoServerStub::WritePropertiesAsJson

- ea: `0x12990`
- end: `0x12a8d`
- name: `Microsoft.SharePoint.Publishing.UserInfoServerStub::WritePropertiesAsJson`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12990`

## pseudocode

```c

```

## disassembly

```asm
0x12990  ldarg.2
0x12991  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo
0x12996  stloc.0
0x12997  ldloc.0
0x12998  brtrue.s loc_1299B
0x1299a  ret
0x1299b  ldarg.0
0x1299c  ldarg.1
0x1299d  ldarg.2
0x1299e  ldarg.3
0x1299f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x129a4  ldarg.0
0x129a5  ldstr    aAccountname// "AccountName"
0x129aa  ldarg.3
0x129ab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x129b0  ldarg.1
0x129b1  ldstr    aAccountname// "AccountName"
0x129b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x129bb  ldarg.3
0x129bc  ldstr    aAccountname// "AccountName"
0x129c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x129c6  ldarg.1
0x129c7  ldloc.0
0x129c8  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo::get_AccountName()
0x129cd  ldarg.3
0x129ce  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x129d3  ldarg.3
0x129d4  ldstr    aAccountname// "AccountName"
0x129d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x129de  ldarg.0
0x129df  ldstr    aAcronym// "Acronym"
0x129e4  ldarg.3
0x129e5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x129ea  ldarg.1
0x129eb  ldstr    aAcronym// "Acronym"
0x129f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x129f5  ldarg.3
0x129f6  ldstr    aAcronym// "Acronym"
0x129fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x12a00  ldarg.1
0x12a01  ldloc.0
0x12a02  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo::get_Acronym()
0x12a07  ldarg.3
0x12a08  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12a0d  ldarg.3
0x12a0e  ldstr    aAcronym// "Acronym"
0x12a13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x12a18  ldarg.0
0x12a19  ldstr    aColor// "Color"
0x12a1e  ldarg.3
0x12a1f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12a24  ldarg.1
0x12a25  ldstr    aColor// "Color"
0x12a2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x12a2f  ldarg.3
0x12a30  ldstr    aColor// "Color"
0x12a35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x12a3a  ldarg.1
0x12a3b  ldloc.0
0x12a3c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo::get_Color()
0x12a41  ldarg.3
0x12a42  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12a47  ldarg.3
0x12a48  ldstr    aColor// "Color"
0x12a4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x12a52  ldarg.0
0x12a53  ldstr    aName// "Name"
0x12a58  ldarg.3
0x12a59  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12a5e  ldarg.1
0x12a5f  ldstr    aName// "Name"
0x12a64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x12a69  ldarg.3
0x12a6a  ldstr    aName// "Name"
0x12a6f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x12a74  ldarg.1
0x12a75  ldloc.0
0x12a76  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo::get_Name()
0x12a7b  ldarg.3
0x12a7c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12a81  ldarg.3
0x12a82  ldstr    aName// "Name"
0x12a87  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x12a8c  ret
```
