# Microsoft.SharePoint.Taxonomy.Internal.CombinableCache`2::RemoveIfAlone

- ea: `0x20c30`
- end: `0x20d5d`
- name: `Microsoft.SharePoint.Taxonomy.Internal.CombinableCache`2::RemoveIfAlone`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x20aa0`
- `0x20c30`
- `0x22250`
- `0x22270`

## string_xrefs

- `0x20c3c`: `Calculating cache entries to remove: start`
- `0x20c63`: `Nothing to remove from this cache.`
- `0x20cba`: `Adjusting the cache entry count.`
- `0x20d37`: `Adjusted the cache entry count.`
- `0x20d51`: `Calculating cache entries to remove: end`

## pseudocode

```c

```

## disassembly

```asm
0x20c30  ldc.i4   0x3134616B
0x20c35  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20c3a  ldc.i4.s 0x64
0x20c3c  ldstr    aCalculatingCac// "Calculating cache entries to remove: st"...
0x20c41  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20c46  ldarg.0
0x20c47  call     instance int32 class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<var<u1>, !!T0>::get_Count()
0x20c4c  stloc.0
0x20c4d  ldloc.0
0x20c4e  newarr   Microsoft.SharePoint.Taxonomy.Internal.CountableEntry
0x20c53  stloc.1
0x20c54  ldloc.0
0x20c55  brtrue.s loc_20C6F
0x20c57  ldc.i4   0x3134616C
0x20c5c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20c61  ldc.i4.s 0x64
0x20c63  ldstr    aNothingToRemov// "Nothing to remove from this cache."
0x20c68  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20c6d  ldloc.1
0x20c6e  ret
0x20c6f  ldloc.0
0x20c70  newarr   class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2/CacheEntry`2<var<u1>, !!T0, var<u1>, void>
0x20c75  stloc.2
0x20c76  ldarg.0
0x20c77  call     instance class [mscorlib]System.IDisposable class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<var<u1>, !!T0>::AcquireReaderLock()
0x20c7c  stloc.s  7
0x20c7e  ldarg.0
0x20c7f  call     instance class [mscorlib]System.Collections.Hashtable class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<var<u1>, !!T0>::get_HashTable()
0x20c84  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x20c89  ldloc.2
0x20c8a  ldc.i4.0
0x20c8b  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x20c90  leave.s  loc_20C9E
0x20c92  ldloc.s  7
0x20c94  brfalse.s loc_20C9D
0x20c96  ldloc.s  7
0x20c98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20c9d  endfinally
0x20c9e  ldloc.2
0x20c9f  newobj   instance void class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2/CacheEntry`2/SortByUsageCount<var<u1>, !!T0, var<u1>, void>::.ctor()
0x20ca4  call     void [mscorlib]System.Array::Sort(class [mscorlib]System.Array, class [mscorlib]System.Collections.IComparer)
0x20ca9  ldc.i4.0
0x20caa  stloc.3
0x20cab  ldc.i4.0
0x20cac  stloc.s  4
0x20cae  ldc.i4   0x3134616D
0x20cb3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20cb8  ldc.i4.s 0x64
0x20cba  ldstr    aAdjustingTheCa// "Adjusting the cache entry count."
0x20cbf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20cc4  ldloc.2
0x20cc5  stloc.s  8
0x20cc7  ldc.i4.0
0x20cc8  stloc.s  9
0x20cca  br.s     loc_20D23
0x20ccc  ldloc.s  8
0x20cce  ldloc.s  9
0x20cd0  ldelem.ref
0x20cd1  stloc.s  5
0x20cd3  ldloc.s  5
0x20cd5  ldarg.2
0x20cd6  callvirt instance void class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2/CacheEntry`2<var<u1>, !!T0, var<u1>, void>::DecrementCount(float64)
0x20cdb  ldloc.3
0x20cdc  ldarg.1
0x20cdd  bge.s    loc_20D1D
0x20cdf  ldloc.s  5
0x20ce1  callvirt instance var<u1> class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2/CacheEntry`2<var<u1>, !!T0, var<u1>, void>::get_Value()
0x20ce6  stloc.s  6
0x20ce8  ldloc.1
0x20ce9  ldloc.s  4
0x20ceb  ldloc.s  5
0x20ced  callvirt instance var<u1> class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2/CacheEntry`2<var<u1>, !!T0, var<u1>, void>::get_Key()
0x20cf2  ldloc.s  6
0x20cf4  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper::get_EstimatedSize()
0x20cf9  ldloc.s  6
0x20cfb  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper::get_Type()
0x20d00  ldloc.s  5
0x20d02  callvirt instance int32 class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2/CacheEntry`2<var<u1>, !!T0, var<u1>, void>::get_Count()
0x20d07  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.CountableEntry::.ctor(class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey sharedItemInternalKey, int32 size, valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType type, int32 count)
0x20d0c  stelem.ref
0x20d0d  ldloc.s  4
0x20d0f  ldc.i4.1
0x20d10  add.ovf
0x20d11  stloc.s  4
0x20d13  ldloc.3
0x20d14  ldloc.s  6
0x20d16  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper::get_EstimatedSize()
0x20d1b  add.ovf
0x20d1c  stloc.3
0x20d1d  ldloc.s  9
0x20d1f  ldc.i4.1
0x20d20  add
0x20d21  stloc.s  9
0x20d23  ldloc.s  9
0x20d25  ldloc.s  8
0x20d27  ldlen
0x20d28  conv.i4
0x20d29  blt.s    loc_20CCC
0x20d2b  ldc.i4   0x3134616E
0x20d30  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20d35  ldc.i4.s 0x64
0x20d37  ldstr    aAdjustedTheCac// "Adjusted the cache entry count."
0x20d3c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20d41  ldarg.3
0x20d42  ldloc.s  4
0x20d44  stind.i4
0x20d45  ldc.i4   0x3134616F
0x20d4a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20d4f  ldc.i4.s 0x64
0x20d51  ldstr    aCalculatingCac_0// "Calculating cache entries to remove: en"...
0x20d56  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20d5b  ldloc.1
0x20d5c  ret
```
