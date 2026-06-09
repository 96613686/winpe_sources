# Microsoft.ReportingServices.Library.HandledSqlDataReader::InvokeNoReturn

- ea: `0x76d0`
- end: `0x76e6`
- name: `Microsoft.ReportingServices.Library.HandledSqlDataReader::InvokeNoReturn`
- size: `22`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x7400`
- `0x74a0`
- `0x7510`

## callees

- `0x6dd0`
- `0x76d0`

## pseudocode

```c

```

## disassembly

```asm
0x76d0  ldarg.1
0x76d1  ldarg.0
0x76d2  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader Microsoft.ReportingServices.Library.HandledSqlDataReader::reader
0x76d7  callvirt instance void class [mscorlib]System.Action`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader>::Invoke(var<u1>)
0x76dc  leave.s  loc_76E5
0x76de  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x76e3  rethrow
0x76e5  ret
```
