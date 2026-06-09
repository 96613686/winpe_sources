# Microsoft.SharePoint.Taxonomy.Group::TryAddSiteCollectionIdsIfEmpty

- ea: `0x49a20`
- end: `0x49ac6`
- name: `Microsoft.SharePoint.Taxonomy.Group::TryAddSiteCollectionIdsIfEmpty`
- size: `166`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x49160`
- `0x55930`
- `0x56080`

## callees

- `0x2f1c0`
- `0x487f0`
- `0x48ac0`
- `0x49a20`
- `0x49b60`
- `0x49d10`
- `0x53f80`

## string_xrefs

- `0x49a59`: `Added site collection ID {0) to have access to local site collection group {1}`
- `0x49a91`: `Failed to update SiteCollection group to have SiteCollection ID, for group {0} and SiteCollection ID {1}.  Error was {2}`

## pseudocode

```c

```

## disassembly

```asm
0x49a20  ldarg.0
0x49a21  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x49a26  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_SiteCollectionIds()
0x49a2b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x49a30  brtrue   loc_49AC5
0x49a35  ldarg.0
0x49a36  ldarg.1
0x49a37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x49a3c  ldc.i4.0
0x49a3d  call     instance void Microsoft.SharePoint.Taxonomy.Group::AddSiteCollectionToGroup(valuetype [mscorlib]System.Guid siteId, bool checkAccess)
0x49a42  ldarg.0
0x49a43  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x49a48  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x49a4d  ldc.i4   0x67716536
0x49a52  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x49a57  ldc.i4.s 0x64
0x49a59  ldstr    aAddedSiteColle// "Added site collection ID {0) to have ac"...
0x49a5e  ldc.i4.2
0x49a5f  newarr   [mscorlib]System.Object
0x49a64  stloc.1
0x49a65  ldloc.1
0x49a66  ldc.i4.0
0x49a67  ldarg.1
0x49a68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x49a6d  box      [mscorlib]System.Guid
0x49a72  stelem.ref
0x49a73  ldloc.1
0x49a74  ldc.i4.1
0x49a75  ldarg.0
0x49a76  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x49a7b  stelem.ref
0x49a7c  ldloc.1
0x49a7d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x49a82  leave.s  loc_49AC5
0x49a84  stloc.0
0x49a85  ldc.i4   0x67716537
0x49a8a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x49a8f  ldc.i4.s 0xA
0x49a91  ldstr    aFailedToUpdate// "Failed to update SiteCollection group t"...
0x49a96  ldc.i4.3
0x49a97  newarr   [mscorlib]System.Object
0x49a9c  stloc.2
0x49a9d  ldloc.2
0x49a9e  ldc.i4.0
0x49a9f  ldarg.0
0x49aa0  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x49aa5  stelem.ref
0x49aa6  ldloc.2
0x49aa7  ldc.i4.1
0x49aa8  ldarg.1
0x49aa9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x49aae  box      [mscorlib]System.Guid
0x49ab3  stelem.ref
0x49ab4  ldloc.2
0x49ab5  ldc.i4.2
0x49ab6  ldloc.0
0x49ab7  callvirt instance string [mscorlib]System.Object::ToString()
0x49abc  stelem.ref
0x49abd  ldloc.2
0x49abe  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x49ac3  leave.s  loc_49AC5
0x49ac5  ret
```
