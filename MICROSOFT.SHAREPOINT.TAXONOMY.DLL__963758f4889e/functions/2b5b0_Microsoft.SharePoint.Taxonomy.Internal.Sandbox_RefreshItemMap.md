# Microsoft.SharePoint.Taxonomy.Internal.Sandbox::RefreshItemMap

- ea: `0x2b5b0`
- end: `0x2b85e`
- name: `Microsoft.SharePoint.Taxonomy.Internal.Sandbox::RefreshItemMap`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x2b3c0`

## callees

- `0x29510`
- `0x29530`
- `0x29550`
- `0x29570`
- `0x29680`
- `0x2b5b0`
- `0x2ebd0`
- `0x2ecb0`
- `0x2f380`
- `0x2f620`
- `0x2f680`
- `0x2fc20`
- `0x32130`
- `0x48a20`
- `0x50610`
- `0x56bd0`
- `0x56c10`

## string_xrefs

- `0x2b5bc`: `Refreshing wrapped shared items for items in sandbox that have been committed`
- `0x2b853`: `Refreshed wrapped shared items for items in sandbox that have been committed`

## pseudocode

```c

```

## disassembly

```asm
0x2b5b0  ldc.i4   0x32657473
0x2b5b5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b5ba  ldc.i4.s 0x64
0x2b5bc  ldstr    aRefreshingWrap// "Refreshing wrapped shared items for ite"...
0x2b5c1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b5c6  ldarg.1
0x2b5c7  ldsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem, bool> Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CS$<>9__CachedAnonymousMethodDelegate2
0x2b5cc  brtrue.s loc_2B5DF
0x2b5ce  ldnull
0x2b5cf  ldftn    bool Microsoft.SharePoint.Taxonomy.Internal.Sandbox::<RefreshItemMap>b__0(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem x)
0x2b5d5  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem, bool>::.ctor(object, native int)
0x2b5da  stsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem, bool> Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CS$<>9__CachedAnonymousMethodDelegate2
0x2b5df  ldsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem, bool> Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CS$<>9__CachedAnonymousMethodDelegate2
0x2b5e4  call     T0x2B00003B
0x2b5e9  ldsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CS$<>9__CachedAnonymousMethodDelegate3
0x2b5ee  brtrue.s loc_2B601
0x2b5f0  ldnull
0x2b5f1  ldftn    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.Sandbox::<RefreshItemMap>b__1(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem x)
0x2b5f7  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x2b5fc  stsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CS$<>9__CachedAnonymousMethodDelegate3
0x2b601  ldsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CS$<>9__CachedAnonymousMethodDelegate3
0x2b606  call     T0x2B00003C
0x2b60b  call     T0x2B000016
0x2b610  stloc.0
0x2b611  ldarg.1
0x2b612  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem>::get_Count()
0x2b617  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::.ctor(int32)
0x2b61c  stloc.1
0x2b61d  ldloc.0
0x2b61e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2b623  ldc.i4.0
0x2b624  ble.s    loc_2B673
0x2b626  ldarg.0
0x2b627  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b62c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x2b631  ldloc.0
0x2b632  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm> Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetTerms(class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid> termGuids)
0x2b637  stloc.2
0x2b638  ldloc.2
0x2b639  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::GetEnumerator()
0x2b63e  stloc.s  0xE
0x2b640  br.s     loc_2B65A
0x2b642  ldloca.s 0xE
0x2b644  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::get_Current()
0x2b649  stloc.3
0x2b64a  ldloc.3
0x2b64b  brfalse.s loc_2B65A
0x2b64d  ldloc.1
0x2b64e  ldloc.3
0x2b64f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_UniqueId()
0x2b654  ldloc.3
0x2b655  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::set_Item(var<u1>, !!T0)
0x2b65a  ldloca.s 0xE
0x2b65c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::MoveNext()
0x2b661  brtrue.s loc_2B642
0x2b663  leave.s  loc_2B673
0x2b665  ldloca.s 0xE
0x2b667  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>
0x2b66d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b672  endfinally
0x2b673  ldarg.1
0x2b674  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem>::GetEnumerator()
0x2b679  stloc.s  0xF
0x2b67b  br       loc_2B82B
0x2b680  ldloca.s 0xF
0x2b682  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem>::get_Current()
0x2b687  stloc.s  4
0x2b689  ldloc.s  4
0x2b68b  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_ItemType()
0x2b690  stloc.s  0x10
0x2b692  ldloc.s  0x10
0x2b694  switch   loc_2B6AA, loc_2B77F, loc_2B7D6
0x2b6a5  br       loc_2B82B
0x2b6aa  ldnull
0x2b6ab  stloc.s  5
0x2b6ad  ldloc.1
0x2b6ae  ldloc.s  4
0x2b6b0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_UniqueId()
0x2b6b5  ldloca.s 5
0x2b6b7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::TryGetValue(var<u1>, !!T0)
0x2b6bc  pop
0x2b6bd  ldloc.s  5
0x2b6bf  brfalse  loc_2B768
0x2b6c4  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2b6c9  stloc.s  6
0x2b6cb  ldloc.s  5
0x2b6cd  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership> Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::get_Memberships()
0x2b6d2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership>::get_Keys()
0x2b6d7  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership>::GetEnumerator()
0x2b6dc  stloc.s  0x11
0x2b6de  br.s     loc_2B736
0x2b6e0  ldloca.s 0x11
0x2b6e2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership>::get_Current()
0x2b6e7  stloc.s  7
0x2b6e9  ldarg.0
0x2b6ea  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b6ef  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x2b6f4  ldloc.s  7
0x2b6f6  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetTermSet(int32 termSetId)
0x2b6fb  stloc.s  8
0x2b6fd  ldarg.0
0x2b6fe  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b703  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap Microsoft.SharePoint.Taxonomy.TermStore::get_ItemMap()
0x2b708  ldloc.s  5
0x2b70a  ldloc.s  8
0x2b70c  ldloca.s 9
0x2b70e  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap::TryGetTerm(class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm sharedTerm, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet sharedTermSet, [out] class Microsoft.SharePoint.Taxonomy.Term& term)
0x2b713  brfalse.s loc_2B736
0x2b715  ldloc.s  6
0x2b717  ldloc.s  8
0x2b719  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_UniqueId()
0x2b71e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x2b723  pop
0x2b724  ldloc.s  9
0x2b726  ldloc.s  5
0x2b728  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::ReplaceSharedItem(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem item)
0x2b72d  ldloc.s  9
0x2b72f  ldloc.s  8
0x2b731  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::ReplaceSharedTermSet(class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet termSet)
0x2b736  ldloca.s 0x11
0x2b738  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership>::MoveNext()
0x2b73d  brtrue.s loc_2B6E0
0x2b73f  leave.s  loc_2B74F
0x2b741  ldloca.s 0x11
0x2b743  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership>
0x2b749  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b74e  endfinally
0x2b74f  ldarg.0
0x2b750  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b755  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap Microsoft.SharePoint.Taxonomy.TermStore::get_ItemMap()
0x2b75a  ldloc.s  5
0x2b75c  ldloc.s  6
0x2b75e  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap::InvalidateExtraTermMemberships(class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm sharedTerm, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> validMembershipTermSetIds)
0x2b763  br       loc_2B82B
0x2b768  ldarg.0
0x2b769  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b76e  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap Microsoft.SharePoint.Taxonomy.TermStore::get_ItemMap()
0x2b773  ldloc.s  4
0x2b775  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap::InvalidateItem(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem item)
0x2b77a  br       loc_2B82B
0x2b77f  ldarg.0
0x2b780  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b785  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x2b78a  ldloc.s  4
0x2b78c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_UniqueId()
0x2b791  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetTermSet(valuetype [mscorlib]System.Guid termSetGuid)
0x2b796  stloc.s  0xA
0x2b798  ldarg.0
0x2b799  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b79e  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap Microsoft.SharePoint.Taxonomy.TermStore::get_ItemMap()
0x2b7a3  ldloc.s  4
0x2b7a5  castclass Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet
0x2b7aa  ldloca.s 0xB
0x2b7ac  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap::TryGetTermSet(class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet sharedTermSet, [out] class Microsoft.SharePoint.Taxonomy.TermSet& termSet)
0x2b7b1  brfalse.s loc_2B82B
0x2b7b3  ldloc.s  0xA
0x2b7b5  brfalse.s loc_2B7C2
0x2b7b7  ldloc.s  0xB
0x2b7b9  ldloc.s  0xA
0x2b7bb  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::ReplaceSharedItem(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem item)
0x2b7c0  br.s     loc_2B82B
0x2b7c2  ldarg.0
0x2b7c3  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b7c8  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap Microsoft.SharePoint.Taxonomy.TermStore::get_ItemMap()
0x2b7cd  ldloc.s  4
0x2b7cf  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap::InvalidateItem(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem item)
0x2b7d4  br.s     loc_2B82B
0x2b7d6  ldarg.0
0x2b7d7  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b7dc  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x2b7e1  ldloc.s  4
0x2b7e3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_UniqueId()
0x2b7e8  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetGroup(valuetype [mscorlib]System.Guid groupGuid)
0x2b7ed  stloc.s  0xC
0x2b7ef  ldarg.0
0x2b7f0  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b7f5  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap Microsoft.SharePoint.Taxonomy.TermStore::get_ItemMap()
0x2b7fa  ldloc.s  4
0x2b7fc  castclass Microsoft.SharePoint.Taxonomy.Internal.SharedGroup
0x2b801  ldloca.s 0xD
0x2b803  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap::TryGetGroup(class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup sharedGroup, [out] class Microsoft.SharePoint.Taxonomy.Group& group)
0x2b808  brfalse.s loc_2B82B
0x2b80a  ldloc.s  0xC
0x2b80c  brfalse.s loc_2B819
0x2b80e  ldloc.s  0xD
0x2b810  ldloc.s  0xC
0x2b812  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::ReplaceSharedItem(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem item)
0x2b817  br.s     loc_2B82B
0x2b819  ldarg.0
0x2b81a  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b81f  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap Microsoft.SharePoint.Taxonomy.TermStore::get_ItemMap()
0x2b824  ldloc.s  4
0x2b826  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyItemMap::InvalidateItem(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem item)
0x2b82b  ldloca.s 0xF
0x2b82d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem>::MoveNext()
0x2b832  brtrue   loc_2B680
0x2b837  leave.s  loc_2B847
0x2b839  ldloca.s 0xF
0x2b83b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedItem>
0x2b841  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b846  endfinally
0x2b847  ldc.i4   0x32657474
0x2b84c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b851  ldc.i4.s 0x64
0x2b853  ldstr    aRefreshedWrapp// "Refreshed wrapped shared items for item"...
0x2b858  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b85d  ret
```
