# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::BatchUpdateKeywordItems

- ea: `0x48160`
- end: `0x482ca`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::BatchUpdateKeywordItems`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x482f0`
- `0x484e0`

## callees

- `0x43110`
- `0x48160`
- `0x487f0`
- `0x48810`
- `0x54bf0`

## string_xrefs

- `0x4816c`: `UpdateHiddenList job - BatchUpdateKeywordItems starting.  Size = {0}`
- `0x481e1`: `UpdateHiddenList job - BatchUpdateKeywordItems starting. Couldn't find {0}`
- `0x4825b`: `UpdateHiddenList job - BatchUpdateKeywordItems starting. Updating {0} with value `
- `0x48299`: `UpdateHiddenList job - BatchUpdateKeywordItems - ArgumentOutOfRange exception.  Expected if the item has been deleted.`
- `0x482bf`: `UpdateHiddenList job - BatchUpdateKeywordItems finished`

## pseudocode

```c

```

## disassembly

```asm
0x48160  ldc.i4   0x656E3036
0x48165  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4816a  ldc.i4.s 0x32
0x4816c  ldstr    aUpdatehiddenli_11// "UpdateHiddenList job - BatchUpdateKeywo"...
0x48171  ldc.i4.1
0x48172  newarr   [mscorlib]System.Object
0x48177  stloc.s  7
0x48179  ldloc.s  7
0x4817b  ldc.i4.0
0x4817c  ldarg.2
0x4817d  box      [mscorlib]System.Int32
0x48182  stelem.ref
0x48183  ldloc.s  7
0x48185  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4818a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::.ctor()
0x4818f  stloc.0
0x48190  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x48195  stloc.1
0x48196  ldc.i4.0
0x48197  stloc.2
0x48198  br.s     loc_4820E
0x4819a  ldloc.0
0x4819b  ldarg.1
0x4819c  ldloc.2
0x4819d  ldelema  [mscorlib]System.Guid
0x481a2  ldobj    [mscorlib]System.Guid
0x481a7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::ContainsKey(var<u1>)
0x481ac  brtrue.s loc_481D5
0x481ae  ldloc.0
0x481af  ldarg.1
0x481b0  ldloc.2
0x481b1  ldelema  [mscorlib]System.Guid
0x481b6  ldobj    [mscorlib]System.Guid
0x481bb  ldc.i4.1
0x481bc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::Add(var<u1>, !!T0)
0x481c1  ldloc.1
0x481c2  ldarg.1
0x481c3  ldloc.2
0x481c4  ldelema  [mscorlib]System.Guid
0x481c9  ldobj    [mscorlib]System.Guid
0x481ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x481d3  br.s     loc_4820A
0x481d5  ldc.i4   0x67326F71
0x481da  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x481df  ldc.i4.s 0x64
0x481e1  ldstr    aUpdatehiddenli_12// "UpdateHiddenList job - BatchUpdateKeywo"...
0x481e6  ldc.i4.1
0x481e7  newarr   [mscorlib]System.Object
0x481ec  stloc.s  8
0x481ee  ldloc.s  8
0x481f0  ldc.i4.0
0x481f1  ldarg.1
0x481f2  ldloc.2
0x481f3  ldelema  [mscorlib]System.Guid
0x481f8  ldobj    [mscorlib]System.Guid
0x481fd  box      [mscorlib]System.Guid
0x48202  stelem.ref
0x48203  ldloc.s  8
0x48205  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4820a  ldloc.2
0x4820b  ldc.i4.1
0x4820c  add.ovf
0x4820d  stloc.2
0x4820e  ldloc.2
0x4820f  ldarg.2
0x48210  blt.s    loc_4819A
0x48212  ldarg.3
0x48213  ldloc.1
0x48214  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x48219  ldc.i4.1
0x4821a  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.TermStore::GetTerms(valuetype [mscorlib]System.Guid[] termIds, bool getAllSiteCollectionTermSets)
0x4821f  stloc.3
0x48220  ldc.i4.0
0x48221  stloc.s  4
0x48223  br       loc_482AB
0x48228  ldloc.3
0x48229  ldarg.1
0x4822a  ldloc.s  4
0x4822c  ldelema  [mscorlib]System.Guid
0x48231  ldobj    [mscorlib]System.Guid
0x48236  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.IndexedCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x4823b  stloc.s  5
0x4823d  ldarg.0
0x4823e  ldloc.s  4
0x48240  ldelem.ref
0x48241  stloc.s  6
0x48243  ldloc.s  6
0x48245  ldloc.s  5
0x48247  ldc.i4.1
0x48248  ldarg.s  4
0x4824a  call     void Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateHiddenListItem(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem item, class Microsoft.SharePoint.Taxonomy.Term term, bool isKeywordField, class [mscorlib]System.Collections.Generic.List`1<int32>& listItemIdsForCatalogPush)
0x4824f  ldc.i4   0x67326F72
0x48254  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48259  ldc.i4.s 0x64
0x4825b  ldstr    aUpdatehiddenli_13// "UpdateHiddenList job - BatchUpdateKeywo"...
0x48260  ldc.i4.2
0x48261  newarr   [mscorlib]System.Object
0x48266  stloc.s  9
0x48268  ldloc.s  9
0x4826a  ldc.i4.0
0x4826b  ldloc.s  5
0x4826d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x48272  box      [mscorlib]System.Guid
0x48277  stelem.ref
0x48278  ldloc.s  9
0x4827a  ldc.i4.1
0x4827b  ldloc.s  5
0x4827d  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x48282  stelem.ref
0x48283  ldloc.s  9
0x48285  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4828a  leave.s  loc_482A5
0x4828c  pop
0x4828d  ldc.i4   0x656E3037
0x48292  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48297  ldc.i4.s 0x32
0x48299  ldstr    aUpdatehiddenli_14// "UpdateHiddenList job - BatchUpdateKeywo"...
0x4829e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x482a3  leave.s  loc_482A5
0x482a5  ldloc.s  4
0x482a7  ldc.i4.1
0x482a8  add.ovf
0x482a9  stloc.s  4
0x482ab  ldloc.s  4
0x482ad  ldarg.2
0x482ae  blt      loc_48228
0x482b3  ldc.i4   0x656E3038
0x482b8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x482bd  ldc.i4.s 0x32
0x482bf  ldstr    aUpdatehiddenli_15// "UpdateHiddenList job - BatchUpdateKeywo"...
0x482c4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x482c9  ret
```
