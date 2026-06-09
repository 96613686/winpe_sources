# Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::RecoverMergedTermRelationship

- ea: `0x61650`
- end: `0x618c0`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::RecoverMergedTermRelationship`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x60680`

## callees

- `0x48780`
- `0x48810`
- `0x4abe0`
- `0x4ada0`
- `0x4d000`
- `0x4e260`
- `0x4e570`
- `0x4e9a0`
- `0x4eef0`
- `0x4f070`
- `0x4f1e0`
- `0x4f490`
- `0x4f560`
- `0x52350`
- `0x555c0`
- `0x55830`
- `0x61650`
- `0x62970`

## string_xrefs

- `0x61787`: `SOX_MultiGeoTaxonomyDeleteOrphanedTermKillSwitch`
- `0x617cf`: `Deleted orphaned term. Id: {0}, deleted: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x61650  ldc.i4   0x120E486
0x61655  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6165a  ldc.i4.s 0x32
0x6165c  ldstr    aStartingToReco// "Starting to recover merged term relatio"...
0x61661  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x61666  ldarg.1
0x61667  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x6166c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x61671  stloc.s  8
0x61673  br       loc_61886
0x61678  ldloc.s  8
0x6167a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6167f  castclass class [mscorlib]System.Tuple`2<class Microsoft.SharePoint.Taxonomy.Term, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>>
0x61684  stloc.0
0x61685  ldloc.0
0x61686  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class Microsoft.SharePoint.Taxonomy.Term, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>>::get_Item1()
0x6168b  stloc.1
0x6168c  ldloc.1
0x6168d  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_SourceTerm()
0x61692  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x61697  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6169c  ldarg.0
0x6169d  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::termStore
0x616a2  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::get_OrphanedTermsTermSet()
0x616a7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x616ac  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x616b1  brfalse.s loc_61718
0x616b3  ldloc.1
0x616b4  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_SourceTerm()
0x616b9  ldloc.1
0x616ba  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::ReassignSourceTerm(class Microsoft.SharePoint.Taxonomy.Term reusedTerm)
0x616bf  ldc.i4   0x120E487
0x616c4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x616c9  ldc.i4.s 0x14
0x616cb  ldstr    aTheMergedTarge// "The merged target term is in OrphanedTe"...
0x616d0  ldc.i4.2
0x616d1  newarr   [mscorlib]System.Object
0x616d6  stloc.s  9
0x616d8  ldloc.s  9
0x616da  ldc.i4.0
0x616db  ldloc.1
0x616dc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x616e1  stloc.s  0xA
0x616e3  ldloca.s 0xA
0x616e5  constrained. [mscorlib]System.Guid
0x616eb  callvirt instance string [mscorlib]System.Object::ToString()
0x616f0  stelem.ref
0x616f1  ldloc.s  9
0x616f3  ldc.i4.1
0x616f4  ldloc.1
0x616f5  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x616fa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x616ff  stloc.s  0xB
0x61701  ldloca.s 0xB
0x61703  constrained. [mscorlib]System.Guid
0x61709  callvirt instance string [mscorlib]System.Object::ToString()
0x6170e  stelem.ref
0x6170f  ldloc.s  9
0x61711  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x61716  br.s     loc_6171F
0x61718  ldloc.1
0x61719  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_SourceTerm()
0x6171e  stloc.1
0x6171f  ldloc.1
0x61720  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x61725  brfalse.s loc_6172F
0x61727  ldloc.1
0x61728  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x6172d  br.s     loc_61735
0x6172f  ldloc.1
0x61730  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x61735  stloc.2
0x61736  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x6173b  stloc.s  0xC
0x6173d  ldloca.s 0xC
0x6173f  constrained. [mscorlib]System.Guid
0x61745  callvirt instance string [mscorlib]System.Object::ToString()
0x6174a  stloc.3
0x6174b  ldloc.0
0x6174c  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class Microsoft.SharePoint.Taxonomy.Term, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>>::get_Item2()
0x61751  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x61756  stloc.s  0xD
0x61758  br       loc_61812
0x6175d  ldloc.s  0xD
0x6175f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x61764  stloc.s  4
0x61766  ldloc.1
0x61767  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Term::get_MergedTermIds()
0x6176c  ldloc.s  4
0x6176e  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x61773  brtrue   loc_61812
0x61778  ldstr    a1b94adf91d5049// "1B94ADF9-1D50-4962-8CAC-28F027F6FF9A"
0x6177d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x61782  ldstr    a8232017// "8/23/2017"
0x61787  ldstr    aSoxMultigeotax// "SOX_MultiGeoTaxonomyDeleteOrphanedTermK"...
0x6178c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x61791  brtrue.s loc_617F3
0x61793  ldarg.0
0x61794  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::termStore
0x61799  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::get_OrphanedTermsTermSet()
0x6179e  ldloc.s  4
0x617a0  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSet::GetTerm(valuetype [mscorlib]System.Guid termId)
0x617a5  stloc.s  5
0x617a7  ldloc.s  5
0x617a9  brfalse.s loc_617F3
0x617ab  ldloc.s  5
0x617ad  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsReused()
0x617b2  brtrue.s loc_617F3
0x617b4  ldloc.s  5
0x617b6  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x617bb  ldarg.0
0x617bc  ldc.i4.1
0x617bd  ldc.i4.0
0x617be  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::CommitAll(bool commitNow, [opt] bool smallBatchSize)
0x617c3  ldc.i4   0x174965B
0x617c8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x617cd  ldc.i4.s 0x32
0x617cf  ldstr    aDeletedOrphane// "Deleted orphaned term. Id: {0}, deleted"...
0x617d4  ldc.i4.1
0x617d5  newarr   [mscorlib]System.Object
0x617da  stloc.s  0xE
0x617dc  ldloc.s  0xE
0x617de  ldc.i4.0
0x617df  ldloc.s  5
0x617e1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x617e6  box      [mscorlib]System.Guid
0x617eb  stelem.ref
0x617ec  ldloc.s  0xE
0x617ee  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x617f3  ldloc.2
0x617f4  ldloc.3
0x617f5  ldarg.0
0x617f6  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::termStore
0x617fb  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_WorkingLanguage()
0x61800  ldloc.s  4
0x61802  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm(string name, int32 lcid, valuetype [mscorlib]System.Guid newTermId)
0x61807  stloc.s  6
0x61809  ldloc.s  6
0x6180b  ldloc.1
0x6180c  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::Merge(class Microsoft.SharePoint.Taxonomy.Term termToMerge)
0x61811  pop
0x61812  ldloc.s  0xD
0x61814  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x61819  brtrue   loc_6175D
0x6181e  leave.s  loc_6182C
0x61820  ldloc.s  0xD
0x61822  brfalse.s loc_6182B
0x61824  ldloc.s  0xD
0x61826  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6182b  endfinally
0x6182c  ldloc.1
0x6182d  ldarg.0
0x6182e  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::termStore
0x61833  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_WorkingLanguage()
0x61838  callvirt instance class Microsoft.SharePoint.Taxonomy.LabelCollection Microsoft.SharePoint.Taxonomy.Term::GetAllLabels(int32 lcid)
0x6183d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Label>::GetEnumerator()
0x61842  stloc.s  0xF
0x61844  br.s     loc_61867
0x61846  ldloc.s  0xF
0x61848  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Label>::get_Current()
0x6184d  stloc.s  7
0x6184f  ldloc.s  7
0x61851  callvirt instance string Microsoft.SharePoint.Taxonomy.Label::get_Value()
0x61856  ldloc.3
0x61857  call     bool [mscorlib]System.String::Equals(string, string)
0x6185c  brfalse.s loc_61867
0x6185e  ldloc.s  7
0x61860  callvirt instance void Microsoft.SharePoint.Taxonomy.Label::Delete()
0x61865  br.s     loc_61870
0x61867  ldloc.s  0xF
0x61869  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6186e  brtrue.s loc_61846
0x61870  leave.s  loc_6187E
0x61872  ldloc.s  0xF
0x61874  brfalse.s loc_6187D
0x61876  ldloc.s  0xF
0x61878  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6187d  endfinally
0x6187e  ldarg.0
0x6187f  ldc.i4.1
0x61880  ldc.i4.0
0x61881  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::CommitAll(bool commitNow, [opt] bool smallBatchSize)
0x61886  ldloc.s  8
0x61888  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6188d  brtrue   loc_61678
0x61892  leave.s  loc_618A9
0x61894  ldloc.s  8
0x61896  isinst   [mscorlib]System.IDisposable
0x6189b  stloc.s  0x10
0x6189d  ldloc.s  0x10
0x6189f  brfalse.s loc_618A8
0x618a1  ldloc.s  0x10
0x618a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x618a8  endfinally
0x618a9  ldc.i4   0x120E488
0x618ae  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x618b3  ldc.i4.s 0x32
0x618b5  ldstr    aFinishedRecove// "Finished recovering merged term relatio"...
0x618ba  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x618bf  ret
```
