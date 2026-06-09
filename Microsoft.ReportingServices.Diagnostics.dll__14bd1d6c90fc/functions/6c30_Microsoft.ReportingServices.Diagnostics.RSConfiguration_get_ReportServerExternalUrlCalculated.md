# Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ReportServerExternalUrlCalculated

- ea: `0x6c30`
- end: `0x6c66`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ReportServerExternalUrlCalculated`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2b0`

## callees

- `0x3fd0`
- `0x6c30`
- `0xab10`

## pseudocode

```c

```

## disassembly

```asm
0x6c30  ldarg.0
0x6c31  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerExternalUrlCalculated
0x6c36  stloc.0
0x6c37  call     bool Microsoft.ReportingServices.Diagnostics.Globals::get_CanTranslateIncomingHttpRequest()
0x6c3c  brfalse.s loc_6C64
0x6c3e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6c43  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x6c48  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x6c4d  ldc.i4   0x85
0x6c52  ldc.i4.1
0x6c53  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x6c58  ldarg.0
0x6c59  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ReportServerVirtualDirectory()
0x6c5e  call     string [mscorlib]System.String::Concat(string, string)
0x6c63  stloc.0
0x6c64  ldloc.0
0x6c65  ret
```
