# Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapperCache::RemoveCachedItems

- ea: `0x228d0`
- end: `0x22988`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapperCache::RemoveCachedItems`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x21730`
- `0x227d0`

## callees

- `0x21900`
- `0x22260`
- `0x228d0`
- `0x2ec30`
- `0x2ec70`

## string_xrefs

- `0x228e5`: `Removing a list of cached objects`
- `0x2297d`: `Removed a list of cached objects`

## pseudocode

```c

```

## disassembly

```asm
0x228d0  ldarg.2
0x228d1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x228d6  brtrue.s loc_228D9
0x228d8  ret
0x228d9  ldc.i4   0x7041C8
0x228de  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x228e3  ldc.i4.s 0x64
0x228e5  ldstr    aRemovingAListO// "Removing a list of cached objects"
0x228ea  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x228ef  ldarg.0
0x228f0  call     instance class [mscorlib]System.IDisposable class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey, class Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper>::AcquireWriterLock()
0x228f5  stloc.3
0x228f6  ldarg.2
0x228f7  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int32>::GetEnumerator()
0x228fc  stloc.s  4
0x228fe  br.s     loc_2294C
0x22900  ldloca.s 4
0x22902  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::get_Current()
0x22907  stloc.0
0x22908  ldarg.1
0x22909  ldloc.0
0x2290a  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey::.ctor(valuetype [mscorlib]System.Guid partitionId, int32 internalId)
0x2290f  stloc.1
0x22910  ldarg.0
0x22911  ldloc.1
0x22912  call     instance var<u1> class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey, class Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper>::get_Item(void)
0x22917  stloc.2
0x22918  ldloc.2
0x22919  brfalse.s loc_2294C
0x2291b  ldloc.2
0x2291c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItem Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper::get_Item()
0x22921  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_LastModifiedTime()
0x22926  ldarg.3
0x22927  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2292c  brfalse.s loc_2294C
0x2292e  ldarg.0
0x2292f  ldloc.1
0x22930  call     instance void class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey, class Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper>::RemoveKey(var<u1>)
0x22935  ldarg.0
0x22936  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper> Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapperCache::lookupBySharedItemKey
0x2293b  ldloc.2
0x2293c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItem Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper::get_Item()
0x22941  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemKey Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_SharedItemKey()
0x22946  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper>::Remove(var<u1>)
0x2294b  pop
0x2294c  ldloca.s 4
0x2294e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::MoveNext()
0x22953  brtrue.s loc_22900
0x22955  leave.s  loc_22965
0x22957  ldloca.s 4
0x22959  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>
0x2295f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22964  endfinally
0x22965  leave.s  loc_22971
0x22967  ldloc.3
0x22968  brfalse.s loc_22970
0x2296a  ldloc.3
0x2296b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22970  endfinally
0x22971  ldc.i4   0x7041C9
0x22976  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2297b  ldc.i4.s 0x64
0x2297d  ldstr    aRemovedAListOf// "Removed a list of cached objects"
0x22982  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x22987  ret
```
