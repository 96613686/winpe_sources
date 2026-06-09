# Microsoft.ReportingServices.Library.HandledSqlDataReader::GetBytes

- ea: `0x7550`
- end: `0x756e`
- name: `Microsoft.ReportingServices.Library.HandledSqlDataReader::GetBytes`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x73a0`

## callees

- `0x6dd0`
- `0x7550`

## pseudocode

```c

```

## disassembly

```asm
0x7550  ldarg.0
0x7551  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader Microsoft.ReportingServices.Library.HandledSqlDataReader::reader
0x7556  ldarg.1
0x7557  ldarg.2
0x7558  ldarg.3
0x7559  ldarg.s  4
0x755b  ldarg.s  5
0x755d  callvirt instance int64 [System.Data]System.Data.Common.DbDataReader::GetBytes(int32, int64, unsigned int8[], int32, int32)
0x7562  stloc.0
0x7563  leave.s  loc_756C
0x7565  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x756a  rethrow
0x756c  ldloc.0
0x756d  ret
```
