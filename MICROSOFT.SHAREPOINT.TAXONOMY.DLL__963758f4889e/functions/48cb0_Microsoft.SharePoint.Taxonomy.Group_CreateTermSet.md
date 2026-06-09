# Microsoft.SharePoint.Taxonomy.Group::CreateTermSet

- ea: `0x48cb0`
- end: `0x48d84`
- name: `Microsoft.SharePoint.Taxonomy.Group::CreateTermSet`
- size: `212`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x48e90`
- `0x48eb0`
- `0x48ec0`

## callees

- `0x25740`
- `0x2acd0`
- `0x2b0a0`
- `0x2dc00`
- `0x2ebf0`
- `0x48790`
- `0x48830`
- `0x489e0`
- `0x48a60`
- `0x48ac0`
- `0x48cb0`
- `0x497b0`
- `0x49d10`
- `0x4cf20`
- `0x51b40`
- `0x53610`
- `0x56720`
- `0x56c30`
- `0x56e70`
- `0x579b0`

## string_xrefs

- `0x48cbc`: `Begin: Group.CreateTermSet(string, Guid, int)`
- `0x48cf5`: `ErrorCannotCreateTermSetInSystemGroup`
- `0x48d78`: `End: Group.CreateTermSet(string, Guid, int)`

## pseudocode

```c

```

## disassembly

```asm
0x48cb0  ldc.i4   0x32657532
0x48cb5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48cba  ldc.i4.s 0x64
0x48cbc  ldstr    aBeginGroupCrea// "Begin: Group.CreateTermSet(string, Guid"...
0x48cc1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x48cc6  ldarg.0
0x48cc7  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x48ccc  ldc.i4.2
0x48ccd  conv.i8
0x48cce  ldarg.0
0x48ccf  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x48cd4  ldarg.0
0x48cd5  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48cda  ldarg.0
0x48cdb  ldnull
0x48cdc  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x48ce1  ldarg.0
0x48ce2  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48ce7  ldarg.3
0x48ce8  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::ValidateLanguage(int32 lcid)
0x48ced  ldarg.0
0x48cee  call     instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsSystemGroup()
0x48cf3  brfalse.s loc_48D05
0x48cf5  ldstr    aErrorcannotcre// "ErrorCannotCreateTermSetInSystemGroup"
0x48cfa  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x48cff  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x48d04  throw
0x48d05  ldarg.1
0x48d06  call     string Microsoft.SharePoint.Taxonomy.TaxonomyItem::NormalizeName(string name)
0x48d0b  starg.s  1
0x48d0d  ldarg.1
0x48d0e  ldstr    aName_1// "name"
0x48d13  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::ValidateName(string name, string parameterName)
0x48d18  ldarg.1
0x48d19  callvirt instance string [mscorlib]System.String::Trim()
0x48d1e  starg.s  1
0x48d20  ldarg.1
0x48d21  ldarg.2
0x48d22  ldarg.0
0x48d23  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x48d28  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x48d2d  ldarg.0
0x48d2e  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48d33  ldarg.3
0x48d34  call     class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermSet::CreateTermSetInSandbox(string name, valuetype [mscorlib]System.Guid newTermSetId, int32 groupId, class Microsoft.SharePoint.Taxonomy.TermStore termStore, int32 lcid)
0x48d39  stloc.0
0x48d3a  ldloc.0
0x48d3b  ldarg.0
0x48d3c  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48d41  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x48d46  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomySession::get_CurrentUserName()
0x48d4b  ldstr    aOwner_0// "Owner"
0x48d50  ldc.i4.0
0x48d51  callvirt instance void Microsoft.SharePoint.Taxonomy.TermSet::SetOwnerWithoutPermissionCheck(string ownerName, string parameterName, bool doValidateOwnerName)
0x48d56  ldarg.0
0x48d57  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x48d5c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x48d61  ldloc.0
0x48d62  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x48d67  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x48d6c  ldc.i4   0x32657533
0x48d71  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x48d76  ldc.i4.s 0x64
0x48d78  ldstr    aEndGroupCreate// "End: Group.CreateTermSet(string, Guid, "...
0x48d7d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x48d82  ldloc.0
0x48d83  ret
```
