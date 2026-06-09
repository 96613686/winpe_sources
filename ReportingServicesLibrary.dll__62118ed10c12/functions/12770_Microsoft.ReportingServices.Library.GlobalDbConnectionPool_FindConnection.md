# Microsoft.ReportingServices.Library.GlobalDbConnectionPool::FindConnection

- ea: `0x12770`
- end: `0x1287c`
- name: `Microsoft.ReportingServices.Library.GlobalDbConnectionPool::FindConnection`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x12740`

## callees

- `0xb3c0`
- `0xb540`
- `0xb560`
- `0xb660`
- `0xb690`
- `0x12770`
- `0x12a10`

## string_xrefs

- `0x12784`: `Waiting to acquire connections lock inside FindConnection`
- `0x127a0`: `Acquired connections lock inside FindConnection`

## pseudocode

```c

```

## disassembly

```asm
0x12770  ldarg.1
0x12771  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionKey::ShouldCheckIsAlive()
0x12776  stloc.0
0x12777  br       loc_12866
0x1277c  ldnull
0x1277d  stloc.1
0x1277e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x12783  ldc.i4.3
0x12784  ldstr    aWaitingToAcqui// "Waiting to acquire connections lock ins"...
0x12789  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1278e  ldarg.2
0x1278f  stloc.2
0x12790  ldc.i4.0
0x12791  stloc.3
0x12792  ldloc.2
0x12793  ldloca.s 3
0x12795  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1279a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x1279f  ldc.i4.3
0x127a0  ldstr    aAcquiredConnec// "Acquired connections lock inside FindCo"...
0x127a5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x127aa  ldarg.2
0x127ab  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry> EntryList::Entries
0x127b0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry>::get_Count()
0x127b5  ldc.i4.1
0x127b6  sub
0x127b7  stloc.s  4
0x127b9  ldloc.s  4
0x127bb  ldc.i4.0
0x127bc  blt.s    loc_127E1
0x127be  ldarg.2
0x127bf  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry> EntryList::Entries
0x127c4  ldloc.s  4
0x127c6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry>::get_Item(!!T0)
0x127cb  stloc.1
0x127cc  ldarg.2
0x127cd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry> EntryList::Entries
0x127d2  ldloc.s  4
0x127d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry>::RemoveAt(int32)
0x127d9  ldloc.1
0x127da  callvirt instance void Microsoft.ReportingServices.Library.ConnectionEntry::RequestFromPool()
0x127df  leave.s  loc_127F3
0x127e1  ldnull
0x127e2  stloc.s  5
0x127e4  leave    loc_12879
0x127e9  ldloc.3
0x127ea  brfalse.s loc_127F2
0x127ec  ldloc.2
0x127ed  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x127f2  endfinally
0x127f3  ldloc.1
0x127f4  brfalse.s loc_127FC
0x127f6  ldloc.1
0x127f7  call     void Microsoft.ReportingServices.Library.DbConnectionPoolLruCache::RemoveConnectionEntry(class Microsoft.ReportingServices.Library.ConnectionEntry connectionEntry)
0x127fc  nop
0x127fd  ldloc.1
0x127fe  callvirt instance bool Microsoft.ReportingServices.Library.ConnectionEntry::get_OKToGetFromPool()
0x12803  brfalse.s loc_12839
0x12805  ldloc.1
0x12806  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionKey Microsoft.ReportingServices.Library.ConnectionEntry::get_Key()
0x1280b  ldarg.1
0x1280c  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x12811  brfalse.s loc_12839
0x12813  ldloc.0
0x12814  brfalse.s loc_12823
0x12816  ldloc.1
0x12817  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbPoolableConnection Microsoft.ReportingServices.Library.ConnectionEntry::get_Connection()
0x1281c  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbPoolableConnection::get_IsAlive()
0x12821  brfalse.s loc_12839
0x12823  ldloc.1
0x12824  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbPoolableConnection Microsoft.ReportingServices.Library.ConnectionEntry::get_Connection()
0x12829  ldc.i4.1
0x1282a  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbPoolableConnection::set_IsFromPool(bool)
0x1282f  ldloc.1
0x12830  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbPoolableConnection Microsoft.ReportingServices.Library.ConnectionEntry::get_Connection()
0x12835  stloc.s  5
0x12837  leave.s  loc_12879
0x12839  leave.s  loc_1285F
0x1283b  stloc.s  6
0x1283d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x12842  ldc.i4.1
0x12843  ldstr    aExceptionOccur_0// "Exception occurred getting the connecti"...
0x12848  ldc.i4.1
0x12849  newarr   [mscorlib]System.Object
0x1284e  dup
0x1284f  ldc.i4.0
0x12850  ldloc.s  6
0x12852  callvirt instance string [mscorlib]System.Object::ToString()
0x12857  stelem.ref
0x12858  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1285d  leave.s  loc_1285F
0x1285f  ldarg.0
0x12860  ldloc.1
0x12861  call     instance void Microsoft.ReportingServices.Library.GlobalDbConnectionPool::CloseEntry(class Microsoft.ReportingServices.Library.ConnectionEntry entry)
0x12866  ldarg.2
0x12867  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry> EntryList::Entries
0x1286c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry>::get_Count()
0x12871  ldc.i4.0
0x12872  bgt      loc_1277C
0x12877  ldnull
0x12878  ret
0x12879  ldloc.s  5
0x1287b  ret
```
