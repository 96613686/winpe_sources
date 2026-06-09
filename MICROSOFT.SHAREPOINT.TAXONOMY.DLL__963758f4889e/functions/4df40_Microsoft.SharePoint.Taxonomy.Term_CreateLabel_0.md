# Microsoft.SharePoint.Taxonomy.Term::CreateLabel_0

- ea: `0x4df40`
- end: `0x4dff9`
- name: `Microsoft.SharePoint.Taxonomy.Term::CreateLabel_0`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x4dd90`
- `0x4df30`

## callees

- `0x30f10`
- `0x48790`
- `0x48980`
- `0x48a60`
- `0x48ac0`
- `0x4aba0`
- `0x4d580`
- `0x4dab0`
- `0x4df40`
- `0x4f560`
- `0x4f680`
- `0x4f6a0`
- `0x4f740`
- `0x50680`
- `0x53690`
- `0x55440`
- `0x56720`

## string_xrefs

- `0x4df4c`: `Begin: Term.CreateLabel(string, int, bool, bool)`
- `0x4dfed`: `End: Term.CreateLabel(string, int, bool, bool)`

## pseudocode

```c

```

## disassembly

```asm
0x4df40  ldc.i4   0x3265766B
0x4df45  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4df4a  ldc.i4.s 0x64
0x4df4c  ldstr    aBeginTermCreat// "Begin: Term.CreateLabel(string, int, bo"...
0x4df51  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4df56  ldarg.0
0x4df57  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x4df5c  ldarg.0
0x4df5d  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsTermSet()
0x4df62  ldarg.0
0x4df63  call     instance void Microsoft.SharePoint.Taxonomy.Term::EnsureNotPinned()
0x4df68  ldarg.s  4
0x4df6a  brfalse.s loc_4DF77
0x4df6c  ldarg.0
0x4df6d  ldc.i4.1
0x4df6e  conv.i8
0x4df6f  ldc.i4.1
0x4df70  call     instance void Microsoft.SharePoint.Taxonomy.Term::BeginUpdate(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, bool checkPermissionsOnSourceTerm)
0x4df75  br.s     loc_4DF7D
0x4df77  ldarg.0
0x4df78  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginUpdateWithoutAclCheck()
0x4df7d  ldarg.1
0x4df7e  call     string Microsoft.SharePoint.Taxonomy.TaxonomyItem::NormalizeName(string name)
0x4df83  starg.s  1
0x4df85  ldarg.0
0x4df86  ldarg.1
0x4df87  ldstr    aLabelname// "labelName"
0x4df8c  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::ValidateName(string label, string parameterName)
0x4df91  ldarg.1
0x4df92  callvirt instance string [mscorlib]System.String::Trim()
0x4df97  starg.s  1
0x4df99  ldarg.0
0x4df9a  call     instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x4df9f  callvirt instance bool Microsoft.SharePoint.Taxonomy.TermSet::get_IsHashTagsTermSet()
0x4dfa4  brfalse.s loc_4DFB3
0x4dfa6  ldarg.0
0x4dfa7  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4dfac  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x4dfb1  starg.s  2
0x4dfb3  ldarg.0
0x4dfb4  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x4dfb9  ldarg.2
0x4dfba  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::ValidateLanguage(int32 lcid)
0x4dfbf  ldarg.0
0x4dfc0  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x4dfc5  ldarg.1
0x4dfc6  ldarg.2
0x4dfc7  ldarg.3
0x4dfc8  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::CreateLabel(string labelName, int32 lcid, bool isDefault)
0x4dfcd  ldarg.0
0x4dfce  ldarg.2
0x4dfcf  ldarg.1
0x4dfd0  ldarg.3
0x4dfd1  newobj   instance void Microsoft.SharePoint.Taxonomy.Label::.ctor(class Microsoft.SharePoint.Taxonomy.Term term, int32 lcid, string value, bool isDefaultLabel)
0x4dfd6  stloc.0
0x4dfd7  ldarg.3
0x4dfd8  brfalse.s loc_4DFE1
0x4dfda  ldarg.0
0x4dfdb  ldarg.2
0x4dfdc  call     instance void Microsoft.SharePoint.Taxonomy.Term::ClearCachedSortOrder(int32 lcid)
0x4dfe1  ldc.i4   0x3265766C
0x4dfe6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4dfeb  ldc.i4.s 0x64
0x4dfed  ldstr    aEndTermCreatel// "End: Term.CreateLabel(string, int, bool"...
0x4dff2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4dff7  ldloc.0
0x4dff8  ret
```
