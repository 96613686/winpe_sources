# Microsoft.SharePoint.Publishing.CustomizableStringServerStub::WritePropertiesAsJson

- ea: `0x2780`
- end: `0x2849`
- name: `Microsoft.SharePoint.Publishing.CustomizableStringServerStub::WritePropertiesAsJson`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2780`

## pseudocode

```c

```

## disassembly

```asm
0x2780  ldarg.2
0x2781  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString
0x2786  stloc.0
0x2787  ldloc.0
0x2788  ldnull
0x2789  call     bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString::op_Equality(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString, class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString)
0x278e  brfalse.s loc_2791
0x2790  ret
0x2791  ldarg.0
0x2792  ldarg.1
0x2793  ldarg.2
0x2794  ldarg.3
0x2795  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x279a  ldarg.0
0x279b  ldstr    aDefaultvalue// "DefaultValue"
0x27a0  ldarg.3
0x27a1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x27a6  ldarg.1
0x27a7  ldstr    aDefaultvalue// "DefaultValue"
0x27ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x27b1  ldarg.3
0x27b2  ldstr    aDefaultvalue// "DefaultValue"
0x27b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x27bc  ldarg.1
0x27bd  ldloc.0
0x27be  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString::get_DefaultValue()
0x27c3  ldarg.3
0x27c4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x27c9  ldarg.3
0x27ca  ldstr    aDefaultvalue// "DefaultValue"
0x27cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x27d4  ldarg.0
0x27d5  ldstr    aUsesdefaultval// "UsesDefaultValue"
0x27da  ldarg.3
0x27db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x27e0  ldarg.1
0x27e1  ldstr    aUsesdefaultval// "UsesDefaultValue"
0x27e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x27eb  ldarg.3
0x27ec  ldstr    aUsesdefaultval// "UsesDefaultValue"
0x27f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x27f6  ldarg.1
0x27f7  ldloc.0
0x27f8  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString::get_UsesDefaultValue()
0x27fd  ldarg.3
0x27fe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2803  ldarg.3
0x2804  ldstr    aUsesdefaultval// "UsesDefaultValue"
0x2809  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x280e  ldarg.0
0x280f  ldstr    aValue// "Value"
0x2814  ldarg.3
0x2815  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x281a  ldarg.1
0x281b  ldstr    aValue// "Value"
0x2820  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2825  ldarg.3
0x2826  ldstr    aValue// "Value"
0x282b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2830  ldarg.1
0x2831  ldloc.0
0x2832  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString::get_Value()
0x2837  ldarg.3
0x2838  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x283d  ldarg.3
0x283e  ldstr    aValue// "Value"
0x2843  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2848  ret
```
