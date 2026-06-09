# Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery

- ea: `0x6c60`
- end: `0x6caa`
- name: `Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery`
- size: `74`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x28c0`
- `0x2990`
- `0x2ba0`
- `0x2be0`
- `0x2c10`
- `0x2f40`

## callees

- `0x32d0`
- `0x6a70`
- `0x6a80`
- `0x6aa0`
- `0x6ba0`
- `0x6c60`
- `0x70d0`
- `0x72f0`
- `0x7310`

## pseudocode

```c

```

## disassembly

```asm
0x6c60  ldnull
0x6c61  stloc.0
0x6c62  ldarg.0
0x6c63  callvirt instance class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x6c68  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x6c6d  stloc.0
0x6c6e  ldarg.1
0x6c6f  ldarg.0
0x6c70  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.Storage::get_Connection()
0x6c75  ldarg.0
0x6c76  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.Storage::get_Transaction()
0x6c7b  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x6c80  ldloc.0
0x6c81  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command, class [mscorlib]System.IDisposable connectionLockContext)
0x6c86  dup
0x6c87  ldc.i4.1
0x6c88  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x6c8d  dup
0x6c8e  ldarg.0
0x6c8f  call     instance int32 Microsoft.ReportingServices.Library.Storage::get_SqlCommandTimeout()
0x6c94  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32 value)
0x6c99  stloc.1
0x6c9a  leave.s  loc_6CA8
0x6c9c  pop
0x6c9d  ldloc.0
0x6c9e  brfalse.s loc_6CA6
0x6ca0  ldloc.0
0x6ca1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ca6  rethrow
0x6ca8  ldloc.1
0x6ca9  ret
```
