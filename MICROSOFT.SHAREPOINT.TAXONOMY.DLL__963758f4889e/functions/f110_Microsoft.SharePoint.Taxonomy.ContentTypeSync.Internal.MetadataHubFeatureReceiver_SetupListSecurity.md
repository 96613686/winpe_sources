# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::SetupListSecurity

- ea: `0xf110`
- end: `0xf1d9`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::SetupListSecurity`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xee60`
- `0xef90`

## callees

- `0xf110`

## string_xrefs

- `0xf11c`: `Setting up list security for list {0}`
- `0xf195`: `Updated security for list {0}`
- `0xf1bd`: `No need to update security for list {0}`

## pseudocode

```c

```

## disassembly

```asm
0xf110  ldc.i4   0x637A6437
0xf115  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xf11a  ldc.i4.s 0x64
0xf11c  ldstr    aSettingUpListS// "Setting up list security for list {0}"
0xf121  ldc.i4.1
0xf122  newarr   [mscorlib]System.Object
0xf127  stloc.1
0xf128  ldloc.1
0xf129  ldc.i4.0
0xf12a  ldarg.0
0xf12b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Title()
0xf130  stelem.ref
0xf131  ldloc.1
0xf132  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xf137  ldc.i4.0
0xf138  stloc.0
0xf139  ldarg.0
0xf13a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurableObject::get_HasUniqueRoleAssignments()
0xf13f  brtrue.s loc_F14A
0xf141  ldarg.0
0xf142  ldc.i4.0
0xf143  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurableObject::BreakRoleInheritance(bool)
0xf148  ldc.i4.1
0xf149  stloc.0
0xf14a  ldarg.0
0xf14b  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_EnableFolderCreation()
0xf150  brfalse.s loc_F15B
0xf152  ldarg.0
0xf153  ldc.i4.0
0xf154  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_EnableFolderCreation(bool)
0xf159  ldc.i4.1
0xf15a  stloc.0
0xf15b  ldarg.0
0xf15c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_AllowEveryoneViewItems()
0xf161  brfalse.s loc_F16C
0xf163  ldarg.0
0xf164  ldc.i4.0
0xf165  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AllowEveryoneViewItems(bool)
0xf16a  ldc.i4.1
0xf16b  stloc.0
0xf16c  ldarg.0
0xf16d  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_AnonymousPermMask64()
0xf172  ldc.i4.0
0xf173  conv.i8
0xf174  beq.s    loc_F180
0xf176  ldarg.0
0xf177  ldc.i4.0
0xf178  conv.i8
0xf179  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AnonymousPermMask64(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions)
0xf17e  ldc.i4.1
0xf17f  stloc.0
0xf180  ldloc.0
0xf181  brfalse.s loc_F1B1
0xf183  ldarg.0
0xf184  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::Update()
0xf189  ldc.i4   0x637A6438
0xf18e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xf193  ldc.i4.s 0x64
0xf195  ldstr    aUpdatedSecurit// "Updated security for list {0}"
0xf19a  ldc.i4.1
0xf19b  newarr   [mscorlib]System.Object
0xf1a0  stloc.2
0xf1a1  ldloc.2
0xf1a2  ldc.i4.0
0xf1a3  ldarg.0
0xf1a4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Title()
0xf1a9  stelem.ref
0xf1aa  ldloc.2
0xf1ab  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xf1b0  ret
0xf1b1  ldc.i4   0x6567346A
0xf1b6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xf1bb  ldc.i4.s 0x64
0xf1bd  ldstr    aNoNeedToUpdate// "No need to update security for list {0}"
0xf1c2  ldc.i4.1
0xf1c3  newarr   [mscorlib]System.Object
0xf1c8  stloc.3
0xf1c9  ldloc.3
0xf1ca  ldc.i4.0
0xf1cb  ldarg.0
0xf1cc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Title()
0xf1d1  stelem.ref
0xf1d2  ldloc.3
0xf1d3  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xf1d8  ret
```
