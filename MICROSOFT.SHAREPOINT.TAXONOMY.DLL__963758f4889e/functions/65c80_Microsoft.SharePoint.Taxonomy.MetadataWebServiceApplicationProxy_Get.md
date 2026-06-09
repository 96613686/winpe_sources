# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Get

- ea: `0x65c80`
- end: `0x65d04`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Get`
- size: `132`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x13a0`
- `0x13d0`
- `0x20600`
- `0x20e00`
- `0x65da0`

## callees

- `0x65c80`

## string_xrefs

- `0x65cc8`: `MetadataWebService proxy is not installed.`
- `0x65cf6`: `MetadataWebService application proxy cannot be found.`

## pseudocode

```c

```

## disassembly

```asm
0x65c80  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x65c85  stloc.0
0x65c86  ldnull
0x65c87  ldloc.0
0x65c88  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65c8d  brfalse.s loc_65CA7
0x65c8f  ldc.i4   0x35657368
0x65c94  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65c99  ldc.i4.s 0x64
0x65c9b  ldstr    aFailedToFindAL_0// "Failed to find a local farm"
0x65ca0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65ca5  ldnull
0x65ca6  ret
0x65ca7  ldloc.0
0x65ca8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x65cad  callvirt T0x2B000004
0x65cb2  stloc.1
0x65cb3  ldnull
0x65cb4  ldloc.1
0x65cb5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65cba  brfalse.s loc_65CD4
0x65cbc  ldc.i4   0x35657369
0x65cc1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65cc6  ldc.i4.s 0x64
0x65cc8  ldstr    aMetadatawebser_62// "MetadataWebService proxy is not install"...
0x65ccd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65cd2  ldnull
0x65cd3  ret
0x65cd4  ldloc.1
0x65cd5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceProxy::get_ApplicationProxies()
0x65cda  ldarg.0
0x65cdb  callvirt T0x2B0000A5
0x65ce0  stloc.2
0x65ce1  ldnull
0x65ce2  ldloc.2
0x65ce3  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65ce8  brfalse.s loc_65D02
0x65cea  ldc.i4   0x3565736A
0x65cef  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65cf4  ldc.i4.s 0x64
0x65cf6  ldstr    aMetadatawebser_63// "MetadataWebService application proxy ca"...
0x65cfb  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65d00  ldnull
0x65d01  ret
0x65d02  ldloc.2
0x65d03  ret
```
