# Microsoft.SharePoint.Taxonomy.Group::Delete

- ea: `0x48ee0`
- end: `0x48fb0`
- name: `Microsoft.SharePoint.Taxonomy.Group::Delete`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callees

- `0x2acd0`
- `0x2b0a0`
- `0x2dc00`
- `0x2ebf0`
- `0x33780`
- `0x33870`
- `0x488b0`
- `0x489e0`
- `0x48a60`
- `0x48ac0`
- `0x48ee0`
- `0x497b0`
- `0x499c0`
- `0x49d10`
- `0x55e70`
- `0x56c30`
- `0x56c80`
- `0x579b0`

## string_xrefs

- `0x48eec`: `Begin: Group.Delete()`
- `0x48f32`: `ErrorGroupMustBeEmptyForDelete`
- `0x48f4a`: `ErrorCannotDeleteSystemGroup`
- `0x48fa5`: `End: Group.Delete()`

## pseudocode

```c

```

## disassembly

```asm
0x48ee0  ldc.i4   0x32657534
0x48ee5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48eea  ldc.i4.s 0x64
0x48eec  ldstr    aBeginGroupDele// "Begin: Group.Delete()"
0x48ef1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x48ef6  ldarg.0
0x48ef7  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x48efc  ldc.i4.s 0x10
0x48efe  conv.i8
0x48eff  ldarg.0
0x48f00  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48f05  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x48f0a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_Acl()
0x48f0f  ldarg.0
0x48f10  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48f15  ldarg.0
0x48f16  ldnull
0x48f17  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x48f1c  ldarg.0
0x48f1d  ldc.i4.0
0x48f1e  conv.i8
0x48f1f  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginDelete(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions)
0x48f24  ldarg.0
0x48f25  call     instance class Microsoft.SharePoint.Taxonomy.TermSetCollection Microsoft.SharePoint.Taxonomy.Group::get_TermSets()
0x48f2a  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermSet>::get_Count()
0x48f2f  ldc.i4.0
0x48f30  ble.s    loc_48F42
0x48f32  ldstr    aErrorgroupmust// "ErrorGroupMustBeEmptyForDelete"
0x48f37  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x48f3c  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x48f41  throw
0x48f42  ldarg.0
0x48f43  call     instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsSystemGroup()
0x48f48  brfalse.s loc_48F5A
0x48f4a  ldstr    aErrorcannotdel// "ErrorCannotDeleteSystemGroup"
0x48f4f  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x48f54  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x48f59  throw
0x48f5a  ldarg.0
0x48f5b  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48f60  stloc.0
0x48f61  ldloc.0
0x48f62  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::BeginMembershipUpdate()
0x48f67  ldloc.0
0x48f68  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x48f6d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_GroupIds()
0x48f72  ldarg.0
0x48f73  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x48f78  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x48f7d  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Remove(var<u1>)
0x48f82  pop
0x48f83  ldarg.0
0x48f84  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48f89  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x48f8e  ldarg.0
0x48f8f  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x48f94  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x48f99  ldc.i4   0x32657535
0x48f9e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48fa3  ldc.i4.s 0x64
0x48fa5  ldstr    aEndGroupDelete// "End: Group.Delete()"
0x48faa  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x48faf  ret
```
