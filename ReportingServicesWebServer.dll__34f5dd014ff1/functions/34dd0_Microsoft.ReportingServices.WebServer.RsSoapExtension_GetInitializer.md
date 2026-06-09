# Microsoft.ReportingServices.WebServer.RsSoapExtension::GetInitializer

- ea: `0x34dd0`
- end: `0x34de2`
- name: `Microsoft.ReportingServices.WebServer.RsSoapExtension::GetInitializer`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x34dd6`: `SharepointSoapExtension attribute applied to web method.`

## pseudocode

```c

```

## disassembly

```asm
0x34dd0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x34dd5  ldc.i4.0
0x34dd6  ldstr    aSharepointsoap// "SharepointSoapExtension attribute appli"...
0x34ddb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x34de0  ldnull
0x34de1  ret
```
