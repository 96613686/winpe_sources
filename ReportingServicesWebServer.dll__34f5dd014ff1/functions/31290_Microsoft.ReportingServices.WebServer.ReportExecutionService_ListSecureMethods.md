# Microsoft.ReportingServices.WebServer.ReportExecutionService::ListSecureMethods

- ea: `0x31290`
- end: `0x312bc`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::ListSecureMethods`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x31290`
- `0x31ca0`
- `0x31d60`
- `0x331e0`

## string_xrefs

- `0x31290`: `ReportExecutionService.ListSecureMethods`

## pseudocode

```c

```

## disassembly

```asm
0x31290  ldstr    aReportexecutio_3// "ReportExecutionService.ListSecureMethod"...
0x31295  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3129a  stloc.0
0x3129b  ldarg.0
0x3129c  ldarg.0
0x3129d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x312a2  ldnull
0x312a3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x312a8  call     string[] Microsoft.ReportingServices.WebServer.WebServiceHelper::get_SecureMethodsExecution2005()
0x312ad  stloc.1
0x312ae  leave.s  loc_312BA
0x312b0  ldloc.0
0x312b1  brfalse.s loc_312B9
0x312b3  ldloc.0
0x312b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x312b9  endfinally
0x312ba  ldloc.1
0x312bb  ret
```
