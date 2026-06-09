# Microsoft.SharePoint.Taxonomy.Internal.Security::DoesUserHaveServiceAdminPermissions

- ea: `0x2df10`
- end: `0x2df71`
- name: `Microsoft.SharePoint.Taxonomy.Internal.Security::DoesUserHaveServiceAdminPermissions`
- size: `97`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2dc50`
- `0x53de0`
- `0x54140`
- `0x545b0`
- `0x55630`
- `0x55f50`
- `0x56080`

## callees

- `0x2dea0`
- `0x2df10`
- `0x387f0`

## string_xrefs

- `0x2df4c`: `Tenant admin security check failed because TaxonomySession was not constructed with an SPSite.`
- `0x2df65`: `The current user has service admin permission.`

## pseudocode

```c

```

## disassembly

```asm
0x2df10  ldc.i4.0
0x2df11  stloc.0
0x2df12  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x2df17  ldc.i4.1
0x2df18  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::CurrentUserIsAdministrator(bool)
0x2df1d  brfalse.s loc_2DF23
0x2df1f  ldc.i4.1
0x2df20  stloc.0
0x2df21  br.s     loc_2DF56
0x2df23  ldarg.0
0x2df24  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext::get_SiteOrNull()
0x2df29  stloc.1
0x2df2a  ldloc.1
0x2df2b  brfalse.s loc_2DF3E
0x2df2d  ldc.i4.1
0x2df2e  ldloc.1
0x2df2f  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPAdministrationSiteType [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AdministrationSiteType()
0x2df34  bne.un.s loc_2DF56
0x2df36  call     bool Microsoft.SharePoint.Taxonomy.Internal.Security::GetIsCurrentUserAuthenticated()
0x2df3b  stloc.0
0x2df3c  br.s     loc_2DF56
0x2df3e  ldc.i4.0
0x2df3f  stloc.0
0x2df40  ldc.i4   0x636E3131
0x2df45  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2df4a  ldc.i4.s 0x32
0x2df4c  ldstr    aTenantAdminSec// "Tenant admin security check failed beca"...
0x2df51  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2df56  ldloc.0
0x2df57  brfalse.s loc_2DF6F
0x2df59  ldc.i4   0x8A340
0x2df5e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2df63  ldc.i4.s 0x64
0x2df65  ldstr    aTheCurrentUser// "The current user has service admin perm"...
0x2df6a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2df6f  ldloc.0
0x2df70  ret
```
