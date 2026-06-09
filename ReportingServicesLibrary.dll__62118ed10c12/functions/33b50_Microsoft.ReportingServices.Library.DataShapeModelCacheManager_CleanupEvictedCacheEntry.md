# Microsoft.ReportingServices.Library.DataShapeModelCacheManager::CleanupEvictedCacheEntry

- ea: `0x33b50`
- end: `0x33bd9`
- name: `Microsoft.ReportingServices.Library.DataShapeModelCacheManager::CleanupEvictedCacheEntry`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x33b50`

## string_xrefs

- `0x33b56`: `ModelCache - CacheEntry - Cleanup: {0}; reason: {1}`
- `0x33bc1`: `ModelCache - Error disposing cached item: `

## pseudocode

```c

```

## disassembly

```asm
0x33b50  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x33b55  ldc.i4.4
0x33b56  ldstr    aModelcacheCach_5// "ModelCache - CacheEntry - Cleanup: {0};"...
0x33b5b  ldc.i4.2
0x33b5c  newarr   [mscorlib]System.Object
0x33b61  dup
0x33b62  ldc.i4.0
0x33b63  ldarg.0
0x33b64  stelem.ref
0x33b65  dup
0x33b66  ldc.i4.1
0x33b67  ldarga.s 2
0x33b69  constrained. [System.Web]System.Web.Caching.CacheItemRemovedReason
0x33b6f  callvirt instance string [mscorlib]System.Object::ToString()
0x33b74  stelem.ref
0x33b75  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33b7a  ldarg.1
0x33b7b  isinst   class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>
0x33b80  stloc.0
0x33b81  ldloc.0
0x33b82  brfalse.s loc_33BAC
0x33b84  ldloc.0
0x33b85  castclass [mscorlib]System.Collections.ICollection
0x33b8a  callvirt instance object [mscorlib]System.Collections.ICollection::get_SyncRoot()
0x33b8f  stloc.1
0x33b90  ldc.i4.0
0x33b91  stloc.2
0x33b92  ldloc.1
0x33b93  ldloca.s 2
0x33b95  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x33b9a  ldloc.0
0x33b9b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::Clear()
0x33ba0  leave.s  loc_33BAC
0x33ba2  ldloc.2
0x33ba3  brfalse.s loc_33BAB
0x33ba5  ldloc.1
0x33ba6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x33bab  endfinally
0x33bac  leave.s  loc_33BD8
0x33bae  stloc.3
0x33baf  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x33bb4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x33bb9  brfalse.s loc_33BD6
0x33bbb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x33bc0  ldc.i4.1
0x33bc1  ldstr    aModelcacheErro// "ModelCache - Error disposing cached ite"...
0x33bc6  ldloc.3
0x33bc7  callvirt instance string [mscorlib]System.Object::ToString()
0x33bcc  call     string [mscorlib]System.String::Concat(string, string)
0x33bd1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x33bd6  leave.s  loc_33BD8
0x33bd8  ret
```
