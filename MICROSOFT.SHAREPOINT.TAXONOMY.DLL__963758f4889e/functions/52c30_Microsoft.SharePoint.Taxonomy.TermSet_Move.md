# Microsoft.SharePoint.Taxonomy.TermSet::Move

- ea: `0x52c30`
- end: `0x52d16`
- name: `Microsoft.SharePoint.Taxonomy.TermSet::Move`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x60b10`
- `0x6e3b0`

## callees

- `0x242a0`
- `0x2acd0`
- `0x2dc00`
- `0x2ebf0`
- `0x33260`
- `0x333a0`
- `0x48830`
- `0x48840`
- `0x48a60`
- `0x48ac0`
- `0x497b0`
- `0x49d10`
- `0x4dad0`
- `0x4db80`
- `0x52c30`
- `0x52e10`
- `0x53460`
- `0x579b0`

## string_xrefs

- `0x52c3c`: `Begin: TermSet.Move(Group)`
- `0x52cb1`: `ErrorCannotMoveSystemTermSet`
- `0x52ce2`: `ErrorCannotMoveToSystemGroup`
- `0x52d0b`: `End: TermSet.Move(Group)`

## pseudocode

```c

```

## disassembly

```asm
0x52c30  ldc.i4   0x32657862
0x52c35  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x52c3a  ldc.i4.s 0x64
0x52c3c  ldstr    aBeginTermsetMo// "Begin: TermSet.Move(Group)"
0x52c41  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x52c46  ldarg.1
0x52c47  ldstr    aTargetgroup// "targetGroup"
0x52c4c  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x52c51  ldarg.0
0x52c52  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x52c57  ldarg.0
0x52c58  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x52c5d  ldc.i4.2
0x52c5e  conv.i8
0x52c5f  ldarg.0
0x52c60  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x52c65  ldarg.0
0x52c66  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x52c6b  ldarg.0
0x52c6c  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x52c71  ldarg.0
0x52c72  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x52c77  ldc.i4.2
0x52c78  conv.i8
0x52c79  ldarg.1
0x52c7a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x52c7f  ldarg.0
0x52c80  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x52c85  ldarg.1
0x52c86  ldnull
0x52c87  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x52c8c  ldarg.1
0x52c8d  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x52c92  brtrue.s loc_52CA4
0x52c94  ldstr    aErrorinvalidob// "ErrorInvalidObject"
0x52c99  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x52c9e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x52ca3  throw
0x52ca4  ldarg.0
0x52ca5  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x52caa  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_Type()
0x52caf  brfalse.s loc_52CC1
0x52cb1  ldstr    aErrorcannotmov_2// "ErrorCannotMoveSystemTermSet"
0x52cb6  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x52cbb  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x52cc0  throw
0x52cc1  ldarg.1
0x52cc2  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x52cc7  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x52ccc  ldarg.0
0x52ccd  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x52cd2  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_GroupId()
0x52cd7  bne.un.s loc_52CDA
0x52cd9  ret
0x52cda  ldarg.1
0x52cdb  callvirt instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsSystemGroup()
0x52ce0  brfalse.s loc_52CF2
0x52ce2  ldstr    aErrorcannotmov_3// "ErrorCannotMoveToSystemGroup"
0x52ce7  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x52cec  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x52cf1  throw
0x52cf2  ldarg.0
0x52cf3  ldarg.0
0x52cf4  call     instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermSet::get_Group()
0x52cf9  ldarg.1
0x52cfa  call     instance void Microsoft.SharePoint.Taxonomy.TermSet::MoveTermSetInSandbox(class Microsoft.SharePoint.Taxonomy.Group sourceGroup, class Microsoft.SharePoint.Taxonomy.Group targetGroup)
0x52cff  ldc.i4   0x32657863
0x52d04  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x52d09  ldc.i4.s 0x64
0x52d0b  ldstr    aEndTermsetMove// "End: TermSet.Move(Group)"
0x52d10  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x52d15  ret
```
