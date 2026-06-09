# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::GetStyleSheetImage

- ea: `0x32190`
- end: `0x321b0`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::GetStyleSheetImage`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x32190`
- `0x353a0`

## string_xrefs

- `0x32190`: `ReportServiceHttpHandler.GetStyleSheetImage`

## pseudocode

```c

```

## disassembly

```asm
0x32190  ldstr    aReportserviceh_3// "ReportServiceHttpHandler.GetStyleSheetI"...
0x32195  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3219a  stloc.0
0x3219b  ldarg.1
0x3219c  call     unsigned int8[] Microsoft.ReportingServices.WebServer.LocalResourceUtils::GetStyleSheetImage(string imageName)
0x321a1  stloc.1
0x321a2  leave.s  loc_321AE
0x321a4  ldloc.0
0x321a5  brfalse.s loc_321AD
0x321a7  ldloc.0
0x321a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x321ad  endfinally
0x321ae  ldloc.1
0x321af  ret
```
