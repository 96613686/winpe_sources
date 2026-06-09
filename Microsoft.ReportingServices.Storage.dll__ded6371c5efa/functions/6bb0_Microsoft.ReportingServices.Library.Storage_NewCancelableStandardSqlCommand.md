# Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand

- ea: `0x6bb0`
- end: `0x6bfa`
- name: `Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x32d0`
- `0x6a70`
- `0x6a80`
- `0x6aa0`
- `0x6ba0`
- `0x6bb0`
- `0x6f90`

## pseudocode

```c

```

## disassembly

```asm
0x6bb0  ldnull
0x6bb1  stloc.0
0x6bb2  ldarg.0
0x6bb3  callvirt instance class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x6bb8  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x6bbd  stloc.0
0x6bbe  ldarg.1
0x6bbf  ldarg.0
0x6bc0  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.Storage::get_Connection()
0x6bc5  ldarg.0
0x6bc6  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.Storage::get_Transaction()
0x6bcb  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x6bd0  dup
0x6bd1  ldc.i4.4
0x6bd2  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x6bd7  dup
0x6bd8  ldarg.0
0x6bd9  call     instance int32 Microsoft.ReportingServices.Library.Storage::get_SqlCommandTimeout()
0x6bde  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x6be3  ldloc.0
0x6be4  call     class Microsoft.ReportingServices.Library.CancelableSqlCommand Microsoft.ReportingServices.Library.CancelableSqlCommand::GetCancelableSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command, class [mscorlib]System.IDisposable connectionLockContext)
0x6be9  stloc.1
0x6bea  leave.s  loc_6BF8
0x6bec  pop
0x6bed  ldloc.0
0x6bee  brfalse.s loc_6BF6
0x6bf0  ldloc.0
0x6bf1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6bf6  rethrow
0x6bf8  ldloc.1
0x6bf9  ret
```
