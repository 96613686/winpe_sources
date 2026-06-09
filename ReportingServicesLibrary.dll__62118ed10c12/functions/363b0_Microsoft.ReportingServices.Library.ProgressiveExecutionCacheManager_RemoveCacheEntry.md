# Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::RemoveCacheEntry

- ea: `0x363b0`
- end: `0x36427`
- name: `Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::RemoveCacheEntry`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x6ce60`

## callees

- `0x363b0`
- `0x37a70`
- `0x37a80`
- `0x37ac0`
- `0x37b00`

## string_xrefs

- `0x363b9`: `RemoveCacheEntry: session != null`
- `0x363d9`: `CacheEntry - REMOVE: `
- `0x3640c`: `CacheEntry - REMOVE: `
- `0x36417`: ` not found in cache`

## pseudocode

```c

```

## disassembly

```asm
0x363b0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x363b5  ldarg.0
0x363b6  ldnull
0x363b7  cgt.un
0x363b9  ldstr    aRemovecacheent// "RemoveCacheEntry: session != null"
0x363be  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x363c3  ldarg.0
0x363c4  callvirt instance bool Microsoft.ReportingServices.Library.IRenderEditSession::get_IsSessionIdValid()
0x363c9  brtrue.s loc_363CC
0x363cb  ret
0x363cc  ldarg.0
0x363cd  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::MakeCacheKey()
0x363d2  stloc.0
0x363d3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x363d8  ldc.i4.4
0x363d9  ldstr    aCacheentryRemo// "CacheEntry - REMOVE: "
0x363de  ldarg.0
0x363df  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_SessionId()
0x363e4  ldstr    aUser// "; user: "
0x363e9  ldarg.0
0x363ea  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_UserName()
0x363ef  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x363f4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x363f9  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::m_cache
0x363fe  ldloc.0
0x363ff  callvirt instance object [System.Web]System.Web.Caching.Cache::Remove(string)
0x36404  brtrue.s loc_36426
0x36406  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x3640b  ldc.i4.4
0x3640c  ldstr    aCacheentryRemo// "CacheEntry - REMOVE: "
0x36411  ldarg.0
0x36412  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_SessionId()
0x36417  ldstr    aNotFoundInCach// " not found in cache"
0x3641c  call     string [mscorlib]System.String::Concat(string, string, string)
0x36421  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x36426  ret
```
