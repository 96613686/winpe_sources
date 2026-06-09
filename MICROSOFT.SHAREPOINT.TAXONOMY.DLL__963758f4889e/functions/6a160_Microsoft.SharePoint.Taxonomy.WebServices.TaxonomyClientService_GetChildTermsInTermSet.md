# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetChildTermsInTermSet

- ea: `0x6a160`
- end: `0x6a306`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetChildTermsInTermSet`
- size: `422`
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
- `0x55050`
- `0x55440`
- `0x55560`
- `0x55610`
- `0x557e0`
- `0x6a160`
- `0x6a4b0`
- `0x6de50`

## string_xrefs

- `0x6a16c`: `TaxonomyClientService: GetChildTermsInTermSet started`
- `0x6a2f8`: `TaxonomyClientService: GetChildTermsInTermSet finished`

## pseudocode

```c

```

## disassembly

```asm
0x6a160  ldc.i4   0x10E656
0x6a165  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6a16a  ldc.i4.s 0x64
0x6a16c  ldstr    aTaxonomyclient_12// "TaxonomyClientService: GetChildTermsInT"...
0x6a171  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6a176  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6a17b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6a180  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6a185  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6a18a  ldc.i4.1
0x6a18b  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6a190  stloc.0
0x6a191  ldloc.0
0x6a192  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6a197  stloc.1
0x6a198  ldloc.1
0x6a199  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x6a19e  ldarg.1
0x6a19f  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.IndexedCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Item(!!T0)
0x6a1a4  stloc.2
0x6a1a5  ldloc.2
0x6a1a6  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.SharePoint.Taxonomy.TermStore::get_Languages()
0x6a1ab  ldarg.2
0x6a1ac  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Contains(var<u1>)
0x6a1b1  brtrue.s loc_6A1BB
0x6a1b3  ldloc.2
0x6a1b4  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x6a1b9  starg.s  2
0x6a1bb  ldloc.2
0x6a1bc  ldarg.2
0x6a1bd  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6a1c2  ldloc.2
0x6a1c3  ldarg.3
0x6a1c4  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6a1c9  stloc.3
0x6a1ca  ldloc.3
0x6a1cb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6a1d0  ldc.i4   0x7FFFFFFF
0x6a1d5  ldc.i4.1
0x6a1d6  ldc.i4.1
0x6a1d7  ldloca.s 4
0x6a1d9  ldloca.s 5
0x6a1db  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.TermSetItem::GetTerms(valuetype [mscorlib]System.Guid currentNodeId, int32 pagingLimit, bool includingCurrentNode, bool pagingforward, [out] bool& hasMoreItemsBefore, [out] bool& hasMoreItemsAfter)
0x6a1e0  stloc.s  6
0x6a1e2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::.ctor()
0x6a1e7  stloc.s  7
0x6a1e9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::.ctor()
0x6a1ee  stloc.s  8
0x6a1f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6a1f5  stloc.s  9
0x6a1f7  ldloc.s  6
0x6a1f9  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x6a1fe  ldc.i4.0
0x6a1ff  ble      loc_6A2C5
0x6a204  ldloc.s  6
0x6a206  ldc.i4.0
0x6a207  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Item(!!T0)
0x6a20c  stloc.s  0xA
0x6a20e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6a213  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6a218  ldloc.2
0x6a219  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0x6a21e  ldarg.3
0x6a21f  ldloc.s  0xA
0x6a221  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6a226  ldc.i4.1
0x6a227  ldc.i4.1
0x6a228  call     int32[] Microsoft.SharePoint.Taxonomy.TaxonomyField::GetWssIdsOfTerm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid termStoreId, valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId, bool includeDescendants, int32 limit)
0x6a22d  pop
0x6a22e  ldloc.s  6
0x6a230  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x6a235  stloc.s  0xE
0x6a237  br.s     loc_6A2AE
0x6a239  ldloc.s  0xE
0x6a23b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x6a240  stloc.s  0xB
0x6a242  ldloc.s  0xB
0x6a244  brfalse.s loc_6A2AE
0x6a246  ldloc.s  0xB
0x6a248  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsDeprecated()
0x6a24d  brtrue.s loc_6A2AE
0x6a24f  ldloc.s  7
0x6a251  ldloc.s  0xB
0x6a253  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x6a258  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::Add(var<u1>)
0x6a25d  ldloc.s  8
0x6a25f  ldloc.2
0x6a260  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::Add(var<u1>)
0x6a265  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6a26a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6a26f  ldloc.s  0xB
0x6a271  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6a276  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x6a27b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0x6a280  ldloc.s  0xB
0x6a282  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6a287  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6a28c  ldloc.s  0xB
0x6a28e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6a293  ldc.i4.0
0x6a294  ldc.i4   0x1F4
0x6a299  call     int32[] Microsoft.SharePoint.Taxonomy.TaxonomyField::GetWssIdsOfTerm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid termStoreId, valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId, bool includeDescendants, int32 limit)
0x6a29e  stloc.s  0xC
0x6a2a0  ldloc.s  9
0x6a2a2  ldloc.s  0xC
0x6a2a4  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::WssIdArrayToString(int32[] ids)
0x6a2a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6a2ae  ldloc.s  0xE
0x6a2b0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a2b5  brtrue.s loc_6A239
0x6a2b7  leave.s  loc_6A2C5
0x6a2b9  ldloc.s  0xE
0x6a2bb  brfalse.s loc_6A2C4
0x6a2bd  ldloc.s  0xE
0x6a2bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a2c4  endfinally
0x6a2c5  ldloc.s  8
0x6a2c7  ldloc.s  7
0x6a2c9  ldarg.2
0x6a2ca  ldloc.3
0x6a2cb  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x6a2d0  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x6a2d5  ldnull
0x6a2d6  ldnull
0x6a2d7  ldloc.s  9
0x6a2d9  call     T0x2B0000AD
0x6a2de  stloc.s  0xD
0x6a2e0  leave.s  loc_6A303
0x6a2e2  ldloc.0
0x6a2e3  brfalse.s loc_6A2EB
0x6a2e5  ldloc.0
0x6a2e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a2eb  endfinally
0x6a2ec  ldc.i4   0x10E657
0x6a2f1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6a2f6  ldc.i4.s 0x64
0x6a2f8  ldstr    aTaxonomyclient_13// "TaxonomyClientService: GetChildTermsInT"...
0x6a2fd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6a302  endfinally
0x6a303  ldloc.s  0xD
0x6a305  ret
```
