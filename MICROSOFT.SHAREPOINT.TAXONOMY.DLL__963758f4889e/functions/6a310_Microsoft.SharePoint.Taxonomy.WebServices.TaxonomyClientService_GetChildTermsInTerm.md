# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetChildTermsInTerm

- ea: `0x6a310`
- end: `0x6a4a1`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetChildTermsInTerm`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2ebf0`
- `0x422a0`
- `0x48810`
- `0x48ac0`
- `0x4ba10`
- `0x4cc10`
- `0x4d6c0`
- `0x4db80`
- `0x4ee90`
- `0x4f560`
- `0x50680`
- `0x54710`
- `0x55440`
- `0x55560`
- `0x55610`
- `0x557e0`
- `0x6a310`
- `0x6a4b0`
- `0x6de50`

## string_xrefs

- `0x6a31c`: `TaxonomyClientService: GetChildTermsInTerm started`
- `0x6a493`: `TaxonomyClientService: GetChildTermsInTerm finished`

## pseudocode

```c

```

## disassembly

```asm
0x6a310  ldc.i4   0x10E658
0x6a315  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6a31a  ldc.i4.s 0x64
0x6a31c  ldstr    aTaxonomyclient_14// "TaxonomyClientService: GetChildTermsInT"...
0x6a321  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6a326  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6a32b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6a330  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6a335  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6a33a  ldc.i4.1
0x6a33b  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6a340  stloc.0
0x6a341  ldloc.0
0x6a342  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6a347  stloc.1
0x6a348  ldloc.1
0x6a349  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x6a34e  ldarg.1
0x6a34f  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.IndexedCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Item(!!T0)
0x6a354  stloc.2
0x6a355  ldloc.2
0x6a356  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.SharePoint.Taxonomy.TermStore::get_Languages()
0x6a35b  ldarg.2
0x6a35c  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Contains(var<u1>)
0x6a361  brtrue.s loc_6A36B
0x6a363  ldloc.2
0x6a364  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x6a369  starg.s  2
0x6a36b  ldloc.2
0x6a36c  ldarg.2
0x6a36d  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6a372  ldloc.2
0x6a373  ldarg.s  4
0x6a375  ldarg.3
0x6a376  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6a37b  stloc.3
0x6a37c  ldloc.3
0x6a37d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6a382  ldc.i4   0x7FFFFFFF
0x6a387  ldc.i4.1
0x6a388  ldc.i4.1
0x6a389  ldloca.s 4
0x6a38b  ldloca.s 5
0x6a38d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.TermSetItem::GetTerms(valuetype [mscorlib]System.Guid currentNodeId, int32 pagingLimit, bool includingCurrentNode, bool pagingforward, [out] bool& hasMoreItemsBefore, [out] bool& hasMoreItemsAfter)
0x6a392  stloc.s  6
0x6a394  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::.ctor()
0x6a399  stloc.s  7
0x6a39b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::.ctor()
0x6a3a0  stloc.s  8
0x6a3a2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6a3a7  stloc.s  9
0x6a3a9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6a3ae  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6a3b3  ldloc.2
0x6a3b4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0x6a3b9  ldarg.s  4
0x6a3bb  ldarg.3
0x6a3bc  ldc.i4.1
0x6a3bd  ldc.i4.1
0x6a3be  call     int32[] Microsoft.SharePoint.Taxonomy.TaxonomyField::GetWssIdsOfTerm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid termStoreId, valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId, bool includeDescendants, int32 limit)
0x6a3c3  pop
0x6a3c4  ldloc.s  6
0x6a3c6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x6a3cb  stloc.s  0xD
0x6a3cd  br.s     loc_6A444
0x6a3cf  ldloc.s  0xD
0x6a3d1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x6a3d6  stloc.s  0xA
0x6a3d8  ldloc.s  0xA
0x6a3da  brfalse.s loc_6A444
0x6a3dc  ldloc.s  0xA
0x6a3de  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsDeprecated()
0x6a3e3  brtrue.s loc_6A444
0x6a3e5  ldloc.s  7
0x6a3e7  ldloc.s  0xA
0x6a3e9  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x6a3ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::Add(var<u1>)
0x6a3f3  ldloc.s  8
0x6a3f5  ldloc.2
0x6a3f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::Add(var<u1>)
0x6a3fb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6a400  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6a405  ldloc.s  0xA
0x6a407  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6a40c  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x6a411  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0x6a416  ldloc.s  0xA
0x6a418  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6a41d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6a422  ldloc.s  0xA
0x6a424  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6a429  ldc.i4.0
0x6a42a  ldc.i4   0x1F4
0x6a42f  call     int32[] Microsoft.SharePoint.Taxonomy.TaxonomyField::GetWssIdsOfTerm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid termStoreId, valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId, bool includeDescendants, int32 limit)
0x6a434  stloc.s  0xB
0x6a436  ldloc.s  9
0x6a438  ldloc.s  0xB
0x6a43a  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::WssIdArrayToString(int32[] ids)
0x6a43f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6a444  ldloc.s  0xD
0x6a446  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a44b  brtrue.s loc_6A3CF
0x6a44d  leave.s  loc_6A45B
0x6a44f  ldloc.s  0xD
0x6a451  brfalse.s loc_6A45A
0x6a453  ldloc.s  0xD
0x6a455  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a45a  endfinally
0x6a45b  ldloc.s  8
0x6a45d  ldloc.s  7
0x6a45f  ldarg.2
0x6a460  ldloc.3
0x6a461  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6a466  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x6a46b  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x6a470  ldnull
0x6a471  ldnull
0x6a472  ldloc.s  9
0x6a474  call     T0x2B0000AD
0x6a479  stloc.s  0xC
0x6a47b  leave.s  loc_6A49E
0x6a47d  ldloc.0
0x6a47e  brfalse.s loc_6A486
0x6a480  ldloc.0
0x6a481  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a486  endfinally
0x6a487  ldc.i4   0x10E659
0x6a48c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6a491  ldc.i4.s 0x64
0x6a493  ldstr    aTaxonomyclient_15// "TaxonomyClientService: GetChildTermsInT"...
0x6a498  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6a49d  endfinally
0x6a49e  ldloc.s  0xC
0x6a4a0  ret
```
