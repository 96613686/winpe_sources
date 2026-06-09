# Microsoft.ReportingServices.Library.EventManager::FireSharedDatasetCacheUpdate

- ea: `0x27f0`
- end: `0x283f`
- name: `Microsoft.ReportingServices.Library.EventManager::FireSharedDatasetCacheUpdate`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x27f0`
- `0x6c00`
- `0x70e0`
- `0x7360`

## string_xrefs

- `0x2805`: `SharedDatasetCacheUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x27f0  ldarg.0
0x27f1  ldstr    aAddevent// "AddEvent"
0x27f6  ldnull
0x27f7  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x27fc  stloc.0
0x27fd  ldloc.0
0x27fe  ldstr    aEventtype// "@EventType"
0x2803  ldc.i4.s 0xC
0x2805  ldstr    aShareddatasetc// "SharedDatasetCacheUpdate"
0x280a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x280f  pop
0x2810  ldloc.0
0x2811  ldstr    aEventdata_0// "@EventData"
0x2816  ldc.i4.s 0xC
0x2818  ldarga.s 1
0x281a  constrained. [mscorlib]System.Guid
0x2820  callvirt instance string [mscorlib]System.Object::ToString()
0x2825  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x282a  pop
0x282b  ldloc.0
0x282c  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2831  pop
0x2832  leave.s  loc_283E
0x2834  ldloc.0
0x2835  brfalse.s loc_283D
0x2837  ldloc.0
0x2838  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x283d  endfinally
0x283e  ret
```
