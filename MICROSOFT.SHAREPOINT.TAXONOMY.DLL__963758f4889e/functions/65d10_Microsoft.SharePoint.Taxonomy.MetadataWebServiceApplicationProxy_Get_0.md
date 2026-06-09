# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Get_0

- ea: `0x65d10`
- end: `0x65d94`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Get_0`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x65da0`

## callees

- `0x65d10`

## string_xrefs

- `0x65d58`: `MetadataWebService proxy is not installed.`
- `0x65d86`: `MetadataWebService application proxy cannot be found.`

## pseudocode

```c

```

## disassembly

```asm
0x65d10  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x65d15  stloc.0
0x65d16  ldnull
0x65d17  ldloc.0
0x65d18  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65d1d  brfalse.s loc_65D37
0x65d1f  ldc.i4   0x387A3064
0x65d24  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65d29  ldc.i4.s 0x64
0x65d2b  ldstr    aFailedToFindAL_0// "Failed to find a local farm"
0x65d30  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65d35  ldnull
0x65d36  ret
0x65d37  ldloc.0
0x65d38  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x65d3d  callvirt T0x2B000004
0x65d42  stloc.1
0x65d43  ldnull
0x65d44  ldloc.1
0x65d45  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65d4a  brfalse.s loc_65D64
0x65d4c  ldc.i4   0x387A3065
0x65d51  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65d56  ldc.i4.s 0x64
0x65d58  ldstr    aMetadatawebser_62// "MetadataWebService proxy is not install"...
0x65d5d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65d62  ldnull
0x65d63  ret
0x65d64  ldloc.1
0x65d65  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceProxy::get_ApplicationProxies()
0x65d6a  ldarg.0
0x65d6b  callvirt T0x2B0000A6
0x65d70  stloc.2
0x65d71  ldnull
0x65d72  ldloc.2
0x65d73  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65d78  brfalse.s loc_65D92
0x65d7a  ldc.i4   0x387A3066
0x65d7f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65d84  ldc.i4.s 0x64
0x65d86  ldstr    aMetadatawebser_63// "MetadataWebService application proxy ca"...
0x65d8b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65d90  ldnull
0x65d91  ret
0x65d92  ldloc.2
0x65d93  ret
```
