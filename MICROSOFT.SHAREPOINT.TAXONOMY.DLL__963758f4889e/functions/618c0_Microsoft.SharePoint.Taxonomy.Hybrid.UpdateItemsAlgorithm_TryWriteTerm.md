# Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::TryWriteTerm

- ea: `0x618c0`
- end: `0x61c6e`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::TryWriteTerm`
- size: `942`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x611b0`

## callees

- `0x487f0`
- `0x48810`
- `0x4e9a0`
- `0x4ef30`
- `0x4f320`
- `0x4f490`
- `0x4f560`
- `0x52e10`
- `0x54710`
- `0x55050`
- `0x618c0`
- `0x61c70`
- `0x61ce0`
- `0x61d50`
- `0x61de0`
- `0x61e60`
- `0x61ec0`
- `0x62640`
- `0x62870`

## string_xrefs

- `0x618cc`: `Try to write term to local termstore. Term name is {0}, guid is {1}. TermSet guid is {2}.`
- `0x61a58`: `Return false. Can't delete the term since it isn't pin root. Term guid is {0}. TermSet guid is {1}.`
- `0x61ac1`: `Return false. Can not find term parent when trying to create or resue term. Term guid is {0}. TermSet guid is {1}.`
- `0x61b3d`: `Return false. Can not find term parent when trying to move term. Term guid is {0}. TermSet guid is {1}.`
- `0x61c12`: `Return true. The term write successfully. Term guid is {0}. TermSet name is {1}. TermSet guid is {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x618c0  ldc.i4   0x120E489
0x618c5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x618ca  ldc.i4.s 0x64
0x618cc  ldstr    aTryToWriteTerm// "Try to write term to local termstore. T"...
0x618d1  ldc.i4.3
0x618d2  newarr   [mscorlib]System.Object
0x618d7  stloc.s  5
0x618d9  ldloc.s  5
0x618db  ldc.i4.0
0x618dc  ldarg.1
0x618dd  callvirt instance string [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Name()
0x618e2  stelem.ref
0x618e3  ldloc.s  5
0x618e5  ldc.i4.1
0x618e6  ldarg.1
0x618e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x618ec  stloc.s  6
0x618ee  ldloca.s 6
0x618f0  constrained. [mscorlib]System.Guid
0x618f6  callvirt instance string [mscorlib]System.Object::ToString()
0x618fb  stelem.ref
0x618fc  ldloc.s  5
0x618fe  ldc.i4.2
0x618ff  ldarg.1
0x61900  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_TermSet()
0x61905  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x6190a  stloc.s  7
0x6190c  ldloca.s 7
0x6190e  constrained. [mscorlib]System.Guid
0x61914  callvirt instance string [mscorlib]System.Object::ToString()
0x61919  stelem.ref
0x6191a  ldloc.s  5
0x6191c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x61921  ldnull
0x61922  stloc.0
0x61923  ldarg.1
0x61924  callvirt instance bool [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_IsPinned()
0x61929  brfalse  loc_61A0B
0x6192e  ldarg.1
0x6192f  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_PinSourceTermSet()
0x61934  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientObject::get_ServerObjectIsNull()
0x61939  stloc.s  8
0x6193b  ldloca.s 8
0x6193d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x61942  brtrue.s loc_6194D
0x61944  ldloca.s 8
0x61946  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6194b  br.s     loc_6194E
0x6194d  ldc.i4.0
0x6194e  brfalse  loc_61A0B
0x61953  ldarg.0
0x61954  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::termStore
0x61959  ldarg.1
0x6195a  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_PinSourceTermSet()
0x6195f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61964  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x61969  dup
0x6196a  stloc.0
0x6196b  brfalse  loc_61A0B
0x61970  ldarg.0
0x61971  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::targetGroupIds
0x61976  ldloc.0
0x61977  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermSet::get_Group()
0x6197c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x61981  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x61986  brfalse  loc_61A0B
0x6198b  ldarg.1
0x6198c  callvirt instance bool [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_IsPinnedRoot()
0x61991  brfalse.s loc_6199A
0x61993  ldarg.2
0x61994  ldarg.1
0x61995  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::Add(var<u1>)
0x6199a  ldarg.0
0x6199b  ldarg.1
0x6199c  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_TermSet()
0x619a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x619a6  ldarg.1
0x619a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x619ac  call     instance bool Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::DeleteTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x619b1  pop
0x619b2  ldc.i4   0x120E48A
0x619b7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x619bc  ldc.i4.s 0x64
0x619be  ldstr    aReturnTrueTheT// "Return true. The term is pinned. Term g"...
0x619c3  ldc.i4.2
0x619c4  newarr   [mscorlib]System.Object
0x619c9  stloc.s  9
0x619cb  ldloc.s  9
0x619cd  ldc.i4.0
0x619ce  ldarg.1
0x619cf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x619d4  stloc.s  0xA
0x619d6  ldloca.s 0xA
0x619d8  constrained. [mscorlib]System.Guid
0x619de  callvirt instance string [mscorlib]System.Object::ToString()
0x619e3  stelem.ref
0x619e4  ldloc.s  9
0x619e6  ldc.i4.1
0x619e7  ldarg.1
0x619e8  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_TermSet()
0x619ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x619f2  stloc.s  0xB
0x619f4  ldloca.s 0xB
0x619f6  constrained. [mscorlib]System.Guid
0x619fc  callvirt instance string [mscorlib]System.Object::ToString()
0x61a01  stelem.ref
0x61a02  ldloc.s  9
0x61a04  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x61a09  ldc.i4.1
0x61a0a  ret
0x61a0b  ldarg.0
0x61a0c  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::termStore
0x61a11  ldarg.1
0x61a12  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_TermSet()
0x61a17  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61a1c  ldarg.1
0x61a1d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61a22  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x61a27  stloc.1
0x61a28  ldloc.1
0x61a29  brfalse.s loc_61AA7
0x61a2b  ldloc.1
0x61a2c  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsPinned()
0x61a31  brfalse.s loc_61AA7
0x61a33  ldarg.0
0x61a34  ldloc.1
0x61a35  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x61a3a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x61a3f  ldloc.1
0x61a40  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x61a45  call     instance bool Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::DeleteTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x61a4a  brtrue.s loc_61AA5
0x61a4c  ldc.i4   0x120E48B
0x61a51  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x61a56  ldc.i4.s 0x32
0x61a58  ldstr    aReturnFalseCan// "Return false. Can't delete the term sin"...
0x61a5d  ldc.i4.2
0x61a5e  newarr   [mscorlib]System.Object
0x61a63  stloc.s  0xC
0x61a65  ldloc.s  0xC
0x61a67  ldc.i4.0
0x61a68  ldarg.1
0x61a69  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61a6e  stloc.s  0xD
0x61a70  ldloca.s 0xD
0x61a72  constrained. [mscorlib]System.Guid
0x61a78  callvirt instance string [mscorlib]System.Object::ToString()
0x61a7d  stelem.ref
0x61a7e  ldloc.s  0xC
0x61a80  ldc.i4.1
0x61a81  ldarg.1
0x61a82  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_TermSet()
0x61a87  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61a8c  stloc.s  0xE
0x61a8e  ldloca.s 0xE
0x61a90  constrained. [mscorlib]System.Guid
0x61a96  callvirt instance string [mscorlib]System.Object::ToString()
0x61a9b  stelem.ref
0x61a9c  ldloc.s  0xC
0x61a9e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x61aa3  ldc.i4.0
0x61aa4  ret
0x61aa5  ldnull
0x61aa6  stloc.1
0x61aa7  ldloc.1
0x61aa8  brtrue.s loc_61B1C
0x61aaa  ldarg.0
0x61aab  ldarg.1
0x61aac  call     instance class Microsoft.SharePoint.Taxonomy.TermSetItem Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::GetParent(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term remoteTerm)
0x61ab1  stloc.2
0x61ab2  ldloc.2
0x61ab3  brtrue.s loc_61B0E
0x61ab5  ldc.i4   0x120E48C
0x61aba  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x61abf  ldc.i4.s 0x32
0x61ac1  ldstr    aReturnFalseCan_0// "Return false. Can not find term parent "...
0x61ac6  ldc.i4.2
0x61ac7  newarr   [mscorlib]System.Object
0x61acc  stloc.s  0xF
0x61ace  ldloc.s  0xF
0x61ad0  ldc.i4.0
0x61ad1  ldarg.1
0x61ad2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61ad7  stloc.s  0x10
0x61ad9  ldloca.s 0x10
0x61adb  constrained. [mscorlib]System.Guid
0x61ae1  callvirt instance string [mscorlib]System.Object::ToString()
0x61ae6  stelem.ref
0x61ae7  ldloc.s  0xF
0x61ae9  ldc.i4.1
0x61aea  ldarg.1
0x61aeb  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_TermSet()
0x61af0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61af5  stloc.s  0x11
0x61af7  ldloca.s 0x11
0x61af9  constrained. [mscorlib]System.Guid
0x61aff  callvirt instance string [mscorlib]System.Object::ToString()
0x61b04  stelem.ref
0x61b05  ldloc.s  0xF
0x61b07  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x61b0c  ldc.i4.0
0x61b0d  ret
0x61b0e  ldarg.0
0x61b0f  ldarg.1
0x61b10  ldloc.2
0x61b11  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::CreateOrReuseTerm(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term remoteTerm, class Microsoft.SharePoint.Taxonomy.TermSetItem localParent)
0x61b16  stloc.1
0x61b17  br       loc_61BAE
0x61b1c  ldarg.0
0x61b1d  ldarg.1
0x61b1e  ldloc.1
0x61b1f  call     instance bool Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::ParentIsSame(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term remoteTerm, class Microsoft.SharePoint.Taxonomy.Term localTerm)
0x61b24  brtrue.s loc_61B9C
0x61b26  ldarg.0
0x61b27  ldarg.1
0x61b28  call     instance class Microsoft.SharePoint.Taxonomy.TermSetItem Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::GetParent(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term remoteTerm)
0x61b2d  stloc.3
0x61b2e  ldloc.3
0x61b2f  brtrue.s loc_61B8A
0x61b31  ldc.i4   0x120E48D
0x61b36  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x61b3b  ldc.i4.s 0x32
0x61b3d  ldstr    aReturnFalseCan_1// "Return false. Can not find term parent "...
0x61b42  ldc.i4.2
0x61b43  newarr   [mscorlib]System.Object
0x61b48  stloc.s  0x12
0x61b4a  ldloc.s  0x12
0x61b4c  ldc.i4.0
0x61b4d  ldarg.1
0x61b4e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61b53  stloc.s  0x13
0x61b55  ldloca.s 0x13
0x61b57  constrained. [mscorlib]System.Guid
0x61b5d  callvirt instance string [mscorlib]System.Object::ToString()
0x61b62  stelem.ref
0x61b63  ldloc.s  0x12
0x61b65  ldc.i4.1
0x61b66  ldarg.1
0x61b67  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_TermSet()
0x61b6c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61b71  stloc.s  0x14
0x61b73  ldloca.s 0x14
0x61b75  constrained. [mscorlib]System.Guid
0x61b7b  callvirt instance string [mscorlib]System.Object::ToString()
0x61b80  stelem.ref
0x61b81  ldloc.s  0x12
0x61b83  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x61b88  ldc.i4.0
0x61b89  ret
0x61b8a  ldarg.0
0x61b8b  ldarg.1
0x61b8c  ldloc.1
0x61b8d  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::RenameDefaultTermLabel(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term remoteTerm, class Microsoft.SharePoint.Taxonomy.Term term)
0x61b92  ldarg.0
0x61b93  ldloc.1
0x61b94  ldloc.3
0x61b95  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::MoveTerm(class Microsoft.SharePoint.Taxonomy.Term term, class Microsoft.SharePoint.Taxonomy.TermSetItem parent)
0x61b9a  br.s     loc_61BAE
0x61b9c  ldarg.0
0x61b9d  ldarg.1
0x61b9e  ldloc.1
0x61b9f  call     instance bool Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::DefaultLabelIsSame(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term remoteTerm, class Microsoft.SharePoint.Taxonomy.Term term)
0x61ba4  brtrue.s loc_61BAE
0x61ba6  ldarg.0
0x61ba7  ldarg.1
0x61ba8  ldloc.1
0x61ba9  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::RenameDefaultTermLabel(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term remoteTerm, class Microsoft.SharePoint.Taxonomy.Term term)
0x61bae  ldarg.1
0x61baf  callvirt instance bool [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_IsSourceTerm()
0x61bb4  brfalse.s loc_61BCA
0x61bb6  ldloc.1
0x61bb7  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsSourceTerm()
0x61bbc  brtrue.s loc_61BCA
0x61bbe  ldloc.1
0x61bbf  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_SourceTerm()
0x61bc4  ldloc.1
0x61bc5  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::ReassignSourceTerm(class Microsoft.SharePoint.Taxonomy.Term reusedTerm)
0x61bca  ldarg.0
0x61bcb  ldloc.1
0x61bcc  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::EnableTerm(class Microsoft.SharePoint.Taxonomy.Term term)
0x61bd1  ldarg.1
0x61bd2  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_TermSet()
0x61bd7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x61bdc  ldloc.1
0x61bdd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x61be2  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor(var<u1>, !!T0)
0x61be7  stloc.s  4
0x61be9  ldarg.0
0x61bea  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::termCache
0x61bef  ldloc.s  4
0x61bf1  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x61bf6  brtrue.s loc_61C06
0x61bf8  ldarg.0
0x61bf9  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::termCache
0x61bfe  ldloc.s  4
0x61c00  ldloc.1
0x61c01  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x61c06  ldc.i4   0x120E48E
0x61c0b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x61c10  ldc.i4.s 0x64
  ... truncated ...
```
