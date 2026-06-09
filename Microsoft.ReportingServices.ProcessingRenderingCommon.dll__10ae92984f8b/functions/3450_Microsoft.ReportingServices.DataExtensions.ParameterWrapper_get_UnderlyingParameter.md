# Microsoft.ReportingServices.DataExtensions.ParameterWrapper::get_UnderlyingParameter

- ea: `0x3450`
- end: `0x345c`
- name: `Microsoft.ReportingServices.DataExtensions.ParameterWrapper::get_UnderlyingParameter`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2ad0`
- `0x3330`
- `0x3410`
- `0x3420`
- `0x3430`
- `0x3440`

## callees

- `0x2a00`

## pseudocode

```c

```

## disassembly

```asm
0x3450  ldarg.0
0x3451  call     instance object Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::get_UnderlyingObject()
0x3456  castclass [System.Data]System.Data.IDataParameter
0x345b  ret
```
