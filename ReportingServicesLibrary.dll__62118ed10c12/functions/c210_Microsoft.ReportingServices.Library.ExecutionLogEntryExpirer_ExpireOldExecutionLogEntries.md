# Microsoft.ReportingServices.Library.ExecutionLogEntryExpirer::ExpireOldExecutionLogEntries

- ea: `0xc210`
- end: `0xc2c5`
- name: `Microsoft.ReportingServices.Library.ExecutionLogEntryExpirer::ExpireOldExecutionLogEntries`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xbfe0`

## callees

- `0x45d0`
- `0xa8f0`
- `0xc210`

## string_xrefs

- `0xc266`: `Expiration of old execution log entries is complete.  Expiration is disabled.`
- `0xc278`: `Expiration of old execution log entries is complete.  Removed {0} entries.`

## pseudocode

```c

```

## disassembly

```asm
0xc210  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0xc215  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0xc21a  brfalse.s loc_C22C
0xc21c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0xc221  ldc.i4.3
0xc222  ldstr    aExpiringOldExe// "Expiring old execution log entries"
0xc227  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xc22c  ldc.i4.1
0xc22d  ldc.i4   0x1000
0xc232  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0xc237  stloc.0
0xc238  ldloc.0
0xc239  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0xc23e  newobj   instance void Microsoft.ReportingServices.Library.DBInterface::.ctor()
0xc243  dup
0xc244  ldloc.0
0xc245  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0xc24a  callvirt instance int32 Microsoft.ReportingServices.Library.DBInterface::ExpireExecutionLogEntries()
0xc24f  stloc.1
0xc250  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0xc255  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0xc25a  brfalse.s loc_C291
0xc25c  ldloc.1
0xc25d  ldc.i4.0
0xc25e  bge.s    loc_C272
0xc260  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0xc265  ldc.i4.3
0xc266  ldstr    aExpirationOfOl// "Expiration of old execution log entries"...
0xc26b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xc270  br.s     loc_C291
0xc272  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0xc277  ldc.i4.3
0xc278  ldstr    aExpirationOfOl_0// "Expiration of old execution log entries"...
0xc27d  ldc.i4.1
0xc27e  newarr   [mscorlib]System.Object
0xc283  dup
0xc284  ldc.i4.0
0xc285  ldloc.1
0xc286  box      [mscorlib]System.Int32
0xc28b  stelem.ref
0xc28c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xc291  leave.s  loc_C2C4
0xc293  stloc.2
0xc294  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0xc299  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xc29e  brfalse.s loc_C2BB
0xc2a0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CleanupTracer()
0xc2a5  ldc.i4.1
0xc2a6  ldstr    aExpirationOfOl_1// "Expiration of old execution log entries"...
0xc2ab  ldloc.2
0xc2ac  callvirt instance string [mscorlib]System.Object::ToString()
0xc2b1  call     string [mscorlib]System.String::Concat(string, string)
0xc2b6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xc2bb  leave.s  loc_C2C4
0xc2bd  ldloc.0
0xc2be  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0xc2c3  endfinally
0xc2c4  ret
```
