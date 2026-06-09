# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::OnProcessIdentityChanged

- ea: `0x64c00`
- end: `0x64ce1`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::OnProcessIdentityChanged`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x242a0`
- `0x63a30`
- `0x64c00`
- `0x66d80`

## string_xrefs

- `0x64c0c`: `MetadataWebServiceApplication '{0}' OnProcessIdentityChanged started.  Ensure new SID has permissions.`
- `0x64c28`: `processSecurityIdentifier`
- `0x64c54`: `MetadataWebServiceApplication '{0}' application pool account to be set: {1}.`
- `0x64c94`: `MetadataWebServiceApplication '{0}' with DB provision disabled: OnProcessIdentityChanged method skipped EnsureApplicationAccess call to the database`
- `0x64cc2`: `MetadataWebServiceApplication '{0}' OnProcessIdentityChanged completed.  New SID has been given permissions.`

## pseudocode

```c

```

## disassembly

```asm
0x64c00  ldc.i4   0x61617334
0x64c05  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64c0a  ldc.i4.s 0x14
0x64c0c  ldstr    aMetadatawebser_50// "MetadataWebServiceApplication '{0}' OnP"...
0x64c11  ldc.i4.1
0x64c12  newarr   [mscorlib]System.Object
0x64c17  stloc.1
0x64c18  ldloc.1
0x64c19  ldc.i4.0
0x64c1a  ldarg.0
0x64c1b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x64c20  stelem.ref
0x64c21  ldloc.1
0x64c22  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64c27  ldarg.1
0x64c28  ldstr    aProcesssecurit// "processSecurityIdentifier"
0x64c2d  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x64c32  ldarg.1
0x64c33  ldtoken  [mscorlib]System.Security.Principal.NTAccount
0x64c38  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x64c3d  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x64c42  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x64c47  stloc.0
0x64c48  ldc.i4   0x61617335
0x64c4d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64c52  ldc.i4.s 0x14
0x64c54  ldstr    aMetadatawebser_51// "MetadataWebServiceApplication '{0}' app"...
0x64c59  ldc.i4.2
0x64c5a  newarr   [mscorlib]System.Object
0x64c5f  stloc.2
0x64c60  ldloc.2
0x64c61  ldc.i4.0
0x64c62  ldarg.0
0x64c63  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x64c68  stelem.ref
0x64c69  ldloc.2
0x64c6a  ldc.i4.1
0x64c6b  ldloc.0
0x64c6c  stelem.ref
0x64c6d  ldloc.2
0x64c6e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64c73  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsServiceDatabaseEnabled()
0x64c78  brfalse.s loc_64C88
0x64c7a  ldarg.0
0x64c7b  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x64c80  ldloc.0
0x64c81  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::EnsureApplicationAccess(string userName)
0x64c86  br.s     loc_64CAF
0x64c88  ldc.i4   0x230D01F
0x64c8d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64c92  ldc.i4.s 0x32
0x64c94  ldstr    aMetadatawebser_52// "MetadataWebServiceApplication '{0}' wit"...
0x64c99  ldc.i4.1
0x64c9a  newarr   [mscorlib]System.Object
0x64c9f  stloc.3
0x64ca0  ldloc.3
0x64ca1  ldc.i4.0
0x64ca2  ldarg.0
0x64ca3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x64ca8  stelem.ref
0x64ca9  ldloc.3
0x64caa  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64caf  ldarg.0
0x64cb0  ldarg.1
0x64cb1  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::OnProcessIdentityChanged(class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x64cb6  ldc.i4   0x61617336
0x64cbb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64cc0  ldc.i4.s 0x14
0x64cc2  ldstr    aMetadatawebser_53// "MetadataWebServiceApplication '{0}' OnP"...
0x64cc7  ldc.i4.1
0x64cc8  newarr   [mscorlib]System.Object
0x64ccd  stloc.s  4
0x64ccf  ldloc.s  4
0x64cd1  ldc.i4.0
0x64cd2  ldarg.0
0x64cd3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x64cd8  stelem.ref
0x64cd9  ldloc.s  4
0x64cdb  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64ce0  ret
```
