# Microsoft.ReportingServices.Library.DatabaseSessionStorage::CleanExpiredCache

- ea: `0x5d640`
- end: `0x5d707`
- name: `Microsoft.ReportingServices.Library.DatabaseSessionStorage::CleanExpiredCache`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfb60`

## callees

- `0x5d640`

## string_xrefs

- `0x5d646`: `Cleaning expired cache from DB`
- `0x5d67c`: `CleanExpiredCache`
- `0x5d6d8`: `Error in CleanExpiredCache: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5d640  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x5d645  ldc.i4.4
0x5d646  ldstr    aCleaningExpire_0// "Cleaning expired cache from DB"
0x5d64b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5d650  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x5d655  stloc.0
0x5d656  ldloc.0
0x5d657  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x5d65c  ldloc.0
0x5d65d  callvirt instance class [mscorlib]System.IDisposable [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x5d662  stloc.1
0x5d663  ldloc.0
0x5d664  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x5d669  stloc.2
0x5d66a  ldloc.0
0x5d66b  ldc.i4   0x1000
0x5d670  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction(valuetype [System.Data]System.Data.IsolationLevel)
0x5d675  ldloc.0
0x5d676  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x5d67b  stloc.3
0x5d67c  ldstr    aCleanexpiredca// "CleanExpiredCache"
0x5d681  ldloc.2
0x5d682  ldloc.3
0x5d683  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x5d688  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand)
0x5d68d  stloc.s  4
0x5d68f  ldloc.s  4
0x5d691  ldc.i4.4
0x5d692  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x5d697  ldloc.s  4
0x5d699  call     int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCleanupTimeoutSeconds()
0x5d69e  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x5d6a3  ldloc.s  4
0x5d6a5  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x5d6aa  ldloc.0
0x5d6ab  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x5d6b0  stloc.s  5
0x5d6b2  leave.s  loc_5D704
0x5d6b4  ldloc.s  4
0x5d6b6  brfalse.s loc_5D6BF
0x5d6b8  ldloc.s  4
0x5d6ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d6bf  endfinally
0x5d6c0  ldloc.1
0x5d6c1  brfalse.s loc_5D6C9
0x5d6c3  ldloc.1
0x5d6c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d6c9  endfinally
0x5d6ca  stloc.s  6
0x5d6cc  ldloc.0
0x5d6cd  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0x5d6d2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x5d6d7  ldc.i4.1
0x5d6d8  ldstr    aErrorInCleanex_2// "Error in CleanExpiredCache: {0}"
0x5d6dd  ldc.i4.1
0x5d6de  newarr   [mscorlib]System.Object
0x5d6e3  dup
0x5d6e4  ldc.i4.0
0x5d6e5  ldloc.s  6
0x5d6e7  stelem.ref
0x5d6e8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5d6ed  ldloc.s  6
0x5d6ef  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x5d6f4  brtrue.s loc_5D6F8
0x5d6f6  rethrow
0x5d6f8  ldc.i4.0
0x5d6f9  stloc.s  5
0x5d6fb  leave.s  loc_5D704
0x5d6fd  ldloc.0
0x5d6fe  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x5d703  endfinally
0x5d704  ldloc.s  5
0x5d706  ret
```
