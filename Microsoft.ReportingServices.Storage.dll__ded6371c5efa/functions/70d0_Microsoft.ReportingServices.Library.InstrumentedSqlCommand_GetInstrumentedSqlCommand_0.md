# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand_0

- ea: `0x70d0`
- end: `0x70d8`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand_0`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x35a0`
- `0x6c00`
- `0x6c60`
- `0x6cb0`

## callees

- `0x70b0`

## pseudocode

```c

```

## disassembly

```asm
0x70d0  ldarg.0
0x70d1  ldarg.1
0x70d2  newobj   instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::.ctor(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand cmd, class [mscorlib]System.IDisposable connectionLockContext)
0x70d7  ret
```
