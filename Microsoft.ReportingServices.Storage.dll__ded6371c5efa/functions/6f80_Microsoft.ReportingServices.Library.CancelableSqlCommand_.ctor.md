# Microsoft.ReportingServices.Library.CancelableSqlCommand::.ctor

- ea: `0x6f80`
- end: `0x6f89`
- name: `Microsoft.ReportingServices.Library.CancelableSqlCommand::.ctor`
- size: `9`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6f90`
- `0x9450`

## callees

- `0x70b0`

## pseudocode

```c

```

## disassembly

```asm
0x6f80  ldarg.0
0x6f81  ldarg.1
0x6f82  ldarg.2
0x6f83  call     instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::.ctor(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand cmd, class [mscorlib]System.IDisposable connectionLockContext)
0x6f88  ret
```
