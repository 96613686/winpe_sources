# Microsoft.SharePoint.Publishing.PrimaryCityTimeServerStub::WritePropertiesAsJson

- ea: `0xaf60`
- end: `0xb023`
- name: `Microsoft.SharePoint.Publishing.PrimaryCityTimeServerStub::WritePropertiesAsJson`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xaf60`

## pseudocode

```c

```

## disassembly

```asm
0xaf60  ldarg.2
0xaf61  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime
0xaf66  stloc.0
0xaf67  ldloc.0
0xaf68  brtrue.s loc_AF6B
0xaf6a  ret
0xaf6b  ldarg.0
0xaf6c  ldarg.1
0xaf6d  ldarg.2
0xaf6e  ldarg.3
0xaf6f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf74  ldarg.0
0xaf75  ldstr    aLocation// "Location"
0xaf7a  ldarg.3
0xaf7b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf80  ldarg.1
0xaf81  ldstr    aLocation// "Location"
0xaf86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf8b  ldarg.3
0xaf8c  ldstr    aLocation// "Location"
0xaf91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf96  ldarg.1
0xaf97  ldloc.0
0xaf98  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime::get_Location()
0xaf9d  ldarg.3
0xaf9e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafa3  ldarg.3
0xafa4  ldstr    aLocation// "Location"
0xafa9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xafae  ldarg.0
0xafaf  ldstr    aTime// "Time"
0xafb4  ldarg.3
0xafb5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafba  ldarg.1
0xafbb  ldstr    aTime// "Time"
0xafc0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xafc5  ldarg.3
0xafc6  ldstr    aTime// "Time"
0xafcb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xafd0  ldarg.1
0xafd1  ldloc.0
0xafd2  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime::get_Time()
0xafd7  ldarg.3
0xafd8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafdd  ldarg.3
0xafde  ldstr    aTime// "Time"
0xafe3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xafe8  ldarg.0
0xafe9  ldstr    aUtcoffset// "UtcOffset"
0xafee  ldarg.3
0xafef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaff4  ldarg.1
0xaff5  ldstr    aUtcoffset// "UtcOffset"
0xaffa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xafff  ldarg.3
0xb000  ldstr    aUtcoffset// "UtcOffset"
0xb005  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xb00a  ldarg.1
0xb00b  ldloc.0
0xb00c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime::get_UtcOffset()
0xb011  ldarg.3
0xb012  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb017  ldarg.3
0xb018  ldstr    aUtcoffset// "UtcOffset"
0xb01d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xb022  ret
```
