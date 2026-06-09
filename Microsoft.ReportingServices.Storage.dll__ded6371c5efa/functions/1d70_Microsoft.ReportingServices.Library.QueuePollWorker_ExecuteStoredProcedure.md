# Microsoft.ReportingServices.Library.QueuePollWorker::ExecuteStoredProcedure

- ea: `0x1d70`
- end: `0x1db3`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::ExecuteStoredProcedure`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x11f0`
- `0x1d70`
- `0x30f0`
- `0x32e0`
- `0x32f0`
- `0x70e0`
- `0x7320`

## pseudocode

```c

```

## disassembly

```asm
0x1d70  ldc.i4.1
0x1d71  ldc.i4   0x1000
0x1d76  newobj   instance void Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType, valuetype [System.Data]System.Data.IsolationLevel defaultIsolationLevel)
0x1d7b  stloc.0
0x1d7c  ldloc.0
0x1d7d  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x1d82  ldarg.1
0x1d83  ldloc.0
0x1d84  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.PollWorker::NewStandardSqlCommand(string storedProcedureName, class Microsoft.ReportingServices.Library.ConnectionManager connManager)
0x1d89  stloc.1
0x1d8a  ldloc.1
0x1d8b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x1d90  ldarg.2
0x1d91  ldarg.3
0x1d92  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d97  pop
0x1d98  ldloc.1
0x1d99  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x1d9e  pop
0x1d9f  leave.s  loc_1DB2
0x1da1  ldloc.1
0x1da2  brfalse.s loc_1DAA
0x1da4  ldloc.1
0x1da5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1daa  endfinally
0x1dab  ldloc.0
0x1dac  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x1db1  endfinally
0x1db2  ret
```
