# Microsoft.ReportingServices.WebServer.ReportExecutionService::Render

- ea: `0x316a0`
- end: `0x316de`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::Render`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x316a0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x316a0`: `ReportExecutionService.Render`

## pseudocode

```c

```

## disassembly

```asm
0x316a0  ldstr    aReportexecutio_16// "ReportExecutionService.Render"
0x316a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x316aa  stloc.0
0x316ab  ldarg.0
0x316ac  ldarg.0
0x316ad  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x316b2  ldnull
0x316b3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x316b8  ldarg.0
0x316b9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x316be  ldarg.1
0x316bf  ldarg.2
0x316c0  ldc.i4.0
0x316c1  ldarg.3
0x316c2  ldarg.s  4
0x316c4  ldarg.s  5
0x316c6  ldarg.s  6
0x316c8  ldarg.s  7
0x316ca  ldarg.s  8
0x316cc  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::Render(string, string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.PageCountMode, unsigned int8[]&, string&, string&, string&, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Warning[]&, string[]&)
0x316d1  leave.s  loc_316DD
0x316d3  ldloc.0
0x316d4  brfalse.s loc_316DC
0x316d6  ldloc.0
0x316d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x316dc  endfinally
0x316dd  ret
```
