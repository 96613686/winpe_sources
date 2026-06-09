# Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm

- ea: `0x4d000`
- end: `0x4d18c`
- name: `Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm`
- size: `396`
- prototype: ``
- caller_count: `3`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x4d190`
- `0x61650`
- `0x61ec0`

## callees

- `0x2acd0`
- `0x2b0a0`
- `0x2dbe0`
- `0x33220`
- `0x332a0`
- `0x333a0`
- `0x48790`
- `0x48810`
- `0x48830`
- `0x48840`
- `0x489e0`
- `0x48a00`
- `0x48a60`
- `0x48ac0`
- `0x4cf20`
- `0x4d000`
- `0x4d580`
- `0x4dab0`
- `0x4db80`
- `0x4dd90`
- `0x4f560`
- `0x4f6a0`
- `0x4f710`
- `0x50680`
- `0x52e10`
- `0x55440`
- `0x56720`
- `0x56a20`
- `0x56c30`
- `0x56e70`
- `0x579b0`

## string_xrefs

- `0x4d00c`: `Begin: TermSetItem.CreateTerm(string, int, string)`
- `0x4d180`: `End: TermSetItem.CreateTerm(string, int, string)`

## pseudocode

```c

```

## disassembly

```asm
0x4d000  ldc.i4   0x32657937
0x4d005  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4d00a  ldc.i4.s 0x64
0x4d00c  ldstr    aBeginTermsetit// "Begin: TermSetItem.CreateTerm(string, i"...
0x4d011  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4d016  ldarg.0
0x4d017  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x4d01c  ldarg.0
0x4d01d  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsTermSet()
0x4d022  ldarg.0
0x4d023  isinst   Microsoft.SharePoint.Taxonomy.Term
0x4d028  brfalse.s loc_4D035
0x4d02a  ldarg.0
0x4d02b  castclass Microsoft.SharePoint.Taxonomy.Term
0x4d030  call     instance void Microsoft.SharePoint.Taxonomy.Term::EnsureNotPinned()
0x4d035  ldarg.0
0x4d036  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x4d03b  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_IsOpen()
0x4d040  brtrue.s loc_4D0AE
0x4d042  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4d047  stloc.0
0x4d048  ldarg.0
0x4d049  isinst   Microsoft.SharePoint.Taxonomy.Term
0x4d04e  brfalse.s loc_4D068
0x4d050  ldarg.0
0x4d051  isinst   Microsoft.SharePoint.Taxonomy.Term
0x4d056  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4d05b  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermSet::get_Group()
0x4d060  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4d065  stloc.0
0x4d066  br.s     loc_4D081
0x4d068  ldarg.0
0x4d069  isinst   Microsoft.SharePoint.Taxonomy.TermSet
0x4d06e  brfalse.s loc_4D081
0x4d070  ldarg.0
0x4d071  isinst   Microsoft.SharePoint.Taxonomy.TermSet
0x4d076  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermSet::get_Group()
0x4d07b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4d080  stloc.0
0x4d081  ldarg.0
0x4d082  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4d087  ldarg.0
0x4d088  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Acl()
0x4d08d  ldloc.0
0x4d08e  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights Microsoft.SharePoint.Taxonomy.TermStore::GetEffectiveRights(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, valuetype [mscorlib]System.Guid groupId)
0x4d093  stloc.1
0x4d094  ldc.i4.1
0x4d095  conv.i8
0x4d096  ldloc.1
0x4d097  ldarg.0
0x4d098  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4d09d  ldarg.0
0x4d09e  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x4d0a3  ldarg.0
0x4d0a4  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetAssociatedTermSet()
0x4d0a9  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights effectiveRights, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x4d0ae  ldarg.0
0x4d0af  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x4d0b4  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_Type()
0x4d0b9  ldc.i4.1
0x4d0ba  beq.s    loc_4D0C9
0x4d0bc  ldarg.0
0x4d0bd  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x4d0c2  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_IsHashTagsTermSet()
0x4d0c7  brfalse.s loc_4D0EE
0x4d0c9  ldarg.0
0x4d0ca  isinst   Microsoft.SharePoint.Taxonomy.Term
0x4d0cf  brfalse.s loc_4D0E1
0x4d0d1  ldstr    aErrorhierarchy// "ErrorHierarchyNotAllowedInKeywordTermSe"...
0x4d0d6  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x4d0db  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x4d0e0  throw
0x4d0e1  ldarg.0
0x4d0e2  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4d0e7  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x4d0ec  starg.s  2
0x4d0ee  ldarg.1
0x4d0ef  call     string Microsoft.SharePoint.Taxonomy.TaxonomyItem::NormalizeName(string name)
0x4d0f4  starg.s  1
0x4d0f6  ldarg.0
0x4d0f7  ldarg.1
0x4d0f8  ldstr    aName_1// "name"
0x4d0fd  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::ValidateName(string label, string parameterName)
0x4d102  ldarg.1
0x4d103  callvirt instance string [mscorlib]System.String::Trim()
0x4d108  starg.s  1
0x4d10a  ldarg.0
0x4d10b  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4d110  ldarg.2
0x4d111  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::ValidateLanguage(int32 lcid)
0x4d116  ldnull
0x4d117  stloc.2
0x4d118  ldarg.0
0x4d119  isinst   Microsoft.SharePoint.Taxonomy.Term
0x4d11e  brfalse.s loc_4D12C
0x4d120  ldarg.0
0x4d121  isinst   Microsoft.SharePoint.Taxonomy.Term
0x4d126  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x4d12b  stloc.2
0x4d12c  ldarg.1
0x4d12d  ldarg.2
0x4d12e  ldarg.3
0x4d12f  ldarg.0
0x4d130  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x4d135  ldloc.2
0x4d136  ldarg.0
0x4d137  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4d13c  call     class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::CreateTermInSandbox(string name, int32 lcid, valuetype [mscorlib]System.Guid newTermId, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet parentSharedTermSet, class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm parentSharedTerm, class Microsoft.SharePoint.Taxonomy.TermStore termStore)
0x4d141  stloc.3
0x4d142  ldloc.3
0x4d143  ldarg.0
0x4d144  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4d149  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x4d14e  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomySession::get_CurrentUserName()
0x4d153  ldstr    aOwner// "owner"
0x4d158  ldc.i4.0
0x4d159  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::SetOwnerWithoutPermissionCheck(string ownerName, string parameterName, bool doValidateOwnerName)
0x4d15e  ldarg.0
0x4d15f  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4d164  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x4d169  ldloc.3
0x4d16a  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x4d16f  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x4d174  ldc.i4   0x32657938
0x4d179  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4d17e  ldc.i4.s 0x64
0x4d180  ldstr    aEndTermsetitem// "End: TermSetItem.CreateTerm(string, int"...
0x4d185  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4d18a  ldloc.3
0x4d18b  ret
```
