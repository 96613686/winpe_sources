# Microsoft.SharePoint.Taxonomy.Term::Move

- ea: `0x4e6a0`
- end: `0x4e842`
- name: `Microsoft.SharePoint.Taxonomy.Term::Move`
- size: `418`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x4e670`
- `0x61d50`
- `0x6e7e0`

## callees

- `0x242a0`
- `0x2acd0`
- `0x2dc00`
- `0x48810`
- `0x48830`
- `0x48840`
- `0x48a60`
- `0x48ac0`
- `0x4dad0`
- `0x4e6a0`
- `0x4ecf0`
- `0x4eeb0`
- `0x4f1e0`
- `0x4f560`
- `0x4f6a0`
- `0x4f6d0`
- `0x4fe30`
- `0x50620`
- `0x50a30`
- `0x50d60`
- `0x51680`
- `0x579b0`

## string_xrefs

- `0x4e6ac`: `Begin: Term.Move(Term)`
- `0x4e7c2`: `ErrorCannotMoveToReusedTermSet`
- `0x4e7e5`: `ErrorCannotMoveToTermSelf`
- `0x4e7fe`: `ErrorCannotMoveToDescendentTerm`
- `0x4e837`: `End: Term.Move(Term)`

## pseudocode

```c

```

## disassembly

```asm
0x4e6a0  ldc.i4   0x32657677
0x4e6a5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4e6aa  ldc.i4.s 0x64
0x4e6ac  ldstr    aBeginTermMoveT// "Begin: Term.Move(Term)"
0x4e6b1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4e6b6  ldarg.1
0x4e6b7  ldstr    aNewparentterm// "newParentTerm"
0x4e6bc  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x4e6c1  ldarg.0
0x4e6c2  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x4e6c7  ldarg.0
0x4e6c8  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x4e6cd  ldarg.0
0x4e6ce  call     instance void Microsoft.SharePoint.Taxonomy.Term::EnsureParentNotPinned()
0x4e6d3  ldarg.1
0x4e6d4  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::EnsureNotPinned()
0x4e6d9  ldc.i4.1
0x4e6da  conv.i8
0x4e6db  ldarg.0
0x4e6dc  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x4e6e1  ldarg.0
0x4e6e2  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4e6e7  ldarg.0
0x4e6e8  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x4e6ed  ldarg.0
0x4e6ee  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e6f3  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x4e6f8  ldarg.1
0x4e6f9  callvirt instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x4e6fe  ldc.i4.1
0x4e6ff  conv.i8
0x4e700  ldarg.1
0x4e701  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x4e706  ldarg.0
0x4e707  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4e70c  ldarg.1
0x4e70d  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x4e712  ldarg.1
0x4e713  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e718  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x4e71d  ldarg.0
0x4e71e  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x4e723  brfalse.s loc_4E75B
0x4e725  ldarg.0
0x4e726  call     instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x4e72b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e730  ldarg.1
0x4e731  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e736  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4e73b  brfalse.s loc_4E75B
0x4e73d  ldarg.0
0x4e73e  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e743  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e748  ldarg.1
0x4e749  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e74e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e753  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4e758  brfalse.s loc_4E75B
0x4e75a  ret
0x4e75b  ldarg.1
0x4e75c  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::get_IsKeyword()
0x4e761  brfalse.s loc_4E773
0x4e763  ldstr    aErrorhierarchy// "ErrorHierarchyNotAllowedInKeywordTermSe"...
0x4e768  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4e76d  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4e772  throw
0x4e773  ldarg.1
0x4e774  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e779  brtrue.s loc_4E790
0x4e77b  ldstr    aErrorinvalidob// "ErrorInvalidObject"
0x4e780  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4e785  ldstr    aNewparenttermT// "newParentTerm.TermSet"
0x4e78a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x4e78f  throw
0x4e790  ldarg.0
0x4e791  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Term::get_ReusedPinnedTerms()
0x4e796  stloc.0
0x4e797  ldarg.1
0x4e798  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e79d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e7a2  ldarg.0
0x4e7a3  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e7a8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e7ad  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4e7b2  brfalse.s loc_4E7D2
0x4e7b4  ldarg.0
0x4e7b5  ldarg.1
0x4e7b6  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e7bb  call     instance bool Microsoft.SharePoint.Taxonomy.Term::ContainsReusedTerms(class Microsoft.SharePoint.Taxonomy.TermSet targetTermSet)
0x4e7c0  brfalse.s loc_4E80E
0x4e7c2  ldstr    aErrorcannotmov// "ErrorCannotMoveToReusedTermSet"
0x4e7c7  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4e7cc  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4e7d1  throw
0x4e7d2  ldarg.1
0x4e7d3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e7d8  ldarg.0
0x4e7d9  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4e7de  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4e7e3  brfalse.s loc_4E7F5
0x4e7e5  ldstr    aErrorcannotmov_0// "ErrorCannotMoveToTermSelf"
0x4e7ea  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4e7ef  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4e7f4  throw
0x4e7f5  ldarg.1
0x4e7f6  ldarg.0
0x4e7f7  callvirt instance bool Microsoft.SharePoint.Taxonomy.Term::GetIsDescendantOf(class Microsoft.SharePoint.Taxonomy.Term ancestorTerm)
0x4e7fc  brfalse.s loc_4E80E
0x4e7fe  ldstr    aErrorcannotmov_1// "ErrorCannotMoveToDescendentTerm"
0x4e803  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4e808  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4e80d  throw
0x4e80e  ldarg.0
0x4e80f  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4e814  stloc.1
0x4e815  ldarg.0
0x4e816  ldarg.0
0x4e817  call     instance class Microsoft.SharePoint.Taxonomy.TermSetItem Microsoft.SharePoint.Taxonomy.Term::get_ParentItem()
0x4e81c  ldarg.1
0x4e81d  call     instance void Microsoft.SharePoint.Taxonomy.Term::MoveTermInSandbox(class Microsoft.SharePoint.Taxonomy.TermSetItem sourceParent, class Microsoft.SharePoint.Taxonomy.TermSetItem targetParent)
0x4e822  ldarg.0
0x4e823  ldloc.0
0x4e824  ldloc.1
0x4e825  ldarg.1
0x4e826  call     instance void Microsoft.SharePoint.Taxonomy.Term::PinSyncMove(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term> pinnedTerms, class Microsoft.SharePoint.Taxonomy.TermSet sourceTermSet, class Microsoft.SharePoint.Taxonomy.Term newParentTerm)
0x4e82b  ldc.i4   0x32657678
0x4e830  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4e835  ldc.i4.s 0x64
0x4e837  ldstr    aEndTermMoveTer// "End: Term.Move(Term)"
0x4e83c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4e841  ret
```
