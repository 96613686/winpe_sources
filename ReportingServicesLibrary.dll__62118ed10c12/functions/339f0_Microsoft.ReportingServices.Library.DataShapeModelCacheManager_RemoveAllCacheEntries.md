# Microsoft.ReportingServices.Library.DataShapeModelCacheManager::RemoveAllCacheEntries

- ea: `0x339f0`
- end: `0x33a9f`
- name: `Microsoft.ReportingServices.Library.DataShapeModelCacheManager::RemoveAllCacheEntries`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x339f0`
- `0x33cc0`
- `0x33e70`
- `0x37a70`
- `0x37a80`

## string_xrefs

- `0x33a1b`: `ModelCache - CacheEntry - REMOVE: {0}; user: {1}, modelScope: {2}`
- `0x33a5e`: `ModelCache - CacheEntry - REMOVE: {0} (modelScope: {1}) not found in cache`

## pseudocode

```c

```

## disassembly

```asm
0x339f0  ldtoken  Microsoft.ReportingServices.Library.ModelCacheScope
0x339f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x339fa  call     class [mscorlib]System.Array [mscorlib]System.Enum::GetValues(class [mscorlib]System.Type)
0x339ff  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Array::GetEnumerator()
0x33a04  stloc.0
0x33a05  br.s     loc_33A80
0x33a07  ldloc.0
0x33a08  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x33a0d  stloc.1
0x33a0e  ldarg.0
0x33a0f  call     string Microsoft.ReportingServices.Library.ModelCacheKey::MakeSessionKey(class Microsoft.ReportingServices.Library.ModelCacheInfo modelCacheInfo)
0x33a14  stloc.2
0x33a15  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x33a1a  ldc.i4.4
0x33a1b  ldstr    aModelcacheCach_1// "ModelCache - CacheEntry - REMOVE: {0}; "...
0x33a20  ldc.i4.3
0x33a21  newarr   [mscorlib]System.Object
0x33a26  dup
0x33a27  ldc.i4.0
0x33a28  ldarg.0
0x33a29  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheInfo::get_Session()
0x33a2e  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_SessionId()
0x33a33  stelem.ref
0x33a34  dup
0x33a35  ldc.i4.1
0x33a36  ldarg.0
0x33a37  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheInfo::get_Session()
0x33a3c  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_UserName()
0x33a41  stelem.ref
0x33a42  dup
0x33a43  ldc.i4.2
0x33a44  ldloc.1
0x33a45  stelem.ref
0x33a46  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33a4b  ldsfld   class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.DataShapeModelCacheManager::m_cache
0x33a50  ldloc.2
0x33a51  callvirt instance object [System.Web]System.Web.Caching.Cache::Remove(string)
0x33a56  brtrue.s loc_33A80
0x33a58  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x33a5d  ldc.i4.4
0x33a5e  ldstr    aModelcacheCach_2// "ModelCache - CacheEntry - REMOVE: {0} ("...
0x33a63  ldc.i4.2
0x33a64  newarr   [mscorlib]System.Object
0x33a69  dup
0x33a6a  ldc.i4.0
0x33a6b  ldarg.0
0x33a6c  callvirt instance class Microsoft.ReportingServices.Library.IRenderEditSession Microsoft.ReportingServices.Library.ModelCacheInfo::get_Session()
0x33a71  callvirt instance string Microsoft.ReportingServices.Library.IRenderEditSession::get_SessionId()
0x33a76  stelem.ref
0x33a77  dup
0x33a78  ldc.i4.1
0x33a79  ldloc.1
0x33a7a  stelem.ref
0x33a7b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33a80  ldloc.0
0x33a81  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33a86  brtrue   loc_33A07
0x33a8b  leave.s  loc_33A9E
0x33a8d  ldloc.0
0x33a8e  isinst   [mscorlib]System.IDisposable
0x33a93  stloc.3
0x33a94  ldloc.3
0x33a95  brfalse.s loc_33A9D
0x33a97  ldloc.3
0x33a98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33a9d  endfinally
0x33a9e  ret
```
