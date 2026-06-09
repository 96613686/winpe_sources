# Microsoft.ReportingServices.Library.HandledSqlDataReader::.ctor

- ea: `0x7490`
- end: `0x749e`
- name: `Microsoft.ReportingServices.Library.HandledSqlDataReader::.ctor`
- size: `14`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x7120`
- `0x7160`
- `0x7390`

## pseudocode

```c

```

## disassembly

```asm
0x7490  ldarg.0
0x7491  call     instance void [mscorlib]System.Object::.ctor()
0x7496  ldarg.0
0x7497  ldarg.1
0x7498  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader Microsoft.ReportingServices.Library.HandledSqlDataReader::reader
0x749d  ret
```
