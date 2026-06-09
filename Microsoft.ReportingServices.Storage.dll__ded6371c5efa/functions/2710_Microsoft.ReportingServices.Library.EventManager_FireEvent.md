# Microsoft.ReportingServices.Library.EventManager::FireEvent

- ea: `0x2710`
- end: `0x2791`
- name: `Microsoft.ReportingServices.Library.EventManager::FireEvent`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2710`
- `0x6c00`
- `0x70e0`
- `0x7360`

## string_xrefs

- `0x273f`: `SnapshotUpdated`
- `0x2725`: `ReportHistorySnapshotCreated`
- `0x2732`: `SnapshotCreated`

## pseudocode

```c

```

## disassembly

```asm
0x2710  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2715  ldarg.1
0x2716  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::IsSupportedEvent(string)
0x271b  brtrue.s loc_2724
0x271d  ldarg.1
0x271e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownEventTypeException::.ctor(string)
0x2723  throw
0x2724  ldarg.1
0x2725  ldstr    aReporthistorys_0// "ReportHistorySnapshotCreated"
0x272a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x272f  brtrue.s loc_274B
0x2731  ldarg.1
0x2732  ldstr    aSnapshotcreate// "SnapshotCreated"
0x2737  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273c  brtrue.s loc_274B
0x273e  ldarg.1
0x273f  ldstr    aSnapshotupdate// "SnapshotUpdated"
0x2744  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2749  brfalse.s loc_2752
0x274b  ldarg.1
0x274c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownEventTypeException::.ctor(string)
0x2751  throw
0x2752  ldarg.0
0x2753  ldstr    aAddevent// "AddEvent"
0x2758  ldnull
0x2759  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x275e  stloc.0
0x275f  ldloc.0
0x2760  ldstr    aEventtype// "@EventType"
0x2765  ldc.i4.s 0xC
0x2767  ldarg.1
0x2768  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x276d  pop
0x276e  ldloc.0
0x276f  ldstr    aEventdata_0// "@EventData"
0x2774  ldc.i4.s 0xC
0x2776  ldarg.2
0x2777  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x277c  pop
0x277d  ldloc.0
0x277e  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2783  pop
0x2784  leave.s  loc_2790
0x2786  ldloc.0
0x2787  brfalse.s loc_278F
0x2789  ldloc.0
0x278a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x278f  endfinally
0x2790  ret
```
