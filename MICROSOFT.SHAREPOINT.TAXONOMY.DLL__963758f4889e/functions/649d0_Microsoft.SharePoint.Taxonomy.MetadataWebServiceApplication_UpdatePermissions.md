# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::UpdatePermissions

- ea: `0x649d0`
- end: `0x64a90`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::UpdatePermissions`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3b1c0`
- `0x3b800`

## string_xrefs

- `0x649dc`: `UpdatePermissions on service app: '{0}' started.`
- `0x64a74`: `UpdatePermissions on service app: '{0}' completed successfully.`

## pseudocode

```c

```

## disassembly

```asm
0x649d0  ldc.i4   0x63636430
0x649d5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x649da  ldc.i4.s 0x14
0x649dc  ldstr    aUpdatepermissi// "UpdatePermissions on service app: '{0}'"...
0x649e1  ldc.i4.1
0x649e2  newarr   [mscorlib]System.Object
0x649e7  stloc.2
0x649e8  ldloc.2
0x649e9  ldc.i4.0
0x649ea  ldarg.0
0x649eb  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x649f0  stelem.ref
0x649f1  ldloc.2
0x649f2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x649f7  ldarg.0
0x649f8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationSecurity [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::GetAccessControl()
0x649fd  stloc.0
0x649fe  ldloc.0
0x649ff  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPObjectSecurity::PurgeAccessRules()
0x64a04  ldarg.0
0x64a05  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPCentralAdministrationSecurity [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplication::GetAdministrationAccessControl()
0x64a0a  stloc.1
0x64a0b  ldloc.1
0x64a0c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPObjectSecurity::PurgeAccessRules()
0x64a11  ldarg.0
0x64a12  ldloc.1
0x64a13  ldarg.1
0x64a14  ldc.i4.m1
0x64a15  conv.i8
0x64a16  ldc.i4.m1
0x64a17  conv.i8
0x64a18  call     T0x2B0000A3
0x64a1d  ldarg.0
0x64a1e  ldloc.0
0x64a1f  ldarg.2
0x64a20  ldc.i4   0x7000
0x64a25  conv.i8
0x64a26  ldc.i4   0x7000
0x64a2b  conv.i8
0x64a2c  call     T0x2B0000A4
0x64a31  ldarg.0
0x64a32  ldloc.0
0x64a33  ldarg.3
0x64a34  ldc.i4   0x3000
0x64a39  conv.i8
0x64a3a  ldc.i4   0x3000
0x64a3f  conv.i8
0x64a40  call     T0x2B0000A4
0x64a45  ldarg.0
0x64a46  ldloc.0
0x64a47  ldarg.s  4
0x64a49  ldc.i4   0x1000
0x64a4e  conv.i8
0x64a4f  ldc.i4   0x1000
0x64a54  conv.i8
0x64a55  call     T0x2B0000A4
0x64a5a  ldarg.0
0x64a5b  ldloc.0
0x64a5c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::SetAccessControl(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationSecurity)
0x64a61  ldarg.0
0x64a62  ldloc.1
0x64a63  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplication::SetAdministrationAccessControl(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPCentralAdministrationSecurity)
0x64a68  ldc.i4   0x63636431
0x64a6d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64a72  ldc.i4.s 0x14
0x64a74  ldstr    aUpdatepermissi_0// "UpdatePermissions on service app: '{0}'"...
0x64a79  ldc.i4.1
0x64a7a  newarr   [mscorlib]System.Object
0x64a7f  stloc.3
0x64a80  ldloc.3
0x64a81  ldc.i4.0
0x64a82  ldarg.0
0x64a83  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x64a88  stelem.ref
0x64a89  ldloc.3
0x64a8a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64a8f  ret
```
