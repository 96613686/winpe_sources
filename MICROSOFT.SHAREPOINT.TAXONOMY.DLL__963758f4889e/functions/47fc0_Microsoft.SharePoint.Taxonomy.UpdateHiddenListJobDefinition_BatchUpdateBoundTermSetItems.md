# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::BatchUpdateBoundTermSetItems

- ea: `0x47fc0`
- end: `0x4815e`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::BatchUpdateBoundTermSetItems`
- size: `414`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x482f0`
- `0x484e0`

## callees

- `0x43110`
- `0x47fc0`
- `0x48810`
- `0x4f560`
- `0x56750`

## string_xrefs

- `0x47fcc`: `UpdateHiddenList job - BatchUpdateBoundTermSetItems starting.  size = {0}`
- `0x4809f`: `UpdateHiddenList job - BatchUpdateBoundTermSetItems trying to update item TSID {0}, TID {1}`
- `0x480f4`: `UpdateHiddenList job - BatchUpdateBoundTermSetItems trying couldn't find item TSID {0}, TID {1}`
- `0x4812d`: `UpdateHiddenList job - BatchUpdateBoundTermSetItems - ArgumentOutOfRange exception.  Expected if the item has been deleted.`
- `0x48153`: `UpdateHiddenList job - BatchUpdateBoundTermSetItems finishing`

## pseudocode

```c

```

## disassembly

```asm
0x47fc0  ldc.i4   0x656E3033
0x47fc5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47fca  ldc.i4.s 0x32
0x47fcc  ldstr    aUpdatehiddenli_6// "UpdateHiddenList job - BatchUpdateBound"...
0x47fd1  ldc.i4.1
0x47fd2  newarr   [mscorlib]System.Object
0x47fd7  stloc.s  0xA
0x47fd9  ldloc.s  0xA
0x47fdb  ldc.i4.0
0x47fdc  ldarg.2
0x47fdd  box      [mscorlib]System.Int32
0x47fe2  stelem.ref
0x47fe3  ldloc.s  0xA
0x47fe5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47fea  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::.ctor()
0x47fef  stloc.0
0x47ff0  ldarg.3
0x47ff1  ldarg.1
0x47ff2  ldc.i4.1
0x47ff3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermCollection> Microsoft.SharePoint.Taxonomy.TermStore::GetTerms(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> idList, bool getAllSiteCollectionTermSets)
0x47ff8  stloc.1
0x47ff9  ldc.i4.0
0x47ffa  stloc.2
0x47ffb  br.s     loc_48040
0x47ffd  ldloc.1
0x47ffe  ldloc.2
0x47fff  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermCollection>::get_Item(!!T0)
0x48004  stloc.3
0x48005  ldloc.3
0x48006  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x4800b  brfalse.s loc_4803C
0x4800d  ldloc.3
0x4800e  ldc.i4.0
0x4800f  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x48014  brfalse.s loc_4803C
0x48016  ldloc.3
0x48017  ldc.i4.0
0x48018  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x4801d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x48022  brfalse.s loc_4803C
0x48024  ldloc.0
0x48025  ldloc.3
0x48026  ldc.i4.0
0x48027  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x4802c  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x48031  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x48036  ldloc.2
0x48037  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::set_Item(var<u1>, !!T0)
0x4803c  ldloc.2
0x4803d  ldc.i4.1
0x4803e  add.ovf
0x4803f  stloc.2
0x48040  ldloc.2
0x48041  ldloc.1
0x48042  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermCollection>::get_Count()
0x48047  blt.s    loc_47FFD
0x48049  ldc.i4.0
0x4804a  stloc.s  4
0x4804c  br       loc_4813F
0x48051  ldarg.0
0x48052  ldloc.s  4
0x48054  ldelem.ref
0x48055  stloc.s  5
0x48057  ldloca.s 6
0x48059  ldloc.s  5
0x4805b  ldstr    aIdforterm// "IdForTerm"
0x48060  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItem::get_Item(string)
0x48065  castclass [mscorlib]System.String
0x4806a  call     instance void [mscorlib]System.Guid::.ctor(string)
0x4806f  ldloca.s 7
0x48071  ldloc.s  5
0x48073  ldstr    aIdfortermset// "IdForTermSet"
0x48078  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItem::get_Item(string)
0x4807d  castclass [mscorlib]System.String
0x48082  call     instance void [mscorlib]System.Guid::.ctor(string)
0x48087  ldloc.0
0x48088  ldloc.s  7
0x4808a  ldloca.s 8
0x4808c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::TryGetValue(var<u1>, !!T0)
0x48091  brfalse.s loc_480E8
0x48093  ldc.i4   0x67326F6F
0x48098  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4809d  ldc.i4.s 0x64
0x4809f  ldstr    aUpdatehiddenli_7// "UpdateHiddenList job - BatchUpdateBound"...
0x480a4  ldc.i4.2
0x480a5  newarr   [mscorlib]System.Object
0x480aa  stloc.s  0xB
0x480ac  ldloc.s  0xB
0x480ae  ldc.i4.0
0x480af  ldloc.s  7
0x480b1  box      [mscorlib]System.Guid
0x480b6  stelem.ref
0x480b7  ldloc.s  0xB
0x480b9  ldc.i4.1
0x480ba  ldloc.s  6
0x480bc  box      [mscorlib]System.Guid
0x480c1  stelem.ref
0x480c2  ldloc.s  0xB
0x480c4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x480c9  ldloc.1
0x480ca  ldloc.s  8
0x480cc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermCollection>::get_Item(!!T0)
0x480d1  ldloc.s  6
0x480d3  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.IndexedCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x480d8  stloc.s  9
0x480da  ldloc.s  5
0x480dc  ldloc.s  9
0x480de  ldc.i4.0
0x480df  ldarg.s  4
0x480e1  call     void Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateHiddenListItem(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem item, class Microsoft.SharePoint.Taxonomy.Term term, bool isKeywordField, class [mscorlib]System.Collections.Generic.List`1<int32>& listItemIdsForCatalogPush)
0x480e6  br.s     loc_4811E
0x480e8  ldc.i4   0x67326F70
0x480ed  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x480f2  ldc.i4.s 0x64
0x480f4  ldstr    aUpdatehiddenli_8// "UpdateHiddenList job - BatchUpdateBound"...
0x480f9  ldc.i4.2
0x480fa  newarr   [mscorlib]System.Object
0x480ff  stloc.s  0xC
0x48101  ldloc.s  0xC
0x48103  ldc.i4.0
0x48104  ldloc.s  7
0x48106  box      [mscorlib]System.Guid
0x4810b  stelem.ref
0x4810c  ldloc.s  0xC
0x4810e  ldc.i4.1
0x4810f  ldloc.s  6
0x48111  box      [mscorlib]System.Guid
0x48116  stelem.ref
0x48117  ldloc.s  0xC
0x48119  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4811e  leave.s  loc_48139
0x48120  pop
0x48121  ldc.i4   0x656E3034
0x48126  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4812b  ldc.i4.s 0x32
0x4812d  ldstr    aUpdatehiddenli_9// "UpdateHiddenList job - BatchUpdateBound"...
0x48132  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x48137  leave.s  loc_48139
0x48139  ldloc.s  4
0x4813b  ldc.i4.1
0x4813c  add.ovf
0x4813d  stloc.s  4
0x4813f  ldloc.s  4
0x48141  ldarg.2
0x48142  blt      loc_48051
0x48147  ldc.i4   0x656E3035
0x4814c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48151  ldc.i4.s 0x32
0x48153  ldstr    aUpdatehiddenli_10// "UpdateHiddenList job - BatchUpdateBound"...
0x48158  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4815d  ret
```
