# Microsoft.ReportingServices.Library.ProviderDBInterface::InactivateSubscriptionWithRemovedProviders

- ea: `0x153d0`
- end: `0x1547a`
- name: `Microsoft.ReportingServices.Library.ProviderDBInterface::InactivateSubscriptionWithRemovedProviders`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x15310`

## callees

- `0x153d0`

## string_xrefs

- `0x153fb`: `@DeliveryExtension`
- `0x153db`: `DeliveryRemovedInactivateSubscription`
- `0x1542f`: `Delivery extensions {0} was removed and subscription with this extension will be marked inactive.`

## pseudocode

```c

```

## disassembly

```asm
0x153d0  ldarg.1
0x153d1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x153d6  ldc.i4.0
0x153d7  bgt.s    loc_153DA
0x153d9  ret
0x153da  ldarg.0
0x153db  ldstr    aDeliveryremove// "DeliveryRemovedInactivateSubscription"
0x153e0  ldnull
0x153e1  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x153e6  stloc.0
0x153e7  ldloc.0
0x153e8  ldstr    aStatus_0// "@Status"
0x153ed  ldc.i4.s 0xC
0x153ef  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_DeliveryExtensionRemoved()
0x153f4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x153f9  pop
0x153fa  ldloc.0
0x153fb  ldstr    aDeliveryextens// "@DeliveryExtension"
0x15400  ldc.i4.s 0xC
0x15402  ldnull
0x15403  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x15408  stloc.1
0x15409  ldarg.1
0x1540a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x1540f  stloc.2
0x15410  br.s     loc_15451
0x15412  ldloc.2
0x15413  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x15418  castclass [mscorlib]System.String
0x1541d  stloc.3
0x1541e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x15423  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x15428  brfalse.s loc_15443
0x1542a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x1542f  ldstr    aDeliveryExtens// "Delivery extensions {0} was removed and"...
0x15434  ldc.i4.1
0x15435  newarr   [mscorlib]System.Object
0x1543a  dup
0x1543b  ldc.i4.0
0x1543c  ldloc.3
0x1543d  stelem.ref
0x1543e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x15443  ldloc.1
0x15444  ldloc.3
0x15445  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1544a  ldloc.0
0x1544b  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x15450  pop
0x15451  ldloc.2
0x15452  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15457  brtrue.s loc_15412
0x15459  leave.s  loc_15479
0x1545b  ldloc.2
0x1545c  isinst   [mscorlib]System.IDisposable
0x15461  stloc.s  4
0x15463  ldloc.s  4
0x15465  brfalse.s loc_1546E
0x15467  ldloc.s  4
0x15469  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1546e  endfinally
0x1546f  ldloc.0
0x15470  brfalse.s loc_15478
0x15472  ldloc.0
0x15473  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15478  endfinally
0x15479  ret
```
