# Microsoft.SharePoint.Taxonomy.Term::Move_0

- ea: `0x4e850`
- end: `0x4e992`
- name: `Microsoft.SharePoint.Taxonomy.Term::Move_0`
- size: `322`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x4e670`
- `0x61d50`
- `0x6e6e0`

## callees

- `0x242a0`
- `0x2acd0`
- `0x2dc00`
- `0x48810`
- `0x48830`
- `0x48840`
- `0x48a60`
- `0x48ac0`
- `0x4d550`
- `0x4dad0`
- `0x4e0d0`
- `0x4e850`
- `0x4f1e0`
- `0x4f330`
- `0x4f560`
- `0x4f6d0`
- `0x4fe30`
- `0x50620`
- `0x50a30`
- `0x51680`
- `0x536f0`
- `0x579b0`

## string_xrefs

- `0x4e913`: `ErrorCannotMoveToReusedTermSet`
- `0x4e85c`: `Begin: Term.Move(TermSet)`
- `0x4e987`: `End: Term.Move(TermSet)`

## pseudocode

```c

```

## disassembly

```asm
0x4e850  ldc.i4   0x32657679
0x4e855  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4e85a  ldc.i4.s 0x64
0x4e85c  ldstr    aBeginTermMoveT_0// "Begin: Term.Move(TermSet)"
0x4e861  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4e866  ldarg.1
0x4e867  ldstr    aParenttermset// "parentTermSet"
0x4e86c  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x4e871  ldarg.0
0x4e872  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x4e877  ldarg.0
0x4e878  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x4e87d  ldarg.0
0x4e87e  call     instance void Microsoft.SharePoint.Taxonomy.Term::EnsureParentNotPinned()
0x4e883  ldc.i4.1
0x4e884  conv.i8
0x4e885  ldarg.0
0x4e886  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x4e88b  ldarg.0
0x4e88c  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4e891  ldarg.0
0x4e892  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x4e897  ldarg.0
0x4e898  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e89d  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x4e8a2  ldarg.1
0x4e8a3  callvirt instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x4e8a8  ldc.i4.1
0x4e8a9  conv.i8
0x4e8aa  ldarg.1
0x4e8ab  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x4e8b0  ldarg.0
0x4e8b1  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4e8b6  ldarg.1
0x4e8b7  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x4e8bc  ldarg.1
0x4e8bd  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x4e8c2  ldarg.0
0x4e8c3  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e8c8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e8cd  ldarg.1
0x4e8ce  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e8d3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4e8d8  brfalse.s loc_4E8E3
0x4e8da  ldarg.0
0x4e8db  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x4e8e0  brtrue.s loc_4E8E3
0x4e8e2  ret
0x4e8e3  ldarg.0
0x4e8e4  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.TermSetItem::get_Terms()
0x4e8e9  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x4e8ee  ldc.i4.0
0x4e8ef  ble.s    loc_4E90A
0x4e8f1  ldarg.1
0x4e8f2  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.TermSet::get_Type()
0x4e8f7  ldc.i4.1
0x4e8f8  bne.un.s loc_4E90A
0x4e8fa  ldstr    aErrorhierarchy// "ErrorHierarchyNotAllowedInKeywordTermSe"...
0x4e8ff  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4e904  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4e909  throw
0x4e90a  ldarg.0
0x4e90b  ldarg.1
0x4e90c  call     instance bool Microsoft.SharePoint.Taxonomy.Term::ContainsReusedTerms(class Microsoft.SharePoint.Taxonomy.TermSet targetTermSet)
0x4e911  brfalse.s loc_4E923
0x4e913  ldstr    aErrorcannotmov// "ErrorCannotMoveToReusedTermSet"
0x4e918  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4e91d  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4e922  throw
0x4e923  ldarg.0
0x4e924  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Term::get_ReusedPinnedTerms()
0x4e929  stloc.0
0x4e92a  ldarg.0
0x4e92b  ldarg.0
0x4e92c  call     instance class Microsoft.SharePoint.Taxonomy.TermSetItem Microsoft.SharePoint.Taxonomy.Term::get_ParentItem()
0x4e931  ldarg.1
0x4e932  call     instance void Microsoft.SharePoint.Taxonomy.Term::MoveTermInSandbox(class Microsoft.SharePoint.Taxonomy.TermSetItem sourceParent, class Microsoft.SharePoint.Taxonomy.TermSetItem targetParent)
0x4e937  ldloc.0
0x4e938  brfalse.s loc_4E97B
0x4e93a  ldloc.0
0x4e93b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x4e940  ldc.i4.0
0x4e941  ble.s    loc_4E97B
0x4e943  ldloc.0
0x4e944  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x4e949  stloc.2
0x4e94a  br.s     loc_4E962
0x4e94c  ldloca.s 2
0x4e94e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x4e953  stloc.1
0x4e954  ldloc.1
0x4e955  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsPinnedRoot()
0x4e95a  brtrue.s loc_4E962
0x4e95c  ldloc.1
0x4e95d  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::DeleteCore()
0x4e962  ldloca.s 2
0x4e964  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>::MoveNext()
0x4e969  brtrue.s loc_4E94C
0x4e96b  leave.s  loc_4E97B
0x4e96d  ldloca.s 2
0x4e96f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>
0x4e975  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e97a  endfinally
0x4e97b  ldc.i4   0x3265767A
0x4e980  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4e985  ldc.i4.s 0x64
0x4e987  ldstr    aEndTermMoveTer_0// "End: Term.Move(TermSet)"
0x4e98c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4e991  ret
```
