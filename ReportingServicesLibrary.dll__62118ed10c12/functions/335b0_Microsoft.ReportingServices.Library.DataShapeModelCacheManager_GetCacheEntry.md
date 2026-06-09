# Microsoft.ReportingServices.Library.DataShapeModelCacheManager::GetCacheEntry

- ea: `0x335b0`
- end: `0x337c2`
- name: `Microsoft.ReportingServices.Library.DataShapeModelCacheManager::GetCacheEntry`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x335b0`
- `0x33eb0`
- `0x33ec0`
- `0x33ed0`
- `0x37ac0`
- `0x8a070`
- `0x8a090`

## string_xrefs

- `0x335c5`: `ModelCache - CacheEntry - GET: Session Key:{0} , Model Key:{1}, Model last updated time={2}`
- `0x3366e`: `GetCacheEntry`
- `0x33767`: `Local model cache: removing cached model due to ModelLastUpdatedTime change. Cached ModelLastModifiedTime={0}, new ModelLastModifiedTime={1}, modelKey={2}`

## pseudocode

```c

```

## disassembly

```asm
0x335b0  ldarg.0
0x335b1  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheKey::get_Session()
0x335b6  callvirt instance bool Microsoft.ReportingServices.Library.IRenderEditSession::get_IsSessionIdValid()
0x335bb  brtrue.s loc_335BF
0x335bd  ldnull
0x335be  ret
0x335bf  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x335c4  ldc.i4.4
0x335c5  ldstr    aModelcacheCach// "ModelCache - CacheEntry - GET: Session "...
0x335ca  ldc.i4.3
0x335cb  newarr   [mscorlib]System.Object
0x335d0  dup
0x335d1  ldc.i4.0
0x335d2  ldarg.0
0x335d3  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_SessionKey()
0x335d8  stelem.ref
0x335d9  dup
0x335da  ldc.i4.1
0x335db  ldarg.0
0x335dc  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x335e1  stelem.ref
0x335e2  dup
0x335e3  ldc.i4.2
0x335e4  ldarg.1
0x335e5  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x335ea  stelem.ref
0x335eb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x335f0  ldnull
0x335f1  stloc.0
0x335f2  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.DataShapeModelCacheManager::m_cache
0x335f7  ldarg.0
0x335f8  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_SessionKey()
0x335fd  callvirt instance object [System.Web]System.Web.Caching.Cache::Get(string)
0x33602  isinst   class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>
0x33607  stloc.1
0x33608  ldloc.1
0x33609  brfalse  loc_337BD
0x3360e  ldloc.1
0x3360f  castclass [mscorlib]System.Collections.ICollection
0x33614  callvirt instance object [mscorlib]System.Collections.ICollection::get_SyncRoot()
0x33619  stloc.3
0x3361a  ldc.i4.0
0x3361b  stloc.s  4
0x3361d  ldloc.3
0x3361e  ldloca.s 4
0x33620  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x33625  ldloc.1
0x33626  ldarg.0
0x33627  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x3362c  ldloca.s 0
0x3362e  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x33633  brtrue.s loc_3363D
0x33635  ldnull
0x33636  stloc.s  5
0x33638  leave    loc_337BF
0x3363d  leave.s  loc_3364A
0x3363f  ldloc.s  4
0x33641  brfalse.s loc_33649
0x33643  ldloc.3
0x33644  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x33649  endfinally
0x3364a  ldloc.0
0x3364b  castclass CacheEntry
0x33650  stloc.2
0x33651  ldloc.2
0x33652  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x33657  stloc.s  6
0x33659  ldloca.s 6
0x3365b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x33660  ldarga.s 1
0x33662  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x33667  beq.s    loc_336C5
0x33669  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventProvider::get_Current()
0x3366e  ldstr    aGetcacheentry// "GetCacheEntry"
0x33673  ldloc.2
0x33674  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x33679  stloc.s  6
0x3367b  ldloca.s 6
0x3367d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x33682  ldarga.s 1
0x33684  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x33689  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider::NotifyModelCacheLastUpdatedTimeMismatch(string, bool, bool)
0x3368e  ldloc.1
0x3368f  castclass [mscorlib]System.Collections.ICollection
0x33694  callvirt instance object [mscorlib]System.Collections.ICollection::get_SyncRoot()
0x33699  stloc.3
0x3369a  ldc.i4.0
0x3369b  stloc.s  4
0x3369d  ldloc.3
0x3369e  ldloca.s 4
0x336a0  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x336a5  ldloc.1
0x336a6  ldarg.0
0x336a7  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x336ac  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Remove(var<u1>)
0x336b1  pop
0x336b2  ldnull
0x336b3  stloc.s  5
0x336b5  leave    loc_337BF
0x336ba  ldloc.s  4
0x336bc  brfalse.s loc_336C4
0x336be  ldloc.3
0x336bf  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x336c4  endfinally
0x336c5  ldloc.2
0x336c6  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x336cb  stloc.s  6
0x336cd  ldarg.1
0x336ce  stloc.s  7
0x336d0  ldloca.s 6
0x336d2  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x336d7  ldloca.s 7
0x336d9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x336de  and
0x336df  brtrue.s loc_336E4
0x336e1  ldc.i4.0
0x336e2  br.s     loc_336F7
0x336e4  ldloca.s 6
0x336e6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x336eb  ldloca.s 7
0x336ed  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x336f2  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x336f7  brfalse  loc_337B6
0x336fc  ldloc.1
0x336fd  castclass [mscorlib]System.Collections.ICollection
0x33702  callvirt instance object [mscorlib]System.Collections.ICollection::get_SyncRoot()
0x33707  stloc.3
0x33708  ldc.i4.0
0x33709  stloc.s  4
0x3370b  ldloc.3
0x3370c  ldloca.s 4
0x3370e  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x33713  ldloc.1
0x33714  ldarg.0
0x33715  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x3371a  ldloca.s 0
0x3371c  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x33721  brfalse  loc_337A9
0x33726  ldloc.0
0x33727  castclass CacheEntry
0x3372c  stloc.2
0x3372d  ldloc.2
0x3372e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x33733  stloc.s  7
0x33735  ldarg.1
0x33736  stloc.s  6
0x33738  ldloca.s 7
0x3373a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x3373f  ldloca.s 6
0x33741  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x33746  and
0x33747  brtrue.s loc_3374C
0x33749  ldc.i4.0
0x3374a  br.s     loc_3375F
0x3374c  ldloca.s 7
0x3374e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x33753  ldloca.s 6
0x33755  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x3375a  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3375f  brfalse.s loc_337A9
0x33761  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x33766  ldc.i4.3
0x33767  ldstr    aLocalModelCach// "Local model cache: removing cached mode"...
0x3376c  ldc.i4.3
0x3376d  newarr   [mscorlib]System.Object
0x33772  dup
0x33773  ldc.i4.0
0x33774  ldloc.2
0x33775  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> CacheEntry::get_ModelLastUpdatedTime()
0x3377a  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x3377f  stelem.ref
0x33780  dup
0x33781  ldc.i4.1
0x33782  ldarg.1
0x33783  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x33788  stelem.ref
0x33789  dup
0x3378a  ldc.i4.2
0x3378b  ldarg.0
0x3378c  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x33791  stelem.ref
0x33792  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33797  ldloc.1
0x33798  ldarg.0
0x33799  callvirt instance string Microsoft.ReportingServices.Library.ModelCacheKey::get_ModelKey()
0x3379e  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Remove(var<u1>)
0x337a3  pop
0x337a4  ldnull
0x337a5  stloc.s  5
0x337a7  leave.s  loc_337BF
0x337a9  leave.s  loc_337B6
0x337ab  ldloc.s  4
0x337ad  brfalse.s loc_337B5
0x337af  ldloc.3
0x337b0  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x337b5  endfinally
0x337b6  ldloc.2
0x337b7  callvirt instance object CacheEntry::get_Value()
0x337bc  ret
0x337bd  ldnull
0x337be  ret
0x337bf  ldloc.s  5
0x337c1  ret
```
