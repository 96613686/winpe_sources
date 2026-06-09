# ConfigFileBasedRequestParameters::ApplyDefaultRenderingParameters

- ea: `0x15a70`
- end: `0x15b1e`
- name: `ConfigFileBasedRequestParameters::ApplyDefaultRenderingParameters`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x51f0`
- `0x6160`
- `0x63a0`
- `0xc420`
- `0x10150`
- `0x15740`
- `0x15a70`

## string_xrefs

- `0x15a9d`: `Extensions`

## pseudocode

```c

```

## disassembly

```asm
0x15a70  ldarg.0
0x15a71  call     instance string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_FormatParamValue()
0x15a76  brfalse.s loc_15A8A
0x15a78  ldarg.0
0x15a79  call     instance string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_FormatParamValue()
0x15a7e  callvirt instance string [mscorlib]System.String::Trim()
0x15a83  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15a88  brtrue.s loc_15A8B
0x15a8a  ret
0x15a8b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x15a90  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x15a95  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x15a9a  ldnull
0x15a9b  cgt.un
0x15a9d  ldstr    aExtensions// "Extensions"
0x15aa2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x15aa7  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x15aac  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x15ab1  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Renderer()
0x15ab6  ldarg.0
0x15ab7  call     instance string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_FormatParamValue()
0x15abc  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x15ac1  castclass Microsoft.ReportingServices.Diagnostics.RenderingExtension
0x15ac6  stloc.0
0x15ac7  ldloc.0
0x15ac8  brtrue.s loc_15ACB
0x15aca  ret
0x15acb  ldloc.0
0x15acc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RenderingExtension::get_DeviceInfo()
0x15ad1  stloc.1
0x15ad2  ldloc.1
0x15ad3  brfalse.s loc_15ADE
0x15ad5  ldloc.1
0x15ad6  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x15adb  ldc.i4.0
0x15adc  bgt.s    loc_15ADF
0x15ade  ret
0x15adf  ldc.i4.0
0x15ae0  stloc.2
0x15ae1  br.s     loc_15B14
0x15ae3  ldarg.0
0x15ae4  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_renderingParameters
0x15ae9  ldloc.1
0x15aea  ldloc.2
0x15aeb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0x15af0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x15af5  brtrue.s loc_15B10
0x15af7  ldarg.0
0x15af8  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_renderingParameters
0x15afd  ldloc.1
0x15afe  ldloc.2
0x15aff  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0x15b04  ldloc.1
0x15b05  ldloc.2
0x15b06  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(int32)
0x15b0b  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x15b10  ldloc.2
0x15b11  ldc.i4.1
0x15b12  add
0x15b13  stloc.2
0x15b14  ldloc.2
0x15b15  ldloc.1
0x15b16  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x15b1b  blt.s    loc_15AE3
0x15b1d  ret
```
