# Microsoft.SharePoint.Taxonomy.TermSet::set_IsOpenForTermCreation

- ea: `0x52f40`
- end: `0x52fab`
- name: `Microsoft.SharePoint.Taxonomy.TermSet::set_IsOpenForTermCreation`
- size: `107`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x6e60`
- `0x96c0`
- `0x60e30`
- `0x6d360`

## callees

- `0x2acd0`
- `0x332b0`
- `0x333a0`
- `0x48950`
- `0x48a60`
- `0x4dad0`
- `0x4db80`
- `0x52f40`
- `0x579b0`

## string_xrefs

- `0x52f4c`: `Begin: set TermSet.IsOpenForTermCreation`
- `0x52fa0`: `End: set TermSet.IsOpenForTermCreation`

## pseudocode

```c

```

## disassembly

```asm
0x52f40  ldc.i4   0x32657872
0x52f45  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x52f4a  ldc.i4.s 0x64
0x52f4c  ldstr    aBeginSetTermse_1// "Begin: set TermSet.IsOpenForTermCreatio"...
0x52f51  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x52f56  ldarg.0
0x52f57  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x52f5c  ldarg.0
0x52f5d  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsOrHashTagsTermSet()
0x52f62  ldarg.0
0x52f63  ldc.i4.2
0x52f64  conv.i8
0x52f65  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginUpdate(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions)
0x52f6a  ldarg.0
0x52f6b  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x52f70  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_Type()
0x52f75  ldc.i4.2
0x52f76  bne.un.s loc_52F88
0x52f78  ldstr    aErrormodifyorp// "ErrorModifyOrphanedTermSet"
0x52f7d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x52f82  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x52f87  throw
0x52f88  ldarg.0
0x52f89  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x52f8e  ldarg.1
0x52f8f  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::set_IsOpen(bool value)
0x52f94  ldc.i4   0x32657873
0x52f99  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x52f9e  ldc.i4.s 0x64
0x52fa0  ldstr    aEndSetTermsetI_0// "End: set TermSet.IsOpenForTermCreation"
0x52fa5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x52faa  ret
```
