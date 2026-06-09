# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Delete

- ea: `0x638e0`
- end: `0x6396b`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Delete`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x638e0`

## string_xrefs

- `0x638f3`: `MetadataWebServiceApplication '{0}' delete started.`
- `0x63936`: `Failed to Delete.`
- `0x63954`: `MetadataWebServiceApplication '{0}' delete complete.`

## pseudocode

```c

```

## disassembly

```asm
0x638e0  ldarg.0
0x638e1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x638e6  stloc.0
0x638e7  ldc.i4   0x61617236
0x638ec  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x638f1  ldc.i4.s 0x14
0x638f3  ldstr    aMetadatawebser_31// "MetadataWebServiceApplication '{0}' del"...
0x638f8  ldc.i4.1
0x638f9  newarr   [mscorlib]System.Object
0x638fe  stloc.2
0x638ff  ldloc.2
0x63900  ldc.i4.0
0x63901  ldloc.0
0x63902  stelem.ref
0x63903  ldloc.2
0x63904  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x63909  ldarg.0
0x6390a  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::Delete()
0x6390f  ldarg.0
0x63910  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x63915  ldnull
0x63916  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x6391b  brfalse.s loc_63928
0x6391d  ldarg.0
0x6391e  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x63923  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0x63928  leave.s  loc_63948
0x6392a  stloc.1
0x6392b  ldc.i4   0x10E654
0x63930  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x63935  ldloc.1
0x63936  ldstr    aFailedToDelete// "Failed to Delete."
0x6393b  ldc.i4.0
0x6393c  newarr   [mscorlib]System.Object
0x63941  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x63946  rethrow
0x63948  ldc.i4   0x61617237
0x6394d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x63952  ldc.i4.s 0x14
0x63954  ldstr    aMetadatawebser_32// "MetadataWebServiceApplication '{0}' del"...
0x63959  ldc.i4.1
0x6395a  newarr   [mscorlib]System.Object
0x6395f  stloc.3
0x63960  ldloc.3
0x63961  ldc.i4.0
0x63962  ldloc.0
0x63963  stelem.ref
0x63964  ldloc.3
0x63965  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6396a  ret
```
