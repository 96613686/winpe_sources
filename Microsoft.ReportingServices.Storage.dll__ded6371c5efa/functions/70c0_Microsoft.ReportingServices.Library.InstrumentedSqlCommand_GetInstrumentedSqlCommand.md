# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand

- ea: `0x70c0`
- end: `0x70c7`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f0`
- `0x17c0`
- `0x20b0`
- `0x2580`

## callees

- `0x70a0`

## pseudocode

```c

```

## disassembly

```asm
0x70c0  ldarg.0
0x70c1  newobj   instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::.ctor(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command)
0x70c6  ret
```
