# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::ProcessRequest

- ea: `0x31ee0`
- end: `0x31f12`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::ProcessRequest`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x31ee0`
- `0x32080`

## string_xrefs

- `0x31ee0`: `ReportServiceHttpHandler.ProcessRequest`

## pseudocode

```c

```

## disassembly

```asm
0x31ee0  ldstr    aReportserviceh// "ReportServiceHttpHandler.ProcessRequest"
0x31ee5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31eea  stloc.0
0x31eeb  ldarg.0
0x31eec  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::Clean()
0x31ef1  ldarg.0
0x31ef2  ldarg.1
0x31ef3  stfld    class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::m_Context
0x31ef8  ldarg.0
0x31ef9  call     instance void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderPage()
0x31efe  leave.s  loc_31F11
0x31f00  ldarg.0
0x31f01  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::Clean()
0x31f06  endfinally
0x31f07  ldloc.0
0x31f08  brfalse.s loc_31F10
0x31f0a  ldloc.0
0x31f0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31f10  endfinally
0x31f11  ret
```
