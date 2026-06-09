# Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::GetValidationErrorOrNull

- ea: `0x3dc0`
- end: `0x3e7f`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::GetValidationErrorOrNull`
- size: `191`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x3a70`
- `0x3ab0`
- `0x3b30`

## callees

- `0x39b0`
- `0x39d0`
- `0x39f0`
- `0x3a10`
- `0x3a30`
- `0x3a50`
- `0x3dc0`
- `0x2acd0`
- `0x4d510`
- `0x4f560`

## string_xrefs

- `0x3dcb`: `TaxonomyItemPickerNoSelection`
- `0x3e23`: `TaxonomyItemPickerDisallowedSelection`
- `0x3e55`: `TaxonomyItemPickerNotAvailableForTagging`
- `0x3e72`: `TaxonomyItemPickerNotAvailableForTagging`

## pseudocode

```c

```

## disassembly

```asm
0x3dc0  ldarg.0
0x3dc1  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::get_RequireSelection()
0x3dc6  brfalse.s loc_3DD6
0x3dc8  ldarg.1
0x3dc9  brtrue.s loc_3DD6
0x3dcb  ldstr    aTaxonomyitempi_0// "TaxonomyItemPickerNoSelection"
0x3dd0  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3dd5  ret
0x3dd6  ldc.i4.0
0x3dd7  stloc.0
0x3dd8  ldarg.0
0x3dd9  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::get_AllowSelectTermStore()
0x3dde  brtrue.s loc_3DEA
0x3de0  ldarg.1
0x3de1  isinst   Microsoft.SharePoint.Taxonomy.TermStore
0x3de6  ldnull
0x3de7  cgt.un
0x3de9  stloc.0
0x3dea  ldarg.0
0x3deb  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::get_AllowSelectGroup()
0x3df0  brtrue.s loc_3DFC
0x3df2  ldarg.1
0x3df3  isinst   Microsoft.SharePoint.Taxonomy.Group
0x3df8  ldnull
0x3df9  cgt.un
0x3dfb  stloc.0
0x3dfc  ldarg.0
0x3dfd  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::get_AllowSelectTermSet()
0x3e02  brtrue.s loc_3E0E
0x3e04  ldarg.1
0x3e05  isinst   Microsoft.SharePoint.Taxonomy.TermSet
0x3e0a  ldnull
0x3e0b  cgt.un
0x3e0d  stloc.0
0x3e0e  ldarg.0
0x3e0f  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::get_AllowSelectTerm()
0x3e14  brtrue.s loc_3E20
0x3e16  ldarg.1
0x3e17  isinst   Microsoft.SharePoint.Taxonomy.Term
0x3e1c  ldnull
0x3e1d  cgt.un
0x3e1f  stloc.0
0x3e20  ldloc.0
0x3e21  brfalse.s loc_3E2E
0x3e23  ldstr    aTaxonomyitempi_1// "TaxonomyItemPickerDisallowedSelection"
0x3e28  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3e2d  ret
0x3e2e  ldarg.0
0x3e2f  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::get_RequireAvailableForTagging()
0x3e34  brfalse.s loc_3E7D
0x3e36  ldarg.1
0x3e37  isinst   Microsoft.SharePoint.Taxonomy.Term
0x3e3c  stloc.1
0x3e3d  ldloc.1
0x3e3e  brfalse.s loc_3E60
0x3e40  ldloc.1
0x3e41  callvirt instance bool Microsoft.SharePoint.Taxonomy.TermSetItem::get_IsAvailableForTagging()
0x3e46  brfalse.s loc_3E55
0x3e48  ldloc.1
0x3e49  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x3e4e  callvirt instance bool Microsoft.SharePoint.Taxonomy.TermSetItem::get_IsAvailableForTagging()
0x3e53  brtrue.s loc_3E7D
0x3e55  ldstr    aTaxonomyitempi_2// "TaxonomyItemPickerNotAvailableForTaggin"...
0x3e5a  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3e5f  ret
0x3e60  ldarg.1
0x3e61  isinst   Microsoft.SharePoint.Taxonomy.TermSet
0x3e66  stloc.2
0x3e67  ldloc.2
0x3e68  brfalse.s loc_3E7D
0x3e6a  ldloc.2
0x3e6b  callvirt instance bool Microsoft.SharePoint.Taxonomy.TermSetItem::get_IsAvailableForTagging()
0x3e70  brtrue.s loc_3E7D
0x3e72  ldstr    aTaxonomyitempi_2// "TaxonomyItemPickerNotAvailableForTaggin"...
0x3e77  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3e7c  ret
0x3e7d  ldnull
0x3e7e  ret
```
