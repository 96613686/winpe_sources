# Microsoft.ReportingServices.Rendering.HtmlRenderer.PowerBIElementExtender::.ctor

- ea: `0x37f80`
- end: `0x37fa3`
- name: `Microsoft.ReportingServices.Rendering.HtmlRenderer.PowerBIElementExtender::.ctor`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x37f93`: `ReportItemPinRoot`

## pseudocode

```c

```

## disassembly

```asm
0x37f80  ldarg.0
0x37f81  ldsfld   string [mscorlib]System.String::Empty
0x37f86  stfld    string Microsoft.ReportingServices.Rendering.HtmlRenderer.PowerBIElementExtender::m_reportItemPinUrl
0x37f8b  ldarg.0
0x37f8c  call     instance void [mscorlib]System.Object::.ctor()
0x37f91  ldarg.0
0x37f92  ldarg.1
0x37f93  ldstr    aReportitempinr// "ReportItemPinRoot"
0x37f98  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x37f9d  stfld    string Microsoft.ReportingServices.Rendering.HtmlRenderer.PowerBIElementExtender::m_reportItemPinUrl
0x37fa2  ret
```
