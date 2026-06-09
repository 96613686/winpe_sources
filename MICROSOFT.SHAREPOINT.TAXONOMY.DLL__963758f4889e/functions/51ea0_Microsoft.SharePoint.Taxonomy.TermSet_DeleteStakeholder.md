# Microsoft.SharePoint.Taxonomy.TermSet::DeleteStakeholder

- ea: `0x51ea0`
- end: `0x51efe`
- name: `Microsoft.SharePoint.Taxonomy.TermSet::DeleteStakeholder`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x5e70`
- `0x8900`
- `0x60e30`

## callees

- `0x2acd0`
- `0x32df0`
- `0x48950`
- `0x48a60`
- `0x4db80`
- `0x51ea0`

## string_xrefs

- `0x51eac`: `Begin: TermSet.DeleteStakeholder(string)`
- `0x51ef3`: `End: TermSet.DeleteStakeholder(string)`

## pseudocode

```c

```

## disassembly

```asm
0x51ea0  ldc.i4   0x3265776C
0x51ea5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x51eaa  ldc.i4.s 0x64
0x51eac  ldstr    aBeginTermsetDe_2// "Begin: TermSet.DeleteStakeholder(string"...
0x51eb1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x51eb6  ldarg.0
0x51eb7  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x51ebc  ldarg.0
0x51ebd  ldc.i4.2
0x51ebe  conv.i8
0x51ebf  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::BeginUpdate(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions)
0x51ec4  ldarg.0
0x51ec5  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x51eca  ldarg.1
0x51ecb  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::DeleteStakeholder(string stakeholderName)
0x51ed0  brtrue.s loc_51EE7
0x51ed2  ldstr    aErrorunknownst// "ErrorUnknownStakeholderName"
0x51ed7  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x51edc  ldstr    aStakeholdernam// "stakeholderName"
0x51ee1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x51ee6  throw
0x51ee7  ldc.i4   0x3265776D
0x51eec  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x51ef1  ldc.i4.s 0x64
0x51ef3  ldstr    aEndTermsetDele_2// "End: TermSet.DeleteStakeholder(string)"
0x51ef8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x51efd  ret
```
