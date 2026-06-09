# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::GetStyleSheet

- ea: `0x32170`
- end: `0x32190`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::GetStyleSheet`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x32170`
- `0x35350`

## string_xrefs

- `0x32170`: `ReportServiceHttpHandler.GetstyleSheet`

## pseudocode

```c

```

## disassembly

```asm
0x32170  ldstr    aReportserviceh_2// "ReportServiceHttpHandler.GetstyleSheet"
0x32175  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3217a  stloc.0
0x3217b  ldarg.1
0x3217c  call     unsigned int8[] Microsoft.ReportingServices.WebServer.LocalResourceUtils::GetStyleSheet(string requestedStyleSheet)
0x32181  stloc.1
0x32182  leave.s  loc_3218E
0x32184  ldloc.0
0x32185  brfalse.s loc_3218D
0x32187  ldloc.0
0x32188  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3218d  endfinally
0x3218e  ldloc.1
0x3218f  ret
```
