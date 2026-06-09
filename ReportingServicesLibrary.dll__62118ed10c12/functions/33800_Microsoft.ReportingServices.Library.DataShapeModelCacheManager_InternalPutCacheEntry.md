# Microsoft.ReportingServices.Library.DataShapeModelCacheManager::InternalPutCacheEntry

- ea: `0x33800`
- end: `0x339e3`
- name: `Microsoft.ReportingServices.Library.DataShapeModelCacheManager::InternalPutCacheEntry`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x337d0`

## callees

- `0x33800`
- `0x33eb0`
- `0x33ec0`
- `0x33ed0`
- `0x33ef0`
- `0x33f00`
- `0x37ac0`
- `0x8a050`
- `0x8a090`

## string_xrefs

- `0x33810`: `ModelCache - PutCacheEntry: session.IsSessionIdValid`
- `0x3382e`: `ModelCache - CacheEntry - PUT: Session Key:{0}, Model Key:{1}, Sliding timeout: {2}, Absolute timeout: {3}, Model last updated time: {4}`
- `0x339c1`: `PutCacheEntry`

## pseudocode

```c

```

## disassembly

```asm
0x33800  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x33805  ldarg.0
0x33806  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheKey::get_Session()
0x3380b  callvirt instance bool Microsoft.ReportingServices.Library.IRenderEditSession::get_IsSessionIdValid()
0x33810  ldstr    aModelcachePutc// "ModelCache - PutCacheEntry: session.IsS"...
0x33815  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x3381a  ldarg.0
0x3381b  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.ModelCacheKey::get_SlidingExpiration()
0x33820  stloc.0
0x33821  ldarg.0
0x33822  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ModelCacheKey::get_AbsoluteExpiration()
0x33827  stloc.1
0x33828  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x3382d  ldc.i4.4
0x3382e  ldstr    aModelcacheCach_0// "ModelCache - CacheEntry - PUT: Session "...
0x33833  ldc.i4.5
0x33834  newarr   [mscorlib]System.Object
0x33839  dup
0x3383a  ldc.i4.0
0x3383b  ldarg.0
0x3383c  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_SessionKey()
0x33841  stelem.ref
0x33842  dup
0x33843  ldc.i4.1
0x33844  ldarg.0
0x33845  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x3384a  stelem.ref
0x3384b  dup
0x3384c  ldc.i4.2
0x3384d  ldloca.s 0
0x3384f  constrained. [mscorlib]System.TimeSpan
0x33855  callvirt instance string [mscorlib]System.Object::ToString()
0x3385a  stelem.ref
0x3385b  dup
0x3385c  ldc.i4.3
0x3385d  ldloca.s 1
0x3385f  call     instance string [mscorlib]System.DateTime::ToString()
0x33864  stelem.ref
0x33865  dup
0x33866  ldc.i4.4
0x33867  ldarg.2
0x33868  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x3386d  stelem.ref
0x3386e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33873  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.DataShapeModelCacheManager::m_cache
0x33878  ldarg.0
0x33879  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_SessionKey()
0x3387e  callvirt instance object [System.Web]System.Web.Caching.Cache::Get(string)
0x33883  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x33888  stloc.2
0x33889  ldloc.2
0x3388a  brtrue.s loc_338EB
0x3388c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x33891  stloc.s  6
0x33893  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.DataShapeModelCacheManager::m_cache
0x33898  stloc.s  7
0x3389a  ldc.i4.0
0x3389b  stloc.s  8
0x3389d  ldloc.s  7
0x3389f  ldloca.s 8
0x338a1  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x338a6  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.DataShapeModelCacheManager::m_cache
0x338ab  ldarg.0
0x338ac  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_SessionKey()
0x338b1  callvirt instance object [System.Web]System.Web.Caching.Cache::Get(string)
0x338b6  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x338bb  stloc.2
0x338bc  ldloc.2
0x338bd  brtrue.s loc_338DD
0x338bf  ldloc.s  6
0x338c1  stloc.2
0x338c2  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.DataShapeModelCacheManager::m_cache
0x338c7  ldarg.0
0x338c8  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_SessionKey()
0x338cd  ldloc.2
0x338ce  ldnull
0x338cf  ldloc.1
0x338d0  ldloc.0
0x338d1  ldc.i4.6
0x338d2  ldsfld   class [System.Web]System.Web.Caching.CacheItemRemovedCallback Microsoft.ReportingServices.Library.DataShapeModelCacheManager::m_cacheEvictionCallback
0x338d7  callvirt instance object [System.Web]System.Web.Caching.Cache::Add(string, object, class [System.Web]System.Web.Caching.CacheDependency, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan, valuetype [System.Web]System.Web.Caching.CacheItemPriority, class [System.Web]System.Web.Caching.CacheItemRemovedCallback)
0x338dc  pop
0x338dd  leave.s  loc_338EB
0x338df  ldloc.s  8
0x338e1  brfalse.s loc_338EA
0x338e3  ldloc.s  7
0x338e5  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x338ea  endfinally
0x338eb  ldarg.1
0x338ec  ldarg.2
0x338ed  newobj   instance void CacheEntry::.ctor(object value, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> modelLastUpdatedTime)
0x338f2  stloc.s  4
0x338f4  ldnull
0x338f5  stloc.s  5
0x338f7  ldloc.2
0x338f8  callvirt instance object [mscorlib]System.Collections.ICollection::get_SyncRoot()
0x338fd  stloc.s  9
0x338ff  ldc.i4.0
0x33900  stloc.s  8
0x33902  ldloc.s  9
0x33904  ldloca.s 8
0x33906  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x3390b  ldloc.2
0x3390c  ldarg.0
0x3390d  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x33912  ldloca.s 3
0x33914  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x33919  brfalse.s loc_33983
0x3391b  ldloc.3
0x3391c  castclass CacheEntry
0x33921  stloc.s  5
0x33923  ldarga.s 2
0x33925  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x3392a  brfalse.s loc_33973
0x3392c  ldloc.s  5
0x3392e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x33933  stloc.s  0xA
0x33935  ldloca.s 0xA
0x33937  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x3393c  brfalse.s loc_33973
0x3393e  ldloc.s  5
0x33940  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x33945  stloc.s  0xA
0x33947  ldarg.2
0x33948  stloc.s  0xB
0x3394a  ldloca.s 0xA
0x3394c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x33951  ldloca.s 0xB
0x33953  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x33958  and
0x33959  brtrue.s loc_3395E
0x3395b  ldc.i4.0
0x3395c  br.s     loc_33971
0x3395e  ldloca.s 0xA
0x33960  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x33965  ldloca.s 0xB
0x33967  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x3396c  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x33971  brfalse.s loc_33991
0x33973  ldloc.2
0x33974  ldarg.0
0x33975  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x3397a  ldloc.s  4
0x3397c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x33981  leave.s  loc_3399F
0x33983  ldloc.2
0x33984  ldarg.0
0x33985  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x3398a  ldloc.s  4
0x3398c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x33991  leave.s  loc_3399F
0x33993  ldloc.s  8
0x33995  brfalse.s loc_3399E
0x33997  ldloc.s  9
0x33999  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x3399e  endfinally
0x3399f  ldloc.s  5
0x339a1  brfalse.s loc_339E2
0x339a3  ldloc.s  5
0x339a5  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x339aa  stloc.s  0xB
0x339ac  ldloca.s 0xB
0x339ae  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x339b3  ldarga.s 2
0x339b5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x339ba  beq.s    loc_339E2
0x339bc  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventProvider::get_Current()
0x339c1  ldstr    aPutcacheentry// "PutCacheEntry"
0x339c6  ldloc.s  5
0x339c8  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x339cd  stloc.s  0xB
0x339cf  ldloca.s 0xB
0x339d1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x339d6  ldarga.s 2
0x339d8  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x339dd  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider::NotifyModelCacheLastUpdatedTimeMismatch(string, bool, bool)
0x339e2  ret
```
