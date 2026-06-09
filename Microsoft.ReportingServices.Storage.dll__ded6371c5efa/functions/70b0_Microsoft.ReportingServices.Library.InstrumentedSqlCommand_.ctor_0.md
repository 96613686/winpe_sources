# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::.ctor_0

- ea: `0x70b0`
- end: `0x70b9`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::.ctor_0`
- size: `9`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6f80`
- `0x70a0`
- `0x70d0`
- `0x94a0`
- `0x94b0`

## callees

- `0x6ef0`

## pseudocode

```c

```

## disassembly

```asm
0x70b0  ldarg.0
0x70b1  ldarg.1
0x70b2  ldarg.2
0x70b3  call     instance void Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::.ctor(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command, class [mscorlib]System.IDisposable connectionLockContext)
0x70b8  ret
```
