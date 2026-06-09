# Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::GrantPermissionsWithoutConsent

- ea: `0x1e4a0`
- end: `0x1e58d`
- name: `Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::GrantPermissionsWithoutConsent`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1e300`
- `0x1e3e0`
- `0x1e4a0`
- `0x1e9d0`
- `0x1e9f0`

## string_xrefs

- `0x1e4bd`: `Not granting TermStore permissions from token, flighted={1} [ProviderName = {0}]`
- `0x1e52e`: `Granting TermStore write permissions for app`
- `0x1e569`: `Granting TermStore read permissions for app`

## pseudocode

```c

```

## disassembly

```asm
0x1e4a0  ldc.i4   0x1BA
0x1e4a5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x1e4aa  stloc.0
0x1e4ab  ldarg.1
0x1e4ac  brfalse.s loc_1E4B1
0x1e4ae  ldloc.0
0x1e4af  brtrue.s loc_1E4E6
0x1e4b1  ldc.i4   0x7220C5
0x1e4b6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1e4bb  ldc.i4.s 0x32
0x1e4bd  ldstr    aNotGrantingTer// "Not granting TermStore permissions from"...
0x1e4c2  ldc.i4.2
0x1e4c3  newarr   [mscorlib]System.Object
0x1e4c8  stloc.s  4
0x1e4ca  ldloc.s  4
0x1e4cc  ldc.i4.0
0x1e4cd  ldarg.0
0x1e4ce  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionProvider::get_DisplayName()
0x1e4d3  stelem.ref
0x1e4d4  ldloc.s  4
0x1e4d6  ldc.i4.1
0x1e4d7  ldloc.0
0x1e4d8  box      [mscorlib]System.Boolean
0x1e4dd  stelem.ref
0x1e4de  ldloc.s  4
0x1e4e0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1e4e5  ret
0x1e4e6  ldc.i4.0
0x1e4e7  stloc.1
0x1e4e8  ldarg.1
0x1e4e9  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionRequestContext::get_PermissionRequestXml()
0x1e4ee  ldstr    aHttpSharepoint// "http://sharepoint/taxonomy"
0x1e4f3  newobj   instance void [System]System.Uri::.ctor(string)
0x1e4f8  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionProvider::DoesAppContainPermissionRequestForScope(class [System.Xml.Linq]System.Xml.Linq.XElement, class [System]System.Uri)
0x1e4fd  brfalse.s loc_1E573
0x1e4ff  ldarg.1
0x1e500  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionRequestContext::get_PermissionRequestXml()
0x1e505  call     bool Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::CanModifyTermStore(class [System.Xml.Linq]System.Xml.Linq.XElement permissionRequestXml)
0x1e50a  brfalse.s loc_1E53A
0x1e50c  ldc.i4.1
0x1e50d  stloc.1
0x1e50e  ldc.i4.1
0x1e50f  ldc.i4.1
0x1e510  call     class Microsoft.SharePoint.Taxonomy.Internal.AppPermission Microsoft.SharePoint.Taxonomy.Internal.AppPermission::Create(bool canAccessTermStore, bool canModifyTermStore)
0x1e515  stloc.2
0x1e516  ldarg.1
0x1e517  ldloc.2
0x1e518  callvirt instance unsigned int8[] Microsoft.SharePoint.Taxonomy.Internal.AppPermission::Serialize()
0x1e51d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionRequestContext::SetTenantScopedPermissions(unsigned int8[])
0x1e522  ldc.i4   0x7220C6
0x1e527  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1e52c  ldc.i4.s 0x32
0x1e52e  ldstr    aGrantingTermst// "Granting TermStore write permissions fo"...
0x1e533  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1e538  br.s     loc_1E573
0x1e53a  ldarg.1
0x1e53b  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionRequestContext::get_PermissionRequestXml()
0x1e540  call     bool Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::CanAccessTermStore(class [System.Xml.Linq]System.Xml.Linq.XElement permissionRequestXml)
0x1e545  brfalse.s loc_1E573
0x1e547  ldc.i4.1
0x1e548  stloc.1
0x1e549  ldc.i4.1
0x1e54a  ldc.i4.0
0x1e54b  call     class Microsoft.SharePoint.Taxonomy.Internal.AppPermission Microsoft.SharePoint.Taxonomy.Internal.AppPermission::Create(bool canAccessTermStore, bool canModifyTermStore)
0x1e550  stloc.3
0x1e551  ldarg.1
0x1e552  ldloc.3
0x1e553  callvirt instance unsigned int8[] Microsoft.SharePoint.Taxonomy.Internal.AppPermission::Serialize()
0x1e558  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionRequestContext::SetTenantScopedPermissions(unsigned int8[])
0x1e55d  ldc.i4   0x7220C7
0x1e562  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1e567  ldc.i4.s 0x32
0x1e569  ldstr    aGrantingTermst_0// "Granting TermStore read permissions for"...
0x1e56e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1e573  ldloc.1
0x1e574  brtrue.s loc_1E58C
0x1e576  ldc.i4   0x7220C8
0x1e57b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1e580  ldc.i4.s 0x32
0x1e582  ldstr    aAppDoesnTConta// "App doesn't contain the permission requ"...
0x1e587  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1e58c  ret
```
