# Microsoft.SharePoint.ServerStub.SPThemeInfoServerStub::WritePropertiesAsJson

- ea: `0x860b0`
- end: `0x86139`
- name: `Microsoft.SharePoint.ServerStub.SPThemeInfoServerStub::WritePropertiesAsJson`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x860b0`

## string_xrefs

- `0x860c5`: `AccessibleDescription`
- `0x860d1`: `AccessibleDescription`
- `0x860dc`: `AccessibleDescription`
- `0x860f4`: `AccessibleDescription`
- `0x860ff`: `ThemeBackgroundImageUri`
- `0x8610b`: `ThemeBackgroundImageUri`
- `0x86116`: `ThemeBackgroundImageUri`
- `0x8612e`: `ThemeBackgroundImageUri`

## pseudocode

```c

```

## disassembly

```asm
0x860b0  ldarg.2
0x860b1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPThemeInfo
0x860b6  stloc.0
0x860b7  ldloc.0
0x860b8  brtrue.s loc_860BB
0x860ba  ret
0x860bb  ldarg.0
0x860bc  ldarg.1
0x860bd  ldarg.2
0x860be  ldarg.3
0x860bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x860c4  ldarg.0
0x860c5  ldstr    aAccessibledesc// "AccessibleDescription"
0x860ca  ldarg.3
0x860cb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x860d0  ldarg.1
0x860d1  ldstr    aAccessibledesc// "AccessibleDescription"
0x860d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x860db  ldarg.3
0x860dc  ldstr    aAccessibledesc// "AccessibleDescription"
0x860e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x860e6  ldarg.1
0x860e7  ldloc.0
0x860e8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPThemeInfo::get_AccessibleDescription()
0x860ed  ldarg.3
0x860ee  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x860f3  ldarg.3
0x860f4  ldstr    aAccessibledesc// "AccessibleDescription"
0x860f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x860fe  ldarg.0
0x860ff  ldstr    aThemebackgroun// "ThemeBackgroundImageUri"
0x86104  ldarg.3
0x86105  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8610a  ldarg.1
0x8610b  ldstr    aThemebackgroun// "ThemeBackgroundImageUri"
0x86110  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x86115  ldarg.3
0x86116  ldstr    aThemebackgroun// "ThemeBackgroundImageUri"
0x8611b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x86120  ldarg.1
0x86121  ldloc.0
0x86122  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPThemeInfo::get_ThemeBackgroundImageUri()
0x86127  ldarg.3
0x86128  call     T0x2B000052
0x8612d  ldarg.3
0x8612e  ldstr    aThemebackgroun// "ThemeBackgroundImageUri"
0x86133  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x86138  ret
```
