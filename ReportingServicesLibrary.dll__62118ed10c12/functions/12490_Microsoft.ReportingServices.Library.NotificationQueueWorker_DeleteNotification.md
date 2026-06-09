# Microsoft.ReportingServices.Library.NotificationQueueWorker::DeleteNotification

- ea: `0x12490`
- end: `0x125d7`
- name: `Microsoft.ReportingServices.Library.NotificationQueueWorker::DeleteNotification`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x12410`

## callees

- `0x24c0`
- `0x26e0`
- `0x12490`

## string_xrefs

- `0x124a9`: `DeleteNotification`
- `0x124e4`: `DeleteNotification`
- `0x12561`: `Notification {0} completed.  Success: {1}, Status: {2}, DeliveryExtension: {3}, Report: {4}, Attempt {5}`

## pseudocode

```c

```

## disassembly

```asm
0x12490  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x12495  stloc.0
0x12496  ldloc.0
0x12497  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x1249c  ldarg.1
0x1249d  ldfld    class Microsoft.ReportingServices.Library.NotificationImpl Microsoft.ReportingServices.Library.NotificationQueueItem::Notification
0x124a2  stloc.1
0x124a3  ldloc.0
0x124a4  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction()
0x124a9  ldstr    aDeletenotifica// "DeleteNotification"
0x124ae  ldloc.0
0x124af  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker::NewStandardSqlCommand(string, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x124b4  stloc.2
0x124b5  ldloc.2
0x124b6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x124bb  ldstr    aId_1// "@ID"
0x124c0  ldloc.1
0x124c1  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.NotificationImpl::m_NotificationID
0x124c6  box      [mscorlib]System.Guid
0x124cb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x124d0  pop
0x124d1  ldloc.2
0x124d2  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x124d7  pop
0x124d8  leave.s  loc_124E4
0x124da  ldloc.2
0x124db  brfalse.s loc_124E3
0x124dd  ldloc.2
0x124de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x124e3  endfinally
0x124e4  ldstr    aDeletenotifica// "DeleteNotification"
0x124e9  ldloc.0
0x124ea  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker::NewStandardSqlCommand(string, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x124ef  stloc.3
0x124f0  ldloc.3
0x124f1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x124f6  ldstr    aId_1// "@ID"
0x124fb  ldloc.1
0x124fc  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.NotificationImpl::m_NotificationID
0x12501  box      [mscorlib]System.Guid
0x12506  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1250b  pop
0x1250c  ldloc.3
0x1250d  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x12512  pop
0x12513  leave.s  loc_1251F
0x12515  ldloc.3
0x12516  brfalse.s loc_1251E
0x12518  ldloc.3
0x12519  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1251e  endfinally
0x1251f  ldloc.1
0x12520  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_IsDataDriven()
0x12525  brfalse.s loc_1254F
0x12527  ldloc.0
0x12528  newobj   instance void Microsoft.ReportingServices.Library.ActiveSubscription::.ctor(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager connManager)
0x1252d  ldc.i4.1
0x1252e  stloc.s  4
0x12530  ldarg.1
0x12531  ldfld    bool Microsoft.ReportingServices.Library.NotificationQueueItem::DeleteAsErrorForDataDrivenNotification
0x12536  brfalse.s loc_1253B
0x12538  ldc.i4.2
0x12539  stloc.s  4
0x1253b  ldloc.1
0x1253c  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.NotificationImpl::m_activationID
0x12541  ldloc.1
0x12542  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.NotificationImpl::m_subscriptionID
0x12547  ldc.i4.1
0x12548  ldloc.s  4
0x1254a  callvirt instance void Microsoft.ReportingServices.Library.ActiveSubscription::SetActiveSubscriptionProperty(valuetype [mscorlib]System.Guid activeID, valuetype [mscorlib]System.Guid subscriptionID, int32 val, valuetype Microsoft.ReportingServices.Library.ActiveSubscriptionProperties property)
0x1254f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x12554  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x12559  brfalse.s loc_125BE
0x1255b  ldarg.0
0x1255c  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
0x12561  ldstr    aNotification0C// "Notification {0} completed.  Success: {"...
0x12566  ldc.i4.6
0x12567  newarr   [mscorlib]System.Object
0x1256c  dup
0x1256d  ldc.i4.0
0x1256e  ldloc.1
0x1256f  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.NotificationImpl::m_NotificationID
0x12574  box      [mscorlib]System.Guid
0x12579  stelem.ref
0x1257a  dup
0x1257b  ldc.i4.1
0x1257c  ldarg.1
0x1257d  ldfld    bool Microsoft.ReportingServices.Library.NotificationQueueItem::DeleteAsErrorForDataDrivenNotification
0x12582  ldc.i4.0
0x12583  ceq
0x12585  box      [mscorlib]System.Boolean
0x1258a  stelem.ref
0x1258b  dup
0x1258c  ldc.i4.2
0x1258d  ldloc.1
0x1258e  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_subscriptionStatus
0x12593  stelem.ref
0x12594  dup
0x12595  ldc.i4.3
0x12596  ldloc.1
0x12597  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_deliveryExtension
0x1259c  stelem.ref
0x1259d  dup
0x1259e  ldc.i4.4
0x1259f  ldloc.1
0x125a0  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Report [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_Report()
0x125a5  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Report::get_Name()
0x125aa  stelem.ref
0x125ab  dup
0x125ac  ldc.i4.5
0x125ad  ldloc.1
0x125ae  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_Attempt()
0x125b3  box      [mscorlib]System.Int32
0x125b8  stelem.ref
0x125b9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x125be  ldloc.0
0x125bf  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x125c4  leave.s  loc_125D6
0x125c6  pop
0x125c7  ldloc.0
0x125c8  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0x125cd  rethrow
0x125cf  ldloc.0
0x125d0  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x125d5  endfinally
0x125d6  ret
```
