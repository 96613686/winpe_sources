# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetKeywordTermsByGuids

- ea: `0x69fb0`
- end: `0x6a15b`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetKeywordTermsByGuids`
- size: `427`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x244f0`
- `0x2acd0`
- `0x2fda0`
- `0x4baa0`
- `0x4cbf0`
- `0x4cc10`
- `0x4ee90`
- `0x50680`
- `0x54760`
- `0x55440`
- `0x557e0`
- `0x56bd0`
- `0x579a0`
- `0x69fb0`

## string_xrefs

- `0x69fbc`: `TaxonomyClientService: Get keyword terms by guids started`
- `0x6a125`: `TaxonomyClientService: Get keyword terms by guids failed: {0}`
- `0x6a14d`: `TaxonomyClientService: Get keyword terms by guids finished`

## pseudocode

```c

```

## disassembly

```asm
0x69fb0  ldc.i4   0x66363834
0x69fb5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x69fba  ldc.i4.s 0x64
0x69fbc  ldstr    aTaxonomyclient_9// "TaxonomyClientService: Get keyword term"...
0x69fc1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x69fc6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x69fcb  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x69fd0  stloc.0
0x69fd1  ldloc.0
0x69fd2  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x69fd7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::EnsureAuthentication(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x69fdc  ldarg.1
0x69fdd  call     valuetype [mscorlib]System.Guid[] Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetGuidsFromXml(string guids)
0x69fe2  stloc.1
0x69fe3  ldloc.1
0x69fe4  ldlen
0x69fe5  conv.i4
0x69fe6  brfalse  loc_6A0F1
0x69feb  ldloc.0
0x69fec  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x69ff1  stloc.2
0x69ff2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::.ctor()
0x69ff7  stloc.3
0x69ff8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::.ctor()
0x69ffd  stloc.s  4
0x69fff  ldloc.2
0x6a000  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x6a005  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::GetEnumerator()
0x6a00a  stloc.s  0xB
0x6a00c  br       loc_6A0C3
0x6a011  ldloc.s  0xB
0x6a013  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Current()
0x6a018  stloc.s  5
0x6a01a  ldloc.s  5
0x6a01c  ldloc.1
0x6a01d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.TermStore::GetTerms(valuetype [mscorlib]System.Guid[] termIds)
0x6a022  stloc.s  6
0x6a024  ldloc.s  5
0x6a026  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.SharePoint.Taxonomy.TermStore::get_Languages()
0x6a02b  ldarg.2
0x6a02c  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Contains(var<u1>)
0x6a031  brtrue.s loc_6A03C
0x6a033  ldloc.s  5
0x6a035  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x6a03a  starg.s  2
0x6a03c  ldloc.2
0x6a03d  callvirt instance class [System]System.Collections.Specialized.StringCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_OfflineTermStoreNames()
0x6a042  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::get_Count()
0x6a047  ldc.i4.0
0x6a048  ble.s    loc_6A060
0x6a04a  ldloc.s  6
0x6a04c  brfalse.s loc_6A05A
0x6a04e  ldloc.s  6
0x6a050  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x6a055  ldloc.1
0x6a056  ldlen
0x6a057  conv.i4
0x6a058  beq.s    loc_6A060
0x6a05a  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor()
0x6a05f  throw
0x6a060  ldloc.s  6
0x6a062  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x6a067  stloc.s  0xC
0x6a069  br.s     loc_6A0AC
0x6a06b  ldloc.s  0xC
0x6a06d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x6a072  stloc.s  7
0x6a074  ldloc.s  7
0x6a076  brfalse.s loc_6A0AC
0x6a078  ldloc.s  7
0x6a07a  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsDeprecated()
0x6a07f  brtrue.s loc_6A0AC
0x6a081  ldloc.s  5
0x6a083  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x6a088  ldloc.s  7
0x6a08a  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x6a08f  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::IsTermAvailableInAtLeastOneTermSet(class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm sharedTerm)
0x6a094  brfalse.s loc_6A0AC
0x6a096  ldloc.s  4
0x6a098  ldloc.s  7
0x6a09a  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x6a09f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::Add(var<u1>)
0x6a0a4  ldloc.3
0x6a0a5  ldloc.s  5
0x6a0a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TermStore>::Add(var<u1>)
0x6a0ac  ldloc.s  0xC
0x6a0ae  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a0b3  brtrue.s loc_6A06B
0x6a0b5  leave.s  loc_6A0C3
0x6a0b7  ldloc.s  0xC
0x6a0b9  brfalse.s loc_6A0C2
0x6a0bb  ldloc.s  0xC
0x6a0bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a0c2  endfinally
0x6a0c3  ldloc.s  0xB
0x6a0c5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a0ca  brtrue   loc_6A011
0x6a0cf  leave.s  loc_6A0DD
0x6a0d1  ldloc.s  0xB
0x6a0d3  brfalse.s loc_6A0DC
0x6a0d5  ldloc.s  0xB
0x6a0d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a0dc  endfinally
0x6a0dd  ldloc.3
0x6a0de  ldloc.s  4
0x6a0e0  ldarg.2
0x6a0e1  ldc.i4.0
0x6a0e2  ldnull
0x6a0e3  ldnull
0x6a0e4  call     T0x2B0000AC
0x6a0e9  stloc.s  8
0x6a0eb  ldloc.s  8
0x6a0ed  stloc.s  0xA
0x6a0ef  leave.s  loc_6A158
0x6a0f1  ldc.i4   0x10E655
0x6a0f6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6a0fb  ldc.i4.s 0x64
0x6a0fd  ldstr    aNoIdsPassedInT// "No Ids passed in to GetKeywordTermsByGu"...
0x6a102  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6a107  ldstr    aErrorkeywordte// "ErrorKeywordTermSetNoHierarchy"
0x6a10c  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x6a111  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6a116  throw
0x6a117  stloc.s  9
0x6a119  ldc.i4   0x66363836
0x6a11e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6a123  ldc.i4.s 0xA
0x6a125  ldstr    aTaxonomyclient_10// "TaxonomyClientService: Get keyword term"...
0x6a12a  ldc.i4.1
0x6a12b  newarr   [mscorlib]System.Object
0x6a130  stloc.s  0xD
0x6a132  ldloc.s  0xD
0x6a134  ldc.i4.0
0x6a135  ldloc.s  9
0x6a137  stelem.ref
0x6a138  ldloc.s  0xD
0x6a13a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6a13f  rethrow
0x6a141  ldc.i4   0x66363835
0x6a146  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6a14b  ldc.i4.s 0x64
0x6a14d  ldstr    aTaxonomyclient_11// "TaxonomyClientService: Get keyword term"...
0x6a152  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6a157  endfinally
0x6a158  ldloc.s  0xA
0x6a15a  ret
```
