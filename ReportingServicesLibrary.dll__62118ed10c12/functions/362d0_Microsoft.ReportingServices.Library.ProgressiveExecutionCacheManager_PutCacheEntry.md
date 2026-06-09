# Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::PutCacheEntry

- ea: `0x362d0`
- end: `0x363b0`
- name: `Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::PutCacheEntry`
- size: `224`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x35c90`
- `0x35e20`
- `0x37700`

## callees

- `0x362d0`
- `0x37a70`
- `0x37a80`
- `0x37a90`
- `0x37ac0`
- `0x37b00`

## string_xrefs

- `0x362e1`: `PutCacheEntry: session != null && session.IsSessionIdValid`
- `0x3632a`: `CacheEntry - PUT: `
- `0x36364`: `; path: `

## pseudocode

```c

```

## disassembly

```asm
0x362d0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x362d5  ldarg.0
0x362d6  brfalse.s loc_362E0
0x362d8  ldarg.0
0x362d9  callvirt instance bool Microsoft.ReportingServices.Library.IRenderEditSession::get_IsSessionIdValid()
0x362de  br.s     loc_362E1
0x362e0  ldc.i4.0
0x362e1  ldstr    aPutcacheentryS// "PutCacheEntry: session != null && sessi"...
0x362e6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x362eb  ldarg.0
0x362ec  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::MakeCacheKey()
0x362f1  stloc.0
0x362f2  ldloca.s 1
0x362f4  ldc.i4.0
0x362f5  ldc.i4.0
0x362f6  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x362fb  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_RdlxSessionTimeout()
0x36300  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x36305  ldarg.0
0x36306  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.IRenderEditSession::get_ItemPath()
0x3630b  brfalse.s loc_3631A
0x3630d  ldarg.0
0x3630e  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.IRenderEditSession::get_ItemPath()
0x36313  callvirt instance string [mscorlib]System.Object::ToString()
0x36318  br.s     loc_3631B
0x3631a  ldnull
0x3631b  stloc.2
0x3631c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x36321  ldc.i4.4
0x36322  ldc.i4.8
0x36323  newarr   [mscorlib]System.String
0x36328  dup
0x36329  ldc.i4.0
0x3632a  ldstr    aCacheentryPut// "CacheEntry - PUT: "
0x3632f  stelem.ref
0x36330  dup
0x36331  ldc.i4.1
0x36332  ldarg.0
0x36333  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_SessionId()
0x36338  stelem.ref
0x36339  dup
0x3633a  ldc.i4.2
0x3633b  ldstr    aSlidingTimeout// "; sliding timeout: "
0x36340  stelem.ref
0x36341  dup
0x36342  ldc.i4.3
0x36343  ldloca.s 1
0x36345  constrained. [mscorlib]System.TimeSpan
0x3634b  callvirt instance string [mscorlib]System.Object::ToString()
0x36350  stelem.ref
0x36351  dup
0x36352  ldc.i4.4
0x36353  ldstr    aUser// "; user: "
0x36358  stelem.ref
0x36359  dup
0x3635a  ldc.i4.5
0x3635b  ldarg.0
0x3635c  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_UserName()
0x36361  stelem.ref
0x36362  dup
0x36363  ldc.i4.6
0x36364  ldstr    aPath_1// "; path: "
0x36369  stelem.ref
0x3636a  dup
0x3636b  ldc.i4.7
0x3636c  ldloc.2
0x3636d  stelem.ref
0x3636e  call     string [mscorlib]System.String::Concat(string[])
0x36373  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x36378  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::m_cache
0x3637d  ldloc.0
0x3637e  ldarg.1
0x3637f  ldnull
0x36380  ldsfld   valuetype [mscorlib]System.DateTime [System.Web]System.Web.Caching.Cache::NoAbsoluteExpiration
0x36385  ldloc.1
0x36386  ldc.i4.6
0x36387  ldsfld   class [System.Web]System.Web.Caching.CacheItemRemovedCallback Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::m_cacheEvictionCallback
0x3638c  callvirt instance void [System.Web]System.Web.Caching.Cache::Insert(string, object, class [System.Web]System.Web.Caching.CacheDependency, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan, valuetype [System.Web]System.Web.Caching.CacheItemPriority, class [System.Web]System.Web.Caching.CacheItemRemovedCallback)
0x36391  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::get_Current()
0x36396  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICounter [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::get_ActiveSession()
0x3639b  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICounter::Increment()
0x363a0  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::get_Current()
0x363a5  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICounter [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::get_NewSessionTotal()
0x363aa  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICounter::Increment()
0x363af  ret
```
