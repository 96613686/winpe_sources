# Microsoft.ReportingServices.WebServer.ReportExecutionService::LogonUser

- ea: `0x31bc0`
- end: `0x31bf8`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LogonUser`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x31bc0`
- `0x31ca0`
- `0x31d60`
- `0x31e20`
- `0x334c0`
- `0x33560`

## string_xrefs

- `0x31bc0`: `ReportExecutionService.LogonUser`

## pseudocode

```c

```

## disassembly

```asm
0x31bc0  ldstr    aReportexecutio_36// "ReportExecutionService.LogonUser"
0x31bc5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31bca  stloc.0
0x31bcb  ldarg.0
0x31bcc  ldarg.0
0x31bcd  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31bd2  ldnull
0x31bd3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31bd8  newobj   instance void Microsoft.ReportingServices.WebServer.RSCustomAuthentication::.ctor()
0x31bdd  ldarg.1
0x31bde  ldarg.2
0x31bdf  ldarg.3
0x31be0  callvirt instance void Microsoft.ReportingServices.WebServer.RSCustomAuthentication::LogonUser(string userName, string password, string authority)
0x31be5  leave.s  loc_31BF7
0x31be7  call     class [mscorlib]System.Exception Microsoft.ReportingServices.WebServer.ReportExecutionService::ConvertRsToSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException rsx)
0x31bec  throw
0x31bed  ldloc.0
0x31bee  brfalse.s loc_31BF6
0x31bf0  ldloc.0
0x31bf1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31bf6  endfinally
0x31bf7  ret
```
