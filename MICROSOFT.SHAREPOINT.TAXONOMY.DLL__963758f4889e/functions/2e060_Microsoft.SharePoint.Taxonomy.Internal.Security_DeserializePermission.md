# Microsoft.SharePoint.Taxonomy.Internal.Security::DeserializePermission

- ea: `0x2e060`
- end: `0x2e171`
- name: `Microsoft.SharePoint.Taxonomy.Internal.Security::DeserializePermission`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e180`
- `0x73780`

## callees

- `0x26dc0`
- `0x26dd0`
- `0x2dfc0`
- `0x2e030`
- `0x2e060`
- `0x2e1b0`
- `0x2e890`

## string_xrefs

- `0x2e0bd`: `Failed to deserialize Site collection group '{0}'.`
- `0x2e126`: `Failed to deserialize permission. Exception: {0}`
- `0x2e14a`: `IsUserDeleted`

## pseudocode

```c

```

## disassembly

```asm
0x2e060  ldarg.0
0x2e061  ldstr    aA2// "a2"
0x2e066  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.IDataReader::GetString(string name)
0x2e06b  stloc.0
0x2e06c  ldarg.0
0x2e06d  ldstr    aA4// "a4"
0x2e072  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.IDataReader::GetInt(string name)
0x2e077  conv.ovf.u4.un
0x2e078  stloc.1
0x2e079  ldloc.0
0x2e07a  ldstr    aSitecollection_3// "SiteCollectionId:"
0x2e07f  ldc.i4.4
0x2e080  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2e085  brfalse.s loc_2E0DB
0x2e087  ldarg.2
0x2e088  brfalse  loc_2E170
0x2e08d  ldloca.s 2
0x2e08f  ldloc.0
0x2e090  ldstr    aSitecollection_3// "SiteCollectionId:"
0x2e095  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2e09a  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2e09f  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2e0a4  ldarg.2
0x2e0a5  ldloc.2
0x2e0a6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x2e0ab  leave    loc_2E170
0x2e0b0  pop
0x2e0b1  ldc.i4   0x67716535
0x2e0b6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2e0bb  ldc.i4.s 0x14
0x2e0bd  ldstr    aFailedToDeseri// "Failed to deserialize Site collection g"...
0x2e0c2  ldc.i4.1
0x2e0c3  newarr   [mscorlib]System.Object
0x2e0c8  stloc.s  5
0x2e0ca  ldloc.s  5
0x2e0cc  ldc.i4.0
0x2e0cd  ldloc.0
0x2e0ce  stelem.ref
0x2e0cf  ldloc.s  5
0x2e0d1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2e0d6  leave    loc_2E170
0x2e0db  ldloc.0
0x2e0dc  ldstr    aSitecollection_4// "SiteCollectionUrl:"
0x2e0e1  ldc.i4.5
0x2e0e2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2e0e7  brfalse.s loc_2E106
0x2e0e9  ldarg.3
0x2e0ea  brfalse  loc_2E170
0x2e0ef  ldarg.3
0x2e0f0  ldloc.0
0x2e0f1  ldstr    aSitecollection_4// "SiteCollectionUrl:"
0x2e0f6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2e0fb  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2e100  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedUrlStringCollection::Add(string urlString)
0x2e105  ret
0x2e106  ldloc.0
0x2e107  call     bool Microsoft.SharePoint.Taxonomy.Internal.Security::IsUserDeleted(string principalName)
0x2e10c  brtrue.s loc_2E170
0x2e10e  ldarg.1
0x2e10f  ldloc.0
0x2e110  ldloc.1
0x2e111  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAce`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> Microsoft.SharePoint.Taxonomy.Internal.Security::AddPermission(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights> acl, string principalName, valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights grantedPermissions)
0x2e116  pop
0x2e117  leave.s  loc_2E170
0x2e119  stloc.3
0x2e11a  ldc.i4   0x1C8559
0x2e11f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2e124  ldc.i4.s 0x32
0x2e126  ldstr    aFailedToDeseri_0// "Failed to deserialize permission. Excep"...
0x2e12b  ldc.i4.1
0x2e12c  newarr   [mscorlib]System.Object
0x2e131  stloc.s  6
0x2e133  ldloc.s  6
0x2e135  ldc.i4.0
0x2e136  ldloc.3
0x2e137  callvirt instance string [mscorlib]System.Object::ToString()
0x2e13c  stelem.ref
0x2e13d  ldloc.s  6
0x2e13f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2e144  ldloc.3
0x2e145  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x2e14a  ldstr    aIsuserdeleted// "IsUserDeleted"
0x2e14f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x2e154  stloc.s  4
0x2e156  ldloc.s  4
0x2e158  isinst   [mscorlib]System.Boolean
0x2e15d  brfalse.s loc_2E16E
0x2e15f  ldloc.s  4
0x2e161  unbox.any [mscorlib]System.Boolean
0x2e166  brfalse.s loc_2E16E
0x2e168  ldloc.0
0x2e169  call     void Microsoft.SharePoint.Taxonomy.Internal.Security::ProcessDeletedUser(string principalName)
0x2e16e  leave.s  loc_2E170
0x2e170  ret
```
