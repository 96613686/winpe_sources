# Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand

- ea: `0x6c00`
- end: `0x6c52`
- name: `Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand`
- size: `82`
- prototype: ``
- caller_count: `15`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e0`
- `0x2710`
- `0x27a0`
- `0x27f0`
- `0x2860`
- `0x2c60`
- `0x2ca0`
- `0x2d40`
- `0x61e0`
- `0x6240`
- `0x62e0`
- `0x63e0`
- `0x6750`
- `0x68b0`
- `0x6970`

## callees

- `0x32d0`
- `0x6a70`
- `0x6a80`
- `0x6aa0`
- `0x6ba0`
- `0x6c00`
- `0x70d0`
- `0x72f0`
- `0x7310`

## pseudocode

```c

```

## disassembly

```asm
0x6c00  ldnull
0x6c01  stloc.0
0x6c02  ldarg.0
0x6c03  callvirt instance class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x6c08  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x6c0d  stloc.0
0x6c0e  ldarg.2
0x6c0f  dup
0x6c10  brtrue.s loc_6C19
0x6c12  pop
0x6c13  ldarg.0
0x6c14  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.Storage::get_Connection()
0x6c19  starg.s  2
0x6c1b  ldarg.1
0x6c1c  ldarg.2
0x6c1d  ldarg.0
0x6c1e  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.Storage::get_Transaction()
0x6c23  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x6c28  ldloc.0
0x6c29  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command, class [mscorlib]System.IDisposable connectionLockContext)
0x6c2e  dup
0x6c2f  ldc.i4.4
0x6c30  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x6c35  dup
0x6c36  ldarg.0
0x6c37  call     instance int32 Microsoft.ReportingServices.Library.Storage::get_SqlCommandTimeout()
0x6c3c  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32 value)
0x6c41  stloc.1
0x6c42  leave.s  loc_6C50
0x6c44  pop
0x6c45  ldloc.0
0x6c46  brfalse.s loc_6C4E
0x6c48  ldloc.0
0x6c49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c4e  rethrow
0x6c50  ldloc.1
0x6c51  ret
```
