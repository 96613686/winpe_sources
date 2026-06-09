# Microsoft.SharePoint.Taxonomy.TermSet::get_IsOpenForTermCreation

- ea: `0x52f00`
- end: `0x52f40`
- name: `Microsoft.SharePoint.Taxonomy.TermSet::get_IsOpenForTermCreation`
- size: `64`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2c40`
- `0x6e60`
- `0x96c0`
- `0x15520`
- `0x58ab0`
- `0x60e30`
- `0x69c00`
- `0x706e0`
- `0x708e0`

## callees

- `0x332a0`
- `0x48a60`
- `0x4db80`

## string_xrefs

- `0x52f0c`: `Begin: get TermSet.IsOpenForTermCreation`
- `0x52f34`: `End: get TermSet.IsOpenForTermCreation`

## pseudocode

```c

```

## disassembly

```asm
0x52f00  ldc.i4   0x32657870
0x52f05  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x52f0a  ldc.i4.s 0x64
0x52f0c  ldstr    aBeginGetTermse_2// "Begin: get TermSet.IsOpenForTermCreatio"...
0x52f11  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x52f16  ldarg.0
0x52f17  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x52f1c  ldarg.0
0x52f1d  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x52f22  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_IsOpen()
0x52f27  stloc.0
0x52f28  ldc.i4   0x32657871
0x52f2d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x52f32  ldc.i4.s 0x64
0x52f34  ldstr    aEndGetTermsetI_0// "End: get TermSet.IsOpenForTermCreation"
0x52f39  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x52f3e  ldloc.0
0x52f3f  ret
```
