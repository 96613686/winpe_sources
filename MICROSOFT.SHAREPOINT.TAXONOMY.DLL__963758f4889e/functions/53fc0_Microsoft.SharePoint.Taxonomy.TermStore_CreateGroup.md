# Microsoft.SharePoint.Taxonomy.TermStore::CreateGroup

- ea: `0x53fc0`
- end: `0x54088`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::CreateGroup`
- size: `200`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x54090`
- `0x540a0`
- `0x540c0`

## callees

- `0x25740`
- `0x2acd0`
- `0x2b0a0`
- `0x2dc10`
- `0x33780`
- `0x48790`
- `0x487f0`
- `0x489e0`
- `0x48ba0`
- `0x53fc0`
- `0x55630`
- `0x56c30`
- `0x56c80`

## string_xrefs

- `0x53fcc`: `Begin: TermStore.CreateGroup(string)`
- `0x5407c`: `End: TermStore.CreateGroup(string)`

## pseudocode

```c

```

## disassembly

```asm
0x53fc0  ldc.i4   0x3778736C
0x53fc5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x53fca  ldc.i4.s 0x64
0x53fcc  ldstr    aBeginTermstore_1// "Begin: TermStore.CreateGroup(string)"
0x53fd1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x53fd6  ldc.i4.s 0x10
0x53fd8  conv.i8
0x53fd9  ldarg.0
0x53fda  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.TermStore::get_SharedTermStore()
0x53fdf  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_Acl()
0x53fe4  ldarg.0
0x53fe5  ldnull
0x53fe6  ldnull
0x53fe7  ldc.i4.2
0x53fe8  ldarg.2
0x53fe9  ceq
0x53feb  ldarg.3
0x53fec  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::CheckPermissions(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class Microsoft.SharePoint.Taxonomy.Group group, class Microsoft.SharePoint.Taxonomy.TermSet termSet, bool isSiteCollectionGroupCreate, class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite siteCollectionForGroup)
0x53ff1  ldarg.1
0x53ff2  call     string Microsoft.SharePoint.Taxonomy.TaxonomyItem::NormalizeName(string name)
0x53ff7  starg.s  1
0x53ff9  ldarg.1
0x53ffa  ldstr    aName_1// "name"
0x53fff  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::ValidateName(string name, string parameterName)
0x54004  ldarg.1
0x54005  callvirt instance string [mscorlib]System.String::Trim()
0x5400a  starg.s  1
0x5400c  ldarg.0
0x5400d  call     instance class Microsoft.SharePoint.Taxonomy.GroupCollection Microsoft.SharePoint.Taxonomy.TermStore::get_Groups()
0x54012  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Group>::GetEnumerator()
0x54017  stloc.2
0x54018  br.s     loc_54040
0x5401a  ldloc.2
0x5401b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Group>::get_Current()
0x54020  stloc.0
0x54021  ldarg.1
0x54022  ldloc.0
0x54023  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x54028  ldc.i4.5
0x54029  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5402e  brfalse.s loc_54040
0x54030  ldstr    aErrorduplicate_2// "ErrorDuplicatedGroupName"
0x54035  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x5403a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x5403f  throw
0x54040  ldloc.2
0x54041  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x54046  brtrue.s loc_5401A
0x54048  leave.s  loc_54054
0x5404a  ldloc.2
0x5404b  brfalse.s loc_54053
0x5404d  ldloc.2
0x5404e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54053  endfinally
0x54054  ldarg.1
0x54055  ldarg.0
0x54056  ldarg.2
0x54057  ldarg.s  4
0x54059  call     class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.Group::CreateGroupInSandbox(string name, class Microsoft.SharePoint.Taxonomy.TermStore termStore, valuetype Microsoft.SharePoint.Taxonomy.Internal.GroupType type, valuetype [mscorlib]System.Guid groupId)
0x5405e  stloc.1
0x5405f  ldarg.0
0x54060  call     instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x54065  ldloc.1
0x54066  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem Microsoft.SharePoint.Taxonomy.TaxonomyItem::GetSandboxItem()
0x5406b  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem sandboxItem)
0x54070  ldc.i4   0x3778736D
0x54075  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5407a  ldc.i4.s 0x64
0x5407c  ldstr    aEndTermstoreCr// "End: TermStore.CreateGroup(string)"
0x54081  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x54086  ldloc.1
0x54087  ret
```
