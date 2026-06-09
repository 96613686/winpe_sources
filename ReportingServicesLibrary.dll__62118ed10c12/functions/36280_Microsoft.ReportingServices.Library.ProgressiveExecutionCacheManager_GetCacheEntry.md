# Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::GetCacheEntry

- ea: `0x36280`
- end: `0x362d0`
- name: `Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::GetCacheEntry`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x36500`
- `0x36570`

## callees

- `0x36280`
- `0x37a70`
- `0x37ac0`
- `0x37b00`

## string_xrefs

- `0x36289`: `GetCacheEntry: session != null`
- `0x362ba`: `CacheEntry - GET: `

## pseudocode

```c

```

## disassembly

```asm
0x36280  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x36285  ldarg.0
0x36286  ldnull
0x36287  cgt.un
0x36289  ldstr    aGetcacheentryS// "GetCacheEntry: session != null"
0x3628e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x36293  ldarg.0
0x36294  callvirt instance bool Microsoft.ReportingServices.Library.IRenderEditSession::get_IsSessionIdValid()
0x36299  brtrue.s loc_3629D
0x3629b  ldnull
0x3629c  ret
0x3629d  ldarg.0
0x3629e  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::MakeCacheKey()
0x362a3  stloc.0
0x362a4  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::m_cache
0x362a9  ldloc.0
0x362aa  callvirt instance object [System.Web]System.Web.Caching.Cache::Get(string)
0x362af  isinst   Microsoft.ReportingServices.Library.ProgressiveCacheEntry
0x362b4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x362b9  ldc.i4.4
0x362ba  ldstr    aCacheentryGet// "CacheEntry - GET: "
0x362bf  ldarg.0
0x362c0  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_SessionId()
0x362c5  call     string [mscorlib]System.String::Concat(string, string)
0x362ca  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x362cf  ret
```
