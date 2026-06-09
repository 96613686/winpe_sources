# Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionParameters3

- ea: `0x315a0`
- end: `0x315d3`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionParameters3`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x23be0`
- `0x23c30`

## callees

- `0x315a0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x315a0`: `ReportExecutionService.SetExecutionParameters3`

## pseudocode

```c

```

## disassembly

```asm
0x315a0  ldstr    aReportexecutio_13// "ReportExecutionService.SetExecutionPara"...
0x315a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x315aa  stloc.0
0x315ab  ldarg.0
0x315ac  ldarg.0
0x315ad  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x315b2  ldnull
0x315b3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x315b8  ldarg.0
0x315b9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x315be  ldarg.1
0x315bf  ldarg.2
0x315c0  ldarg.3
0x315c1  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::SetExecutionParameters(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValue[], string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x315c6  leave.s  loc_315D2
0x315c8  ldloc.0
0x315c9  brfalse.s loc_315D1
0x315cb  ldloc.0
0x315cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x315d1  endfinally
0x315d2  ret
```
