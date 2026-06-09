# Microsoft.ReportingServices.DataExtensions.ConnectionWrapper::get_UnderlyingConnection

- ea: `0x31a0`
- end: `0x31c4`
- name: `Microsoft.ReportingServices.DataExtensions.ConnectionWrapper::get_UnderlyingConnection`
- size: `36`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x3110`
- `0x3120`
- `0x3130`
- `0x3150`
- `0x3170`
- `0x3180`
- `0x3190`

## callees

- `0x2a00`

## string_xrefs

- `0x31ae`: `If the underlying connection is not provided in the constructor it must be set before accessing it.`

## pseudocode

```c

```

## disassembly

```asm
0x31a0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x31a5  ldarg.0
0x31a6  call     instance object Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::get_UnderlyingObject()
0x31ab  ldnull
0x31ac  cgt.un
0x31ae  ldstr    aIfTheUnderlyin// "If the underlying connection is not pro"...
0x31b3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x31b8  ldarg.0
0x31b9  call     instance object Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::get_UnderlyingObject()
0x31be  castclass [System.Data]System.Data.IDbConnection
0x31c3  ret
```
