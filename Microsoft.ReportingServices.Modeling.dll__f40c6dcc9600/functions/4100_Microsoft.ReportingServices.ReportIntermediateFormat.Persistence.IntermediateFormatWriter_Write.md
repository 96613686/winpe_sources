# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write

- ea: `0x4100`
- end: `0x4109`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write`
- size: `9`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14f0`
- `0x3e80`
- `0x41a0`
- `0x42a0`
- `0x4320`
- `0x43b0`
- `0x4550`
- `0x4830`
- `0x4bb0`
- `0x4c30`
- `0x4de0`
- `0x4e30`
- `0x5200`
- `0x52a0`
- `0xd3b0`
- `0xfdf0`
- `0x11360`
- `0x12a00`
- `0x15f40`
- `0x16680`
- `0x166b0`
- `0x19510`
- `0x2fb30`
- `0x30300`

## callees

- `0x4110`

## pseudocode

```c

```

## disassembly

```asm
0x4100  ldarg.0
0x4101  ldarg.1
0x4102  ldc.i4.1
0x4103  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable persistableObj, bool verify)
0x4108  ret
```
