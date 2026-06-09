# Microsoft.ReportingServices.WebServer.ReportExecutionService::Logoff

- ea: `0x31c00`
- end: `0x31c35`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::Logoff`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x31c00`
- `0x31ca0`
- `0x31d60`
- `0x31e20`
- `0x33540`
- `0x33560`

## string_xrefs

- `0x31c00`: `ReportExecutionService.Logoff`

## pseudocode

```c

```

## disassembly

```asm
0x31c00  ldstr    aReportexecutio_37// "ReportExecutionService.Logoff"
0x31c05  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31c0a  stloc.0
0x31c0b  ldarg.0
0x31c0c  ldarg.0
0x31c0d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31c12  ldnull
0x31c13  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31c18  newobj   instance void Microsoft.ReportingServices.WebServer.RSCustomAuthentication::.ctor()
0x31c1d  callvirt instance void Microsoft.ReportingServices.WebServer.RSCustomAuthentication::Logoff()
0x31c22  leave.s  loc_31C34
0x31c24  call     class [mscorlib]System.Exception Microsoft.ReportingServices.WebServer.ReportExecutionService::ConvertRsToSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException rsx)
0x31c29  throw
0x31c2a  ldloc.0
0x31c2b  brfalse.s loc_31C33
0x31c2d  ldloc.0
0x31c2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31c33  endfinally
0x31c34  ret
```
