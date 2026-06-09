# Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::MaintainCacheByUsage

- ea: `0x1f000`
- end: `0x1f1f5`
- name: `Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::MaintainCacheByUsage`
- size: `501`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1ec60`
- `0x1f000`
- `0x20500`
- `0x20ae0`
- `0x20af0`
- `0x20b60`
- `0x214b0`

## string_xrefs

- `0x1f034`: `Maintaining cache size by usage`
- `0x1f064`: `Calculating which cache entries should be removed.`
- `0x1f10c`: `Removing cache entries.`
- `0x1f193`: `Cache maintenance is done.`
- `0x1f1b2`: `While attempting to trim cache, removed all selected items but the estimated size is still: {0}, desired final size: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x1f000  ldarg.0
0x1f001  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_CacheSize()
0x1f006  stloc.0
0x1f007  ldarg.0
0x1f008  ldfld    int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::maximumCacheSize
0x1f00d  ldc.i4.0
0x1f00e  ble      loc_1F1F4
0x1f013  ldloc.0
0x1f014  conv.r8
0x1f015  ldarg.0
0x1f016  ldfld    int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::maximumCacheSize
0x1f01b  conv.r8
0x1f01c  ldarg.0
0x1f01d  ldfld    float64 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::trimmingThreshold
0x1f022  mul
0x1f023  ble.un   loc_1F1F4
0x1f028  ldc.i4   0x31346730
0x1f02d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1f032  ldc.i4.s 0x32
0x1f034  ldstr    aMaintainingCac// "Maintaining cache size by usage"
0x1f039  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1f03e  ldarg.0
0x1f03f  ldfld    int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::maximumCacheSize
0x1f044  conv.r8
0x1f045  ldarg.0
0x1f046  ldfld    float64 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::cacheSizeReductionAmount
0x1f04b  mul
0x1f04c  conv.ovf.i2.un
0x1f04d  stloc.1
0x1f04e  ldloc.1
0x1f04f  ldc.i4.1
0x1f050  bge.s    loc_1F054
0x1f052  ldc.i4.1
0x1f053  stloc.1
0x1f054  ldloc.0
0x1f055  ldloc.1
0x1f056  sub.ovf
0x1f057  stloc.2
0x1f058  ldc.i4   0x31346737
0x1f05d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1f062  ldc.i4.s 0x32
0x1f064  ldstr    aCalculatingWhi// "Calculating which cache entries should "...
0x1f069  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1f06e  ldnull
0x1f06f  stloc.3
0x1f070  ldc.i4.0
0x1f071  stloc.s  4
0x1f073  ldarg.0
0x1f074  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.ICombinableCache> Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::combinableCaches
0x1f079  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.ICombinableCache>::get_Values()
0x1f07e  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<int32, class Microsoft.SharePoint.Taxonomy.Internal.ICombinableCache>::GetEnumerator()
0x1f083  stloc.s  0xB
0x1f085  br.s     loc_1F0E1
0x1f087  ldloca.s 0xB
0x1f089  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.SharePoint.Taxonomy.Internal.ICombinableCache>::get_Current()
0x1f08e  stloc.s  5
0x1f090  ldc.i4.0
0x1f091  stloc.s  6
0x1f093  ldloc.s  5
0x1f095  ldloc.2
0x1f096  ldarg.0
0x1f097  ldfld    float64 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::countSizeReductionAmount
0x1f09c  ldloca.s 6
0x1f09e  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.CountableEntry[] Microsoft.SharePoint.Taxonomy.Internal.ICombinableCache::RemoveIfAlone(int32 sizeToRemove, float64 countSizeReductionAmount, int32& entryCount)
0x1f0a3  stloc.s  7
0x1f0a5  ldloc.3
0x1f0a6  brtrue.s loc_1F0B2
0x1f0a8  ldloc.s  6
0x1f0aa  newarr   Microsoft.SharePoint.Taxonomy.Internal.CountableEntry
0x1f0af  stloc.3
0x1f0b0  br.s     loc_1F0BF
0x1f0b2  ldloca.s 3
0x1f0b4  ldloc.3
0x1f0b5  ldlen
0x1f0b6  conv.i4
0x1f0b7  ldloc.s  6
0x1f0b9  add.ovf
0x1f0ba  call     T0x2B000020
0x1f0bf  ldc.i4.0
0x1f0c0  stloc.s  8
0x1f0c2  br.s     loc_1F0D6
0x1f0c4  ldloc.3
0x1f0c5  ldloc.s  4
0x1f0c7  ldloc.s  8
0x1f0c9  add.ovf
0x1f0ca  ldloc.s  7
0x1f0cc  ldloc.s  8
0x1f0ce  ldelem.ref
0x1f0cf  stelem.ref
0x1f0d0  ldloc.s  8
0x1f0d2  ldc.i4.1
0x1f0d3  add.ovf
0x1f0d4  stloc.s  8
0x1f0d6  ldloc.s  8
0x1f0d8  ldloc.s  6
0x1f0da  blt.s    loc_1F0C4
0x1f0dc  ldloc.3
0x1f0dd  ldlen
0x1f0de  conv.i4
0x1f0df  stloc.s  4
0x1f0e1  ldloca.s 0xB
0x1f0e3  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.SharePoint.Taxonomy.Internal.ICombinableCache>::MoveNext()
0x1f0e8  brtrue.s loc_1F087
0x1f0ea  leave.s  loc_1F0FA
0x1f0ec  ldloca.s 0xB
0x1f0ee  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class Microsoft.SharePoint.Taxonomy.Internal.ICombinableCache>
0x1f0f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f0f9  endfinally
0x1f0fa  ldloc.3
0x1f0fb  call     T0x2B000021
0x1f100  ldc.i4   0x31346761
0x1f105  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1f10a  ldc.i4.s 0x32
0x1f10c  ldstr    aRemovingCacheE// "Removing cache entries."
0x1f111  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1f116  ldnull
0x1f117  stloc.s  9
0x1f119  ldloc.3
0x1f11a  stloc.s  0xC
0x1f11c  ldc.i4.0
0x1f11d  stloc.s  0xD
0x1f11f  br.s     loc_1F17F
0x1f121  ldloc.s  0xC
0x1f123  ldloc.s  0xD
0x1f125  ldelem.ref
0x1f126  stloc.s  0xA
0x1f128  ldarg.0
0x1f129  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_CacheSize()
0x1f12e  ldloc.1
0x1f12f  blt.s    loc_1F187
0x1f131  ldloc.s  0xA
0x1f133  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType Microsoft.SharePoint.Taxonomy.Internal.CountableEntry::get_Type()
0x1f138  stloc.s  0xE
0x1f13a  ldloc.s  0xE
0x1f13c  switch   loc_1F14F, loc_1F159, loc_1F163
0x1f14d  br.s     loc_1F16B
0x1f14f  ldarg.0
0x1f150  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.SharedItemCache`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm> Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::termCache
0x1f155  stloc.s  9
0x1f157  br.s     loc_1F16B
0x1f159  ldarg.0
0x1f15a  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.SharedItemCache`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet> Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::termSetCache
0x1f15f  stloc.s  9
0x1f161  br.s     loc_1F16B
0x1f163  ldarg.0
0x1f164  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.SharedItemCache`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup> Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::groupCache
0x1f169  stloc.s  9
0x1f16b  ldloc.s  9
0x1f16d  ldloc.s  0xA
0x1f16f  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey Microsoft.SharePoint.Taxonomy.Internal.CountableEntry::get_SharedItemInternalKey()
0x1f174  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedItemCache::RemoveKey(class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey internalKey)
0x1f179  ldloc.s  0xD
0x1f17b  ldc.i4.1
0x1f17c  add
0x1f17d  stloc.s  0xD
0x1f17f  ldloc.s  0xD
0x1f181  ldloc.s  0xC
0x1f183  ldlen
0x1f184  conv.i4
0x1f185  blt.s    loc_1F121
0x1f187  ldc.i4   0x31346762
0x1f18c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1f191  ldc.i4.s 0x32
0x1f193  ldstr    aCacheMaintenan// "Cache maintenance is done."
0x1f198  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1f19d  ldarg.0
0x1f19e  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_CacheSize()
0x1f1a3  ldloc.1
0x1f1a4  ble.s    loc_1F1F4
0x1f1a6  ldc.i4   0x747A6A78
0x1f1ab  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1f1b0  ldc.i4.s 0xA
0x1f1b2  ldstr    aWhileAttemptin// "While attempting to trim cache, removed"...
0x1f1b7  ldc.i4.2
0x1f1b8  newarr   [mscorlib]System.Object
0x1f1bd  stloc.s  0xF
0x1f1bf  ldloc.s  0xF
0x1f1c1  ldc.i4.0
0x1f1c2  ldarg.0
0x1f1c3  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_CacheSize()
0x1f1c8  stloc.s  0x10
0x1f1ca  ldloca.s 0x10
0x1f1cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f1d1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1f1d6  stelem.ref
0x1f1d7  ldloc.s  0xF
0x1f1d9  ldc.i4.1
0x1f1da  ldloca.s 1
0x1f1dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f1e1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1f1e6  stelem.ref
0x1f1e7  ldloc.s  0xF
0x1f1e9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1f1ee  ldarg.0
0x1f1ef  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::Flush()
0x1f1f4  ret
```
