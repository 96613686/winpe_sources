# Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand

- ea: `0x30e0`
- end: `0x30ec`
- name: `Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand`
- size: `12`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2a60`
- `0x2ad0`
- `0x2b30`
- `0x2be0`
- `0x2c10`
- `0x2c90`
- `0x2f50`
- `0x2f70`
- `0x2fe0`
- `0x2ff0`
- `0x3000`
- `0x3010`
- `0x3020`
- `0x3030`
- `0x3070`
- `0x30c0`

## callees

- `0x2a00`

## pseudocode

```c

```

## disassembly

```asm
0x30e0  ldarg.0
0x30e1  call     instance object Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::get_UnderlyingObject()
0x30e6  castclass [System.Data]System.Data.IDbCommand
0x30eb  ret
```
