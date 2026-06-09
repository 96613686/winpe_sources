# Microsoft.ReportingServices.Library.EventManager::FireSnapShotCreatedEvent

- ea: `0x27a0`
- end: `0x27ef`
- name: `Microsoft.ReportingServices.Library.EventManager::FireSnapShotCreatedEvent`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x27a0`
- `0x6c00`
- `0x70e0`
- `0x7360`

## string_xrefs

- `0x27b5`: `SnapshotUpdated`

## pseudocode

```c

```

## disassembly

```asm
0x27a0  ldarg.0
0x27a1  ldstr    aAddevent// "AddEvent"
0x27a6  ldnull
0x27a7  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x27ac  stloc.0
0x27ad  ldloc.0
0x27ae  ldstr    aEventtype// "@EventType"
0x27b3  ldc.i4.s 0xC
0x27b5  ldstr    aSnapshotupdate// "SnapshotUpdated"
0x27ba  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x27bf  pop
0x27c0  ldloc.0
0x27c1  ldstr    aEventdata_0// "@EventData"
0x27c6  ldc.i4.s 0xC
0x27c8  ldarga.s 1
0x27ca  constrained. [mscorlib]System.Guid
0x27d0  callvirt instance string [mscorlib]System.Object::ToString()
0x27d5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x27da  pop
0x27db  ldloc.0
0x27dc  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x27e1  pop
0x27e2  leave.s  loc_27EE
0x27e4  ldloc.0
0x27e5  brfalse.s loc_27ED
0x27e7  ldloc.0
0x27e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27ed  endfinally
0x27ee  ret
```
