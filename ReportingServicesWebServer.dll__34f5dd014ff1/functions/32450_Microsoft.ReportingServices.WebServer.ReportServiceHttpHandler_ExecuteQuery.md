# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::ExecuteQuery

- ea: `0x32450`
- end: `0x32474`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::ExecuteQuery`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x32450`
- `0x32a90`

## string_xrefs

- `0x32450`: `ReportServiceHttpHandler.ExecuteQuery`

## pseudocode

```c

```

## disassembly

```asm
0x32450  ldstr    aReportserviceh_8// "ReportServiceHttpHandler.ExecuteQuery"
0x32455  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3245a  stloc.0
0x3245b  ldc.i4.2
0x3245c  call     void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::EnsureHttpsLevel(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.HttpsLevel level)
0x32461  ldarg.0
0x32462  call     instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::ExecuteQuery()
0x32467  leave.s  loc_32473
0x32469  ldloc.0
0x3246a  brfalse.s loc_32472
0x3246c  ldloc.0
0x3246d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32472  endfinally
0x32473  ret
```
