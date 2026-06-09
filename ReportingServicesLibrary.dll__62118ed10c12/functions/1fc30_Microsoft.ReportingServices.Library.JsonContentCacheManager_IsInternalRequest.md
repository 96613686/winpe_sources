# Microsoft.ReportingServices.Library.JsonContentCacheManager::IsInternalRequest

- ea: `0x1fc30`
- end: `0x1fc79`
- name: `Microsoft.ReportingServices.Library.JsonContentCacheManager::IsInternalRequest`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1fc10`

## callees

- `0x1fc30`

## string_xrefs

- `0x1fc50`: `JsonCacheCreation`
- `0x1fc67`: `JsonCacheCreation`

## pseudocode

```c

```

## disassembly

```asm
0x1fc30  ldarg.0
0x1fc31  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters Microsoft.ReportingServices.Library.JsonContentCacheManager::m_requestParameters
0x1fc36  brfalse.s loc_1FC77
0x1fc38  ldarg.0
0x1fc39  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters Microsoft.ReportingServices.Library.JsonContentCacheManager::m_requestParameters
0x1fc3e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x1fc43  brfalse.s loc_1FC77
0x1fc45  ldarg.0
0x1fc46  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters Microsoft.ReportingServices.Library.JsonContentCacheManager::m_requestParameters
0x1fc4b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x1fc50  ldstr    aJsoncachecreat// "JsonCacheCreation"
0x1fc55  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1fc5a  brfalse.s loc_1FC77
0x1fc5c  ldarg.0
0x1fc5d  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters Microsoft.ReportingServices.Library.JsonContentCacheManager::m_requestParameters
0x1fc62  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x1fc67  ldstr    aJsoncachecreat// "JsonCacheCreation"
0x1fc6c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1fc71  call     bool [mscorlib]System.Boolean::Parse(string)
0x1fc76  ret
0x1fc77  ldc.i4.0
0x1fc78  ret
```
