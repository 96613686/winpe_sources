# Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::.ctor

- ea: `0x29d0`
- end: `0x29de`
- name: `Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::.ctor`
- size: `14`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2a50`
- `0x3100`
- `0x3220`
- `0x3310`
- `0x3400`
- `0x3470`

## pseudocode

```c

```

## disassembly

```asm
0x29d0  ldarg.0
0x29d1  call     instance void [mscorlib]System.Object::.ctor()
0x29d6  ldarg.0
0x29d7  ldarg.1
0x29d8  stfld    object Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::m_underlyingObject
0x29dd  ret
```
