# Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateCacheWhileLocked

- ea: `0x1fd00`
- end: `0x1fddd`
- name: `Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateCacheWhileLocked`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x20600`
- `0x20e00`

## callees

- `0x1fd00`
- `0x1fde0`
- `0x1feb0`
- `0x1ff50`
- `0x20130`
- `0x20170`
- `0x38f30`
- `0x38f50`

## string_xrefs

- `0x1fd0c`: `Invalidating cache`
- `0x1fdd1`: `End of invalidating cache`

## pseudocode

```c

```

## disassembly

```asm
0x1fd00  ldc.i4   0x31346770
0x1fd05  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1fd0a  ldc.i4.s 0x64
0x1fd0c  ldstr    aInvalidatingCa// "Invalidating cache"
0x1fd11  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1fd16  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x1fd1b  stloc.0
0x1fd1c  ldarg.1
0x1fd1d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem>::GetEnumerator()
0x1fd22  stloc.2
0x1fd23  br       loc_1FDA9
0x1fd28  ldloca.s 2
0x1fd2a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.ChangedItem>::get_Current()
0x1fd2f  stloc.1
0x1fd30  ldloc.1
0x1fd31  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.ChangedItemType Microsoft.SharePoint.Taxonomy.ChangedItem::get_ItemType()
0x1fd36  stloc.3
0x1fd37  ldloc.3
0x1fd38  ldc.i4.1
0x1fd39  sub
0x1fd3a  switch   loc_1FD55, loc_1FD63, loc_1FD71, loc_1FD7F, loc_1FD88
0x1fd53  br.s     loc_1FD94
0x1fd55  ldarg.0
0x1fd56  ldloc.1
0x1fd57  isinst   Microsoft.SharePoint.Taxonomy.ChangedTerm
0x1fd5c  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateTermWhileLocked(class Microsoft.SharePoint.Taxonomy.ChangedTerm changedTerm)
0x1fd61  br.s     loc_1FD94
0x1fd63  ldarg.0
0x1fd64  ldloc.1
0x1fd65  isinst   Microsoft.SharePoint.Taxonomy.ChangedTermSet
0x1fd6a  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateTermSetWhileLocked(class Microsoft.SharePoint.Taxonomy.ChangedTermSet changedTermSet)
0x1fd6f  br.s     loc_1FD94
0x1fd71  ldarg.0
0x1fd72  ldloc.1
0x1fd73  isinst   Microsoft.SharePoint.Taxonomy.ChangedGroup
0x1fd78  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateGroup(class Microsoft.SharePoint.Taxonomy.ChangedGroup changedGroup)
0x1fd7d  br.s     loc_1FD94
0x1fd7f  ldarg.0
0x1fd80  ldloc.1
0x1fd81  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateTermStore(class Microsoft.SharePoint.Taxonomy.ChangedItem item)
0x1fd86  br.s     loc_1FD94
0x1fd88  ldarg.0
0x1fd89  ldloc.1
0x1fd8a  isinst   Microsoft.SharePoint.Taxonomy.ChangedSite
0x1fd8f  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateSite(class Microsoft.SharePoint.Taxonomy.ChangedSite changedSite)
0x1fd94  ldloc.1
0x1fd95  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.ChangedItem::get_ChangedTime()
0x1fd9a  ldloc.0
0x1fd9b  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1fda0  brfalse.s loc_1FDA9
0x1fda2  ldloc.1
0x1fda3  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.ChangedItem::get_ChangedTime()
0x1fda8  stloc.0
0x1fda9  ldloca.s 2
0x1fdab  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.ChangedItem>::MoveNext()
0x1fdb0  brtrue   loc_1FD28
0x1fdb5  leave.s  loc_1FDC5
0x1fdb7  ldloca.s 2
0x1fdb9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.ChangedItem>
0x1fdbf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fdc4  endfinally
0x1fdc5  ldc.i4   0x31346772
0x1fdca  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1fdcf  ldc.i4.s 0x64
0x1fdd1  ldstr    aEndOfInvalidat// "End of invalidating cache"
0x1fdd6  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1fddb  ldloc.0
0x1fddc  ret
```
