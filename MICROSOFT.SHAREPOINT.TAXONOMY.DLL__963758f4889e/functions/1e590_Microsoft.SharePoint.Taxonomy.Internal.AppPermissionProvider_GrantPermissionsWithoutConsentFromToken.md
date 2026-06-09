# Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::GrantPermissionsWithoutConsentFromToken

- ea: `0x1e590`
- end: `0x1e6cf`
- name: `Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::GrantPermissionsWithoutConsentFromToken`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1e300`
- `0x1e3e0`
- `0x1e590`

## string_xrefs

- `0x1e624`: `Write`
- `0x1e676`: `Granting TermStore write:{0} and read:{1} permissions for app`
- `0x1e6ab`: `Not granting TermStore permissions from token since permission is {1} - [ProviderName = {0}]`

## pseudocode

```c

```

## disassembly

```asm
0x1e590  ldc.i4   0x1BA
0x1e595  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x1e59a  stloc.0
0x1e59b  ldarg.1
0x1e59c  brfalse.s loc_1E5AE
0x1e59e  ldarg.1
0x1e59f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionRequestContext::get_PermissionScopeString()
0x1e5a4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1e5a9  brtrue.s loc_1E5AE
0x1e5ab  ldloc.0
0x1e5ac  brtrue.s loc_1E5E3
0x1e5ae  ldc.i4   0x7220C9
0x1e5b3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1e5b8  ldc.i4.s 0x32
0x1e5ba  ldstr    aNotGrantingTer_0// "Not granting TermStore permissions, fli"...
0x1e5bf  ldc.i4.2
0x1e5c0  newarr   [mscorlib]System.Object
0x1e5c5  stloc.s  7
0x1e5c7  ldloc.s  7
0x1e5c9  ldc.i4.0
0x1e5ca  ldarg.0
0x1e5cb  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionProvider::get_DisplayName()
0x1e5d0  stelem.ref
0x1e5d1  ldloc.s  7
0x1e5d3  ldc.i4.1
0x1e5d4  ldloc.0
0x1e5d5  box      [mscorlib]System.Boolean
0x1e5da  stelem.ref
0x1e5db  ldloc.s  7
0x1e5dd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1e5e2  ret
0x1e5e3  ldc.i4.0
0x1e5e4  stloc.1
0x1e5e5  ldc.i4.0
0x1e5e6  stloc.2
0x1e5e7  ldarg.1
0x1e5e8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionRequestContext::get_PermissionScopeString()
0x1e5ed  stloc.3
0x1e5ee  ldloc.3
0x1e5ef  ldstr    aTermstore// "TermStore"
0x1e5f4  ldloca.s 4
0x1e5f6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionProvider::DoesAppContainPermissionRequestForScope(string, string, class [mscorlib]System.Collections.Generic.IList`1<string>&)
0x1e5fb  brfalse.s loc_1E64E
0x1e5fd  ldloc.s  4
0x1e5ff  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x1e604  stloc.s  8
0x1e606  br.s     loc_1E637
0x1e608  ldloc.s  8
0x1e60a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1e60f  stloc.s  5
0x1e611  ldloc.s  5
0x1e613  ldstr    aRead// "Read"
0x1e618  ldc.i4.5
0x1e619  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1e61e  brfalse.s loc_1E622
0x1e620  ldc.i4.1
0x1e621  stloc.2
0x1e622  ldloc.s  5
0x1e624  ldstr    aWrite// "Write"
0x1e629  ldc.i4.5
0x1e62a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1e62f  brfalse.s loc_1E637
0x1e631  ldc.i4.1
0x1e632  stloc.1
0x1e633  ldc.i4.1
0x1e634  stloc.2
0x1e635  br.s     loc_1E640
0x1e637  ldloc.s  8
0x1e639  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1e63e  brtrue.s loc_1E608
0x1e640  leave.s  loc_1E64E
0x1e642  ldloc.s  8
0x1e644  brfalse.s loc_1E64D
0x1e646  ldloc.s  8
0x1e648  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e64d  endfinally
0x1e64e  ldloc.1
0x1e64f  brtrue.s loc_1E654
0x1e651  ldloc.2
0x1e652  brfalse.s loc_1E69F
0x1e654  ldloc.2
0x1e655  ldloc.1
0x1e656  call     class Microsoft.SharePoint.Taxonomy.Internal.AppPermission Microsoft.SharePoint.Taxonomy.Internal.AppPermission::Create(bool canAccessTermStore, bool canModifyTermStore)
0x1e65b  stloc.s  6
0x1e65d  ldarg.1
0x1e65e  ldloc.s  6
0x1e660  callvirt instance unsigned int8[] Microsoft.SharePoint.Taxonomy.Internal.AppPermission::Serialize()
0x1e665  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionRequestContext::SetTenantScopedPermissions(unsigned int8[])
0x1e66a  ldc.i4   0x7220CA
0x1e66f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1e674  ldc.i4.s 0x32
0x1e676  ldstr    aGrantingTermst_1// "Granting TermStore write:{0} and read:{"...
0x1e67b  ldc.i4.2
0x1e67c  newarr   [mscorlib]System.Object
0x1e681  stloc.s  9
0x1e683  ldloc.s  9
0x1e685  ldc.i4.0
0x1e686  ldloc.1
0x1e687  box      [mscorlib]System.Boolean
0x1e68c  stelem.ref
0x1e68d  ldloc.s  9
0x1e68f  ldc.i4.1
0x1e690  ldloc.2
0x1e691  box      [mscorlib]System.Boolean
0x1e696  stelem.ref
0x1e697  ldloc.s  9
0x1e699  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1e69e  ret
0x1e69f  ldc.i4   0x7220CB
0x1e6a4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1e6a9  ldc.i4.s 0x32
0x1e6ab  ldstr    aNotGrantingTer_1// "Not granting TermStore permissions from"...
0x1e6b0  ldc.i4.2
0x1e6b1  newarr   [mscorlib]System.Object
0x1e6b6  stloc.s  0xA
0x1e6b8  ldloc.s  0xA
0x1e6ba  ldc.i4.0
0x1e6bb  ldarg.0
0x1e6bc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAppPermissionProvider::get_DisplayName()
0x1e6c1  stelem.ref
0x1e6c2  ldloc.s  0xA
0x1e6c4  ldc.i4.1
0x1e6c5  ldloc.3
0x1e6c6  stelem.ref
0x1e6c7  ldloc.s  0xA
0x1e6c9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1e6ce  ret
```
