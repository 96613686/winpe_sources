# Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::CleanupEvictedCacheEntry

- ea: `0x36430`
- end: `0x364fa`
- name: `Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::CleanupEvictedCacheEntry`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x36430`
- `0x36850`

## string_xrefs

- `0x36469`: `Cache entry isn't a ProgressiveCacheEntry, logging eviction with Guid.Empty`
- `0x36491`: `CacheEntry - Cleanup: `
- `0x364e2`: `Error removing cached item: `

## pseudocode

```c

```

## disassembly

```asm
0x36430  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x36435  pop
0x36436  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3643b  pop
0x3643c  ldarg.1
0x3643d  isinst   Microsoft.ReportingServices.Library.ProgressiveCacheEntry
0x36442  stloc.0
0x36443  ldloc.0
0x36444  brfalse.s loc_3644F
0x36446  ldloc.0
0x36447  callvirt instance string Microsoft.ReportingServices.Library.ProgressiveCacheEntry::get_ClientActivityId()
0x3644c  pop
0x3644d  br.s     loc_36473
0x3644f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36454  stloc.1
0x36455  ldloca.s 1
0x36457  constrained. [mscorlib]System.Guid
0x3645d  callvirt instance string [mscorlib]System.Object::ToString()
0x36462  pop
0x36463  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x36468  ldc.i4.1
0x36469  ldstr    aCacheEntryIsnT// "Cache entry isn't a ProgressiveCacheEnt"...
0x3646e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x36473  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventProvider::get_Current()
0x36478  ldarg.0
0x36479  ldarga.s 2
0x3647b  constrained. [System.Web]System.Web.Caching.CacheItemRemovedReason
0x36481  callvirt instance string [mscorlib]System.Object::ToString()
0x36486  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider::NotifySessionEvicted(string, string)
0x3648b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x36490  ldc.i4.4
0x36491  ldstr    aCacheentryClea// "CacheEntry - Cleanup: "
0x36496  ldarg.0
0x36497  ldstr    aReason// "; reason: "
0x3649c  ldarga.s 2
0x3649e  constrained. [System.Web]System.Web.Caching.CacheItemRemovedReason
0x364a4  callvirt instance string [mscorlib]System.Object::ToString()
0x364a9  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x364ae  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x364b3  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::get_Current()
0x364b8  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICounter [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::get_ActiveSession()
0x364bd  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICounter::Decrement()
0x364c2  ldarg.1
0x364c3  castclass [mscorlib]System.IDisposable
0x364c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x364cd  leave.s  loc_364F9
0x364cf  stloc.2
0x364d0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x364d5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x364da  brfalse.s loc_364F7
0x364dc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x364e1  ldc.i4.1
0x364e2  ldstr    aErrorRemovingC// "Error removing cached item: "
0x364e7  ldloc.2
0x364e8  callvirt instance string [mscorlib]System.Object::ToString()
0x364ed  call     string [mscorlib]System.String::Concat(string, string)
0x364f2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x364f7  leave.s  loc_364F9
0x364f9  ret
```
