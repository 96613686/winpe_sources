# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::GetCachedChanges

- ea: `0x1b010`
- end: `0x1b211`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::GetCachedChanges`
- size: `513`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1d080`
- `0x1d1e0`

## callees

- `0x1b010`
- `0x1b230`
- `0x1b2a0`
- `0x72d20`

## string_xrefs

- `0x1b0a5`: `Taxonomy database change cache miss - expired. ContentDB:{0}; SinceTime:{1}`
- `0x1b15f`: `Taxonomy database change cache hit. ContentDB:{0}; SinceTime:{1}`
- `0x1b1be`: `Taxonomy database change cache miss - different sinceTime. ContentDB:{0}; SinceTime:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x1b010  ldnull
0x1b011  stloc.s  4
0x1b013  newobj   instance void <>c__DisplayClass5::.ctor()
0x1b018  stloc.s  5
0x1b01a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1b01f  stloc.0
0x1b020  ldc.i4.0
0x1b021  stloc.1
0x1b022  ldnull
0x1b023  stloc.2
0x1b024  ldarg.0
0x1b025  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::ClearCacheIfFull()
0x1b02a  ldloc.s  5
0x1b02c  ldarg.0
0x1b02d  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class CacheChangeInfo> Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::contentDatabaseChangeInfoCache
0x1b032  ldarg.2
0x1b033  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class CacheChangeInfo> Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::CS$<>9__CachedAnonymousMethodDelegate3
0x1b038  brtrue.s loc_1B04B
0x1b03a  ldnull
0x1b03b  ldftn    class CacheChangeInfo Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::<GetCachedChanges>b__1(valuetype [mscorlib]System.Guid key)
0x1b041  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class CacheChangeInfo>::.ctor(object, native int)
0x1b046  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class CacheChangeInfo> Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::CS$<>9__CachedAnonymousMethodDelegate3
0x1b04b  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class CacheChangeInfo> Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::CS$<>9__CachedAnonymousMethodDelegate3
0x1b050  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class CacheChangeInfo>::GetOrAdd(void, var<u1>)
0x1b055  stfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b05a  ldc.i4.0
0x1b05b  stloc.3
0x1b05c  ldloc.s  5
0x1b05e  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b063  ldfld    object CacheChangeInfo::Sync
0x1b068  dup
0x1b069  stloc.s  6
0x1b06b  ldloca.s 3
0x1b06d  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1b072  ldloc.0
0x1b073  ldloc.s  5
0x1b075  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b07a  ldflda   valuetype [mscorlib]System.DateTime CacheChangeInfo::LatestAccessTime
0x1b07f  ldc.r8   5.0
0x1b088  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x1b08d  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1b092  stloc.1
0x1b093  ldloc.1
0x1b094  brfalse  loc_1B13F
0x1b099  ldc.i4   0x686762
0x1b09e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1b0a3  ldc.i4.s 0xF
0x1b0a5  ldstr    aTaxonomyDataba// "Taxonomy database change cache miss - e"...
0x1b0aa  ldc.i4.2
0x1b0ab  newarr   [mscorlib]System.Object
0x1b0b0  stloc.s  7
0x1b0b2  ldloc.s  7
0x1b0b4  ldc.i4.0
0x1b0b5  ldloc.s  5
0x1b0b7  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b0bc  ldfld    valuetype [mscorlib]System.Guid CacheChangeInfo::ContentDatabaseId
0x1b0c1  stloc.s  8
0x1b0c3  ldloca.s 8
0x1b0c5  constrained. [mscorlib]System.Guid
0x1b0cb  callvirt instance string [mscorlib]System.Object::ToString()
0x1b0d0  stelem.ref
0x1b0d1  ldloc.s  7
0x1b0d3  ldc.i4.1
0x1b0d4  ldarga.s 1
0x1b0d6  constrained. [mscorlib]System.DateTime
0x1b0dc  callvirt instance string [mscorlib]System.Object::ToString()
0x1b0e1  stelem.ref
0x1b0e2  ldloc.s  7
0x1b0e4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1b0e9  ldarg.0
0x1b0ea  ldarg.1
0x1b0eb  ldloc.s  5
0x1b0ed  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b0f2  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::RefreshCachedChanges(valuetype [mscorlib]System.DateTime sinceTime, class CacheChangeInfo cacheChangeInfo)
0x1b0f7  ldloc.s  5
0x1b0f9  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b0fe  ldloc.0
0x1b0ff  stfld    valuetype [mscorlib]System.DateTime CacheChangeInfo::LatestAccessTime
0x1b104  ldarg.0
0x1b105  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class CacheChangeInfo> Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseChangeCache::contentDatabaseChangeInfoCache
0x1b10a  ldarg.2
0x1b10b  ldloc.s  5
0x1b10d  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b112  ldloc.s  4
0x1b114  brtrue.s loc_1B125
0x1b116  ldloc.s  5
0x1b118  ldftn    instance class CacheChangeInfo <>c__DisplayClass5::<GetCachedChanges>b__2(valuetype [mscorlib]System.Guid key, class CacheChangeInfo value)
0x1b11e  newobj   instance void class [mscorlib]System.Func`3<valuetype [mscorlib]System.Guid, class CacheChangeInfo, class CacheChangeInfo>::.ctor(object, native int)
0x1b123  stloc.s  4
0x1b125  ldloc.s  4
0x1b127  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class CacheChangeInfo>::AddOrUpdate(void, var<u1>, !!T0)
0x1b12c  pop
0x1b12d  ldloc.s  5
0x1b12f  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b134  ldfld    string CacheChangeInfo::LatestChangesString
0x1b139  stloc.2
0x1b13a  br       loc_1B202
0x1b13f  ldarg.1
0x1b140  ldloc.s  5
0x1b142  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b147  ldfld    valuetype [mscorlib]System.DateTime CacheChangeInfo::LastSinceTime
0x1b14c  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1b151  brfalse.s loc_1B1B2
0x1b153  ldc.i4   0x686763
0x1b158  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1b15d  ldc.i4.s 0xF
0x1b15f  ldstr    aTaxonomyDataba_0// "Taxonomy database change cache hit. Con"...
0x1b164  ldc.i4.2
0x1b165  newarr   [mscorlib]System.Object
0x1b16a  stloc.s  9
0x1b16c  ldloc.s  9
0x1b16e  ldc.i4.0
0x1b16f  ldloc.s  5
0x1b171  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b176  ldfld    valuetype [mscorlib]System.Guid CacheChangeInfo::ContentDatabaseId
0x1b17b  stloc.s  0xA
0x1b17d  ldloca.s 0xA
0x1b17f  constrained. [mscorlib]System.Guid
0x1b185  callvirt instance string [mscorlib]System.Object::ToString()
0x1b18a  stelem.ref
0x1b18b  ldloc.s  9
0x1b18d  ldc.i4.1
0x1b18e  ldarga.s 1
0x1b190  constrained. [mscorlib]System.DateTime
0x1b196  callvirt instance string [mscorlib]System.Object::ToString()
0x1b19b  stelem.ref
0x1b19c  ldloc.s  9
0x1b19e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1b1a3  ldloc.s  5
0x1b1a5  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b1aa  ldfld    string CacheChangeInfo::LatestChangesString
0x1b1af  stloc.2
0x1b1b0  br.s     loc_1B202
0x1b1b2  ldc.i4   0x686780
0x1b1b7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1b1bc  ldc.i4.s 0xF
0x1b1be  ldstr    aTaxonomyDataba_1// "Taxonomy database change cache miss - d"...
0x1b1c3  ldc.i4.2
0x1b1c4  newarr   [mscorlib]System.Object
0x1b1c9  stloc.s  0xB
0x1b1cb  ldloc.s  0xB
0x1b1cd  ldc.i4.0
0x1b1ce  ldloc.s  5
0x1b1d0  ldfld    class CacheChangeInfo <>c__DisplayClass5::cacheChangeInfo
0x1b1d5  ldfld    valuetype [mscorlib]System.Guid CacheChangeInfo::ContentDatabaseId
0x1b1da  stloc.s  0xC
0x1b1dc  ldloca.s 0xC
0x1b1de  constrained. [mscorlib]System.Guid
0x1b1e4  callvirt instance string [mscorlib]System.Object::ToString()
0x1b1e9  stelem.ref
0x1b1ea  ldloc.s  0xB
0x1b1ec  ldc.i4.1
0x1b1ed  ldarga.s 1
0x1b1ef  constrained. [mscorlib]System.DateTime
0x1b1f5  callvirt instance string [mscorlib]System.Object::ToString()
0x1b1fa  stelem.ref
0x1b1fb  ldloc.s  0xB
0x1b1fd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1b202  leave.s  loc_1B20F
0x1b204  ldloc.3
0x1b205  brfalse.s loc_1B20E
0x1b207  ldloc.s  6
0x1b209  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1b20e  endfinally
0x1b20f  ldloc.2
0x1b210  ret
```
