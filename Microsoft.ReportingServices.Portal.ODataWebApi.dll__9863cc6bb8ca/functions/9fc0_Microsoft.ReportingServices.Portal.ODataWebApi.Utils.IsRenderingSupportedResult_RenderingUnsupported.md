# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::RenderingUnsupported

- ea: `0x9fc0`
- end: `0x9fdb`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::RenderingUnsupported`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa670`
- `0xa900`

## callees

- `0x9f60`
- `0x9f80`
- `0x9fa0`
- `0x9fe0`

## pseudocode

```c

```

## disassembly

```asm
0x9fc0  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::.ctor()
0x9fc5  dup
0x9fc6  ldc.i4.0
0x9fc7  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::set_IsSupported(bool value)
0x9fcc  dup
0x9fcd  ldarg.0
0x9fce  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::set_ErrorCode(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode value)
0x9fd3  dup
0x9fd4  ldarg.1
0x9fd5  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::set_ErrorMessage(string value)
0x9fda  ret
```
