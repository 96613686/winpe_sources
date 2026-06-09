# Microsoft.ReportingServices.Library.SubscriptionDB::DeleteSubscription

- ea: `0x526b0`
- end: `0x52797`
- name: `Microsoft.ReportingServices.Library.SubscriptionDB::DeleteSubscription`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x541f0`

## callees

- `0x526b0`

## string_xrefs

- `0x526b1`: `AddSubscriptionToBeingDeleted`
- `0x526f5`: `DeleteSubscription`
- `0x52744`: `RemoveSubscriptionFromBeingDeleted`

## pseudocode

```c

```

## disassembly

```asm
0x526b0  ldarg.0
0x526b1  ldstr    aAddsubscriptio// "AddSubscriptionToBeingDeleted"
0x526b6  ldnull
0x526b7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x526bc  dup
0x526bd  stloc.0
0x526be  stloc.1
0x526bf  ldloc.0
0x526c0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x526c5  ldstr    aSubscriptionid// "@SubscriptionID"
0x526ca  ldarg.1
0x526cb  box      [mscorlib]System.Guid
0x526d0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x526d5  pop
0x526d6  ldloc.0
0x526d7  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x526dc  pop
0x526dd  ldarg.0
0x526de  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x526e3  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x526e8  leave.s  loc_526F4
0x526ea  ldloc.1
0x526eb  brfalse.s loc_526F3
0x526ed  ldloc.1
0x526ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x526f3  endfinally
0x526f4  ldarg.0
0x526f5  ldstr    aDeletesubscrip_0// "DeleteSubscription"
0x526fa  ldnull
0x526fb  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x52700  dup
0x52701  stloc.0
0x52702  stloc.1
0x52703  ldloc.0
0x52704  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52709  ldstr    aSubscriptionid// "@SubscriptionID"
0x5270e  ldarg.1
0x5270f  box      [mscorlib]System.Guid
0x52714  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52719  pop
0x5271a  ldloc.0
0x5271b  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x52720  pop
0x52721  leave.s  loc_5272D
0x52723  ldloc.1
0x52724  brfalse.s loc_5272C
0x52726  ldloc.1
0x52727  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5272c  endfinally
0x5272d  leave.s  loc_52796
0x5272f  stloc.2
0x52730  ldloc.2
0x52731  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x52736  brfalse.s loc_52794
0x52738  ldarg.0
0x52739  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x5273e  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0x52743  ldarg.0
0x52744  ldstr    aRemovesubscrip// "RemoveSubscriptionFromBeingDeleted"
0x52749  ldnull
0x5274a  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x5274f  stloc.3
0x52750  ldloc.3
0x52751  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52756  ldstr    aSubscriptionid// "@SubscriptionID"
0x5275b  ldarg.1
0x5275c  box      [mscorlib]System.Guid
0x52761  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52766  pop
0x52767  ldloc.3
0x52768  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x5276d  pop
0x5276e  ldarg.0
0x5276f  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x52774  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x52779  ldloc.2
0x5277a  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x5277f  ldc.i4   0x37B6
0x52784  beq.s    loc_52788
0x52786  rethrow
0x52788  leave.s  loc_52794
0x5278a  ldloc.3
0x5278b  brfalse.s loc_52793
0x5278d  ldloc.3
0x5278e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x52793  endfinally
0x52794  leave.s  loc_52796
0x52796  ret
```
