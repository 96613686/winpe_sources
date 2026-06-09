# Microsoft.ReportingServices.DataExtensions.DataReaderWrapper::get_UnderlyingReader

- ea: `0x32b0`
- end: `0x32bc`
- name: `Microsoft.ReportingServices.DataExtensions.DataReaderWrapper::get_UnderlyingReader`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x3230`
- `0x3240`
- `0x3260`
- `0x3270`
- `0x3290`
- `0x32a0`

## callees

- `0x2a00`

## pseudocode

```c

```

## disassembly

```asm
0x32b0  ldarg.0
0x32b1  call     instance object Microsoft.ReportingServices.DataExtensions.BaseDataWrapper::get_UnderlyingObject()
0x32b6  castclass [System.Data]System.Data.IDataReader
0x32bb  ret
```
