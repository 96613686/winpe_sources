# Microsoft.ReportingServices.Library.HandledSqlDataReader::GetChars

- ea: `0x7580`
- end: `0x759e`
- name: `Microsoft.ReportingServices.Library.HandledSqlDataReader::GetChars`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x73d0`

## callees

- `0x6dd0`
- `0x7580`

## pseudocode

```c

```

## disassembly

```asm
0x7580  ldarg.0
0x7581  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader Microsoft.ReportingServices.Library.HandledSqlDataReader::reader
0x7586  ldarg.1
0x7587  ldarg.2
0x7588  ldarg.3
0x7589  ldarg.s  4
0x758b  ldarg.s  5
0x758d  callvirt instance int64 [System.Data]System.Data.Common.DbDataReader::GetChars(int32, int64, char[], int32, int32)
0x7592  stloc.0
0x7593  leave.s  loc_759C
0x7595  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x759a  rethrow
0x759c  ldloc.0
0x759d  ret
```
