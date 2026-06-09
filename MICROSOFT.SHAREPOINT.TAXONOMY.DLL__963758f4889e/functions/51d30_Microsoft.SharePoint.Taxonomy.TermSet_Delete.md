# Microsoft.SharePoint.Taxonomy.TermSet::Delete

- ea: `0x51d30`
- end: `0x51deb`
- name: `Microsoft.SharePoint.Taxonomy.TermSet::Delete`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callees

- `0x2acd0`
- `0x2b0a0`
- `0x2dc00`
- `0x2ebf0`
- `0x2f1a0`
- `0x333a0`
- `0x48830`
- `0x48840`
- `0x488e0`
- `0x48920`
- `0x489e0`
- `0x48a60`
- `0x48ac0`
- `0x49d10`
- `0x4d9e0`
- `0x4dad0`
- `0x4db80`
- `0x51d30`
- `0x52e10`
- `0x56c30`
- `0x579b0`

## string_xrefs

- `0x51d3c`: `Begin: TermSet.Delete()`
- `0x51d79`: `ErrorCannotDeleteSystemTermSet`
- `0x51de0`: `End: TermSet.Delete()`

## pseudocode

```c

```

## disassembly

```asm
0x51d30  ldc.i4   0x3265776A
0x51d35  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x51d3a  ldc.i4.s 0x64
0x51d3c  ldstr    aBeginTermsetDe// "Begin: TermSet.Delete()"
0x51d41  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x51d46  ldarg.0
0x51d47  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x51d4c  ldarg.0
0x51d4d  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x51d52  ldc.i4.2
0x51d53  conv.i8
0x51d54  ldarg.0
0x51d55  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x51d5a  ldarg.0
0x51d5b  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x51d60  ldarg.0
0x51d61  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x51d66  ldarg.0
0x51d67  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x51d6c  ldarg.0
0x51d6d  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x51d72  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_Type()
0x51d77  brfalse.s loc_51D89
0x51d79  ldstr    aErrorcannotdel_4// "ErrorCannotDeleteSystemTermSet"
0x51d7e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x51d83  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x51d88  throw
0x51d89  ldarg.0
0x51d8a  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::PrepareDescendentsForDelete()
0x51d8f  ldarg.0
0x51d90  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginDeleteWithoutAclCheck()
0x51d95  ldarg.0
0x51d96  call     instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermSet::get_Group()
0x51d9b  stloc.0
0x51d9c  ldloc.0
0x51d9d  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginMembershipUpdate()
0x51da2  ldloc.0
0x51da3  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x51da8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_TermSetIds()
0x51dad  ldarg.0
0x51dae  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x51db3  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x51db8  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Remove(var<u1>)
0x51dbd  pop
0x51dbe  ldarg.0
0x51dbf  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x51dc4  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x51dc9  ldarg.0
0x51dca  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x51dcf  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x51dd4  ldc.i4   0x3265776B
0x51dd9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x51dde  ldc.i4.s 0x64
0x51de0  ldstr    aEndTermsetDele// "End: TermSet.Delete()"
0x51de5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x51dea  ret
```
