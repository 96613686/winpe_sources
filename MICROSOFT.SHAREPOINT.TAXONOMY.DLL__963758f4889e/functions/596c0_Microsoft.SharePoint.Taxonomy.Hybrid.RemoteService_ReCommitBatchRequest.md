# Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ReCommitBatchRequest

- ea: `0x596c0`
- end: `0x59b81`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ReCommitBatchRequest`
- size: `1217`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x59bf0`

## callees

- `0x48810`
- `0x4f560`
- `0x58520`
- `0x58530`
- `0x58540`
- `0x58550`
- `0x58560`
- `0x58570`
- `0x58580`
- `0x58590`
- `0x58940`
- `0x58ab0`
- `0x58c90`
- `0x59040`
- `0x59070`
- `0x590b0`
- `0x59150`
- `0x596c0`
- `0x59bd0`

## string_xrefs

- `0x596cc`: `Re-commit current batch in Migration`
- `0x59865`: `Re-commit {0} group(s)`
- `0x598dc`: `Re-commit {0} term set(s)`
- `0x59953`: `Taxonomy migration: Re-commit {0} term(s)`
- `0x599ca`: `Taxonomy migration: Re-commit {0} pinned root term(s)`
- `0x59a41`: `Taxonomy migration Re-commit {0} deprecated term(s)`
- `0x59ab8`: `Taxonomy migration Re-commit {0} source term membership(s)`
- `0x59b2f`: `Taxonomy migration: Re-commit {0} pinned term(s)`
- `0x59b68`: `Taxonomy migration: Re-Commit current batch in Migration successful`

## pseudocode

```c

```

## disassembly

```asm
0x596c0  ldc.i4   0x1210595
0x596c5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x596ca  ldc.i4.s 0x32
0x596cc  ldstr    aReCommitCurren// "Re-commit current batch in Migration"
0x596d1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x596d6  ldarg.0
0x596d7  ldfld    int32 Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::batchSize
0x596dc  stloc.0
0x596dd  ldarg.0
0x596de  ldc.i4   0x7FFFFFFF
0x596e3  stfld    int32 Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::batchSize
0x596e8  ldarg.0
0x596e9  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x596ee  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Group> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_Groups()
0x596f3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Group>::GetEnumerator()
0x596f8  stloc.s  0xE
0x596fa  br.s     loc_59716
0x596fc  ldloc.s  0xE
0x596fe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Group>::get_Current()
0x59703  stloc.1
0x59704  ldarg.0
0x59705  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreGroups
0x5970a  ldloc.1
0x5970b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x59710  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup>::Remove(var<u1>)
0x59715  pop
0x59716  ldloc.s  0xE
0x59718  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5971d  brtrue.s loc_596FC
0x5971f  leave.s  loc_5972D
0x59721  ldloc.s  0xE
0x59723  brfalse.s loc_5972C
0x59725  ldloc.s  0xE
0x59727  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5972c  endfinally
0x5972d  ldarg.0
0x5972e  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59733  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_TermSets()
0x59738  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.TermSet>::GetEnumerator()
0x5973d  stloc.s  0xF
0x5973f  br.s     loc_5975B
0x59741  ldloc.s  0xF
0x59743  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.TermSet>::get_Current()
0x59748  stloc.2
0x59749  ldarg.0
0x5974a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreTermSets
0x5974f  ldloc.2
0x59750  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x59755  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet>::Remove(var<u1>)
0x5975a  pop
0x5975b  ldloc.s  0xF
0x5975d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59762  brtrue.s loc_59741
0x59764  leave.s  loc_59772
0x59766  ldloc.s  0xF
0x59768  brfalse.s loc_59771
0x5976a  ldloc.s  0xF
0x5976c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59771  endfinally
0x59772  ldarg.0
0x59773  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59778  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_TermMemberships()
0x5977d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x59782  stloc.s  0x10
0x59784  br.s     loc_597B0
0x59786  ldloc.s  0x10
0x59788  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x5978d  stloc.3
0x5978e  ldarg.0
0x5978f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreTermMemeberships
0x59794  ldloc.3
0x59795  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x5979a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x5979f  ldloc.3
0x597a0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x597a5  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor(var<u1>, !!T0)
0x597aa  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::Remove(var<u1>)
0x597af  pop
0x597b0  ldloc.s  0x10
0x597b2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x597b7  brtrue.s loc_59786
0x597b9  leave.s  loc_597C7
0x597bb  ldloc.s  0x10
0x597bd  brfalse.s loc_597C6
0x597bf  ldloc.s  0x10
0x597c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x597c6  endfinally
0x597c7  ldarg.0
0x597c8  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x597cd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_SourceTerms()
0x597d2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x597d7  stloc.s  0x11
0x597d9  br.s     loc_597F7
0x597db  ldloc.s  0x11
0x597dd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x597e2  stloc.s  4
0x597e4  ldarg.0
0x597e5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreTerms
0x597ea  ldloc.s  4
0x597ec  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x597f1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::Remove(var<u1>)
0x597f6  pop
0x597f7  ldloc.s  0x11
0x597f9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x597fe  brtrue.s loc_597DB
0x59800  leave.s  loc_5980E
0x59802  ldloc.s  0x11
0x59804  brfalse.s loc_5980D
0x59806  ldloc.s  0x11
0x59808  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5980d  endfinally
0x5980e  ldc.i4.0
0x5980f  stloc.s  5
0x59811  ldc.i4.0
0x59812  stloc.s  6
0x59814  ldarg.0
0x59815  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x5981a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Group> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_Groups()
0x5981f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Group>::GetEnumerator()
0x59824  stloc.s  0x12
0x59826  br.s     loc_59842
0x59828  ldloc.s  0x12
0x5982a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Group>::get_Current()
0x5982f  stloc.s  7
0x59831  ldarg.0
0x59832  ldloc.s  7
0x59834  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::CreateGroup(class Microsoft.SharePoint.Taxonomy.Group group)
0x59839  ldarg.0
0x5983a  ldloca.s 5
0x5983c  ldarg.1
0x5983d  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ExecuteClientQueryInBatch(int32& actionCount, int32 currentBatchSize)
0x59842  ldloc.s  0x12
0x59844  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59849  brtrue.s loc_59828
0x5984b  leave.s  loc_59859
0x5984d  ldloc.s  0x12
0x5984f  brfalse.s loc_59858
0x59851  ldloc.s  0x12
0x59853  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59858  endfinally
0x59859  ldc.i4   0x1210596
0x5985e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59863  ldc.i4.s 0x64
0x59865  ldstr    aReCommit0Group// "Re-commit {0} group(s)"
0x5986a  ldc.i4.1
0x5986b  newarr   [mscorlib]System.Object
0x59870  stloc.s  0x13
0x59872  ldloc.s  0x13
0x59874  ldc.i4.0
0x59875  ldloc.s  5
0x59877  ldloc.s  6
0x59879  sub.ovf
0x5987a  box      [mscorlib]System.Int32
0x5987f  stelem.ref
0x59880  ldloc.s  0x13
0x59882  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x59887  ldloc.s  5
0x59889  stloc.s  6
0x5988b  ldarg.0
0x5988c  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59891  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_TermSets()
0x59896  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.TermSet>::GetEnumerator()
0x5989b  stloc.s  0x14
0x5989d  br.s     loc_598B9
0x5989f  ldloc.s  0x14
0x598a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.TermSet>::get_Current()
0x598a6  stloc.s  8
0x598a8  ldarg.0
0x598a9  ldloc.s  8
0x598ab  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::CreateTermSet(class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x598b0  ldarg.0
0x598b1  ldloca.s 5
0x598b3  ldarg.1
0x598b4  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ExecuteClientQueryInBatch(int32& actionCount, int32 currentBatchSize)
0x598b9  ldloc.s  0x14
0x598bb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x598c0  brtrue.s loc_5989F
0x598c2  leave.s  loc_598D0
0x598c4  ldloc.s  0x14
0x598c6  brfalse.s loc_598CF
0x598c8  ldloc.s  0x14
0x598ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x598cf  endfinally
0x598d0  ldc.i4   0x1210597
0x598d5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x598da  ldc.i4.s 0x64
0x598dc  ldstr    aReCommit0TermS// "Re-commit {0} term set(s)"
0x598e1  ldc.i4.1
0x598e2  newarr   [mscorlib]System.Object
0x598e7  stloc.s  0x15
0x598e9  ldloc.s  0x15
0x598eb  ldc.i4.0
0x598ec  ldloc.s  5
0x598ee  ldloc.s  6
0x598f0  sub.ovf
0x598f1  box      [mscorlib]System.Int32
0x598f6  stelem.ref
0x598f7  ldloc.s  0x15
0x598f9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x598fe  ldloc.s  5
0x59900  stloc.s  6
0x59902  ldarg.0
0x59903  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59908  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_TermMemberships()
0x5990d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x59912  stloc.s  0x16
0x59914  br.s     loc_59930
0x59916  ldloc.s  0x16
0x59918  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x5991d  stloc.s  9
0x5991f  ldarg.0
0x59920  ldloc.s  9
0x59922  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::CreateTerm(class Microsoft.SharePoint.Taxonomy.Term term)
0x59927  ldarg.0
0x59928  ldloca.s 5
0x5992a  ldarg.1
0x5992b  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ExecuteClientQueryInBatch(int32& actionCount, int32 currentBatchSize)
0x59930  ldloc.s  0x16
0x59932  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59937  brtrue.s loc_59916
0x59939  leave.s  loc_59947
0x5993b  ldloc.s  0x16
0x5993d  brfalse.s loc_59946
0x5993f  ldloc.s  0x16
0x59941  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59946  endfinally
0x59947  ldc.i4   0x1210598
0x5994c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59951  ldc.i4.s 0x64
0x59953  ldstr    aTaxonomyMigrat_0// "Taxonomy migration: Re-commit {0} term("...
0x59958  ldc.i4.1
0x59959  newarr   [mscorlib]System.Object
0x5995e  stloc.s  0x17
0x59960  ldloc.s  0x17
0x59962  ldc.i4.0
0x59963  ldloc.s  5
0x59965  ldloc.s  6
0x59967  sub.ovf
0x59968  box      [mscorlib]System.Int32
0x5996d  stelem.ref
0x5996e  ldloc.s  0x17
0x59970  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x59975  ldloc.s  5
0x59977  stloc.s  6
0x59979  ldarg.0
0x5997a  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x5997f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_PinnedRootTerms()
0x59984  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x59989  stloc.s  0x18
0x5998b  br.s     loc_599A7
0x5998d  ldloc.s  0x18
0x5998f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x59994  stloc.s  0xA
0x59996  ldarg.0
0x59997  ldloc.s  0xA
0x59999  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::CreatePinedRootTerm(class Microsoft.SharePoint.Taxonomy.Term term)
0x5999e  ldarg.0
0x5999f  ldloca.s 5
0x599a1  ldarg.1
0x599a2  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ExecuteClientQueryInBatch(int32& actionCount, int32 currentBatchSize)
0x599a7  ldloc.s  0x18
0x599a9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x599ae  brtrue.s loc_5998D
0x599b0  leave.s  loc_599BE
0x599b2  ldloc.s  0x18
0x599b4  brfalse.s loc_599BD
0x599b6  ldloc.s  0x18
0x599b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x599bd  endfinally
0x599be  ldc.i4   0x1210599
0x599c3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x599c8  ldc.i4.s 0x64
0x599ca  ldstr    aTaxonomyMigrat_1// "Taxonomy migration: Re-commit {0} pinne"...
0x599cf  ldc.i4.1
0x599d0  newarr   [mscorlib]System.Object
0x599d5  stloc.s  0x19
0x599d7  ldloc.s  0x19
0x599d9  ldc.i4.0
0x599da  ldloc.s  5
0x599dc  ldloc.s  6
0x599de  sub.ovf
0x599df  box      [mscorlib]System.Int32
0x599e4  stelem.ref
0x599e5  ldloc.s  0x19
0x599e7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x599ec  ldloc.s  5
0x599ee  stloc.s  6
0x599f0  ldarg.0
0x599f1  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x599f6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_DeprecatedTerms()
0x599fb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>>::GetEnumerator()
0x59a00  stloc.s  0x1A
0x59a02  br.s     loc_59A1E
0x59a04  ldloc.s  0x1A
0x59a06  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>>::get_Current()
0x59a0b  stloc.s  0xB
0x59a0d  ldarg.0
0x59a0e  ldloc.s  0xB
0x59a10  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::SetDeprecatedTerm(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> uniqueKey)
0x59a15  ldarg.0
  ... truncated ...
```
