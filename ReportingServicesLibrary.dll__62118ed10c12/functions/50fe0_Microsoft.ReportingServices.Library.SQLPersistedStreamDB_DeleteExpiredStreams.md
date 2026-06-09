# Microsoft.ReportingServices.Library.SQLPersistedStreamDB::DeleteExpiredStreams

- ea: `0x50fe0`
- end: `0x51036`
- name: `Microsoft.ReportingServices.Library.SQLPersistedStreamDB::DeleteExpiredStreams`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfb60`

## callees

- `0x50fe0`

## string_xrefs

- `0x50fe1`: `DeleteExpiredPersistedStreams`
- `0x51012`: `Error in DeleteExpiredPersistedStreams: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x50fe0  ldarg.0
0x50fe1  ldstr    aDeleteexpiredp// "DeleteExpiredPersistedStreams"
0x50fe6  ldnull
0x50fe7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x50fec  stloc.0
0x50fed  ldloc.0
0x50fee  call     int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCleanupTimeoutSeconds()
0x50ff3  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x50ff8  ldloc.0
0x50ff9  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x50ffe  stloc.1
0x50fff  leave.s  loc_51034
0x51001  ldloc.0
0x51002  brfalse.s loc_5100A
0x51004  ldloc.0
0x51005  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5100a  endfinally
0x5100b  stloc.2
0x5100c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0x51011  ldc.i4.1
0x51012  ldstr    aErrorInDeletee// "Error in DeleteExpiredPersistedStreams:"...
0x51017  ldc.i4.1
0x51018  newarr   [mscorlib]System.Object
0x5101d  dup
0x5101e  ldc.i4.0
0x5101f  ldloc.2
0x51020  stelem.ref
0x51021  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x51026  ldloc.2
0x51027  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x5102c  brtrue.s loc_51030
0x5102e  rethrow
0x51030  ldc.i4.0
0x51031  stloc.1
0x51032  leave.s  loc_51034
0x51034  ldloc.1
0x51035  ret
```
