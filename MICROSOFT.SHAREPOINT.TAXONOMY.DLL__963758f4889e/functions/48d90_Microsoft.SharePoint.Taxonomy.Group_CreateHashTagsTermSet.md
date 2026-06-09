# Microsoft.SharePoint.Taxonomy.Group::CreateHashTagsTermSet

- ea: `0x48d90`
- end: `0x48e47`
- name: `Microsoft.SharePoint.Taxonomy.Group::CreateHashTagsTermSet`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x557a0`

## callees

- `0x2acd0`
- `0x2b0a0`
- `0x2ebf0`
- `0x33250`
- `0x33290`
- `0x332b0`
- `0x489e0`
- `0x48a60`
- `0x48ac0`
- `0x49d10`
- `0x4db80`
- `0x51b40`
- `0x53f80`
- `0x55440`
- `0x56c30`

## string_xrefs

- `0x48d9c`: `Begin: Group.CreateHashTagsTermSet()`
- `0x48e3b`: `End: Group.CreateHashTagsTermSet()`

## pseudocode

```c

```

## disassembly

```asm
0x48d90  ldc.i4   0x25C846
0x48d95  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48d9a  ldc.i4.s 0x64
0x48d9c  ldstr    aBeginGroupCrea_0// "Begin: Group.CreateHashTagsTermSet()"
0x48da1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x48da6  ldarg.0
0x48da7  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x48dac  ldstr    aHashtagstermse// "HashtagsTermSetName"
0x48db1  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x48db6  stloc.0
0x48db7  ldstr    aHashtagstermse_0// "HashtagsTermSetDescription"
0x48dbc  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x48dc1  stloc.1
0x48dc2  ldloc.0
0x48dc3  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::HashTagsTermSetId
0x48dc8  ldarg.0
0x48dc9  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x48dce  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x48dd3  ldarg.0
0x48dd4  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48dd9  ldarg.0
0x48dda  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48ddf  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x48de4  call     class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermSet::CreateTermSetInSandbox(string name, valuetype [mscorlib]System.Guid newTermSetId, int32 groupId, class Microsoft.SharePoint.Taxonomy.TermStore termStore, int32 lcid)
0x48de9  stloc.2
0x48dea  ldloc.2
0x48deb  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x48df0  ldc.i4.1
0x48df1  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::set_IsAvailableForTagging(bool value)
0x48df6  ldloc.2
0x48df7  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x48dfc  ldc.i4.1
0x48dfd  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::set_IsOpen(bool value)
0x48e02  ldloc.2
0x48e03  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x48e08  ldloc.1
0x48e09  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::set_Description(string value)
0x48e0e  ldarg.0
0x48e0f  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48e14  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x48e19  ldloc.2
0x48e1a  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x48e1f  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x48e24  ldarg.0
0x48e25  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48e2a  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x48e2f  ldc.i4   0x25C847
0x48e34  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48e39  ldc.i4.s 0x64
0x48e3b  ldstr    aEndGroupCreate_0// "End: Group.CreateHashTagsTermSet()"
0x48e40  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x48e45  ldloc.2
0x48e46  ret
```
