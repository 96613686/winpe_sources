# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::RenderingSupported

- ea: `0x9fb0`
- end: `0x9fbd`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::RenderingSupported`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xa670`
- `0xa900`

## callees

- `0x9f60`
- `0x9fe0`

## pseudocode

```c

```

## disassembly

```asm
0x9fb0  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::.ctor()
0x9fb5  dup
0x9fb6  ldc.i4.1
0x9fb7  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::set_IsSupported(bool value)
0x9fbc  ret
```
