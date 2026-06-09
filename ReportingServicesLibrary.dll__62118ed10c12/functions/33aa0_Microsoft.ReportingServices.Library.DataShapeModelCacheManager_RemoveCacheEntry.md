# Microsoft.ReportingServices.Library.DataShapeModelCacheManager::RemoveCacheEntry

- ea: `0x33aa0`
- end: `0x33b21`
- name: `Microsoft.ReportingServices.Library.DataShapeModelCacheManager::RemoveCacheEntry`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x33b30`

## callees

- `0x33aa0`
- `0x33c00`
- `0x33cc0`
- `0x33e70`
- `0x37a70`
- `0x37a80`
- `0x37ac0`

## string_xrefs

- `0x33ac3`: `ModelCache - CacheEntry - REMOVE: {0}; user: {1}`
- `0x33b02`: `ModelCache - CacheEntry - REMOVE: {0} not found in cache`

## pseudocode

```c

```

## disassembly

```asm
0x33aa0  ldarg.0
0x33aa1  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheInfo::get_Session()
0x33aa6  callvirt instance bool Microsoft.ReportingServices.Library.IRenderEditSession::get_IsSessionIdValid()
0x33aab  brfalse.s loc_33AB5
0x33aad  ldarg.0
0x33aae  call     valuetype Microsoft.ReportingServices.Library.ModelCacheScope Microsoft.ReportingServices.Library.DataShapeModelCacheManager::DetermineModelCacheScope(class Microsoft.ReportingServices.Library.ModelCacheInfo cacheInfo)
0x33ab3  brtrue.s loc_33AB6
0x33ab5  ret
0x33ab6  ldarg.0
0x33ab7  call     string Microsoft.ReportingServices.Library.ModelCacheKey::MakeSessionKey(class Microsoft.ReportingServices.Library.ModelCacheInfo modelCacheInfo)
0x33abc  stloc.0
0x33abd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x33ac2  ldc.i4.4
0x33ac3  ldstr    aModelcacheCach_3// "ModelCache - CacheEntry - REMOVE: {0}; "...
0x33ac8  ldc.i4.2
0x33ac9  newarr   [mscorlib]System.Object
0x33ace  dup
0x33acf  ldc.i4.0
0x33ad0  ldarg.0
0x33ad1  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheInfo::get_Session()
0x33ad6  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_SessionId()
0x33adb  stelem.ref
0x33adc  dup
0x33add  ldc.i4.1
0x33ade  ldarg.0
0x33adf  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheInfo::get_Session()
0x33ae4  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_UserName()
0x33ae9  stelem.ref
0x33aea  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33aef  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.DataShapeModelCacheManager::m_cache
0x33af4  ldloc.0
0x33af5  callvirt instance object [System.Web]System.Web.Caching.Cache::Remove(string)
0x33afa  brtrue.s loc_33B20
0x33afc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x33b01  ldc.i4.4
0x33b02  ldstr    aModelcacheCach_4// "ModelCache - CacheEntry - REMOVE: {0} n"...
0x33b07  ldc.i4.1
0x33b08  newarr   [mscorlib]System.Object
0x33b0d  dup
0x33b0e  ldc.i4.0
0x33b0f  ldarg.0
0x33b10  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheInfo::get_Session()
0x33b15  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_SessionId()
0x33b1a  stelem.ref
0x33b1b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33b20  ret
```
