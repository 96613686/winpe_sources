# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Unprovision

- ea: `0x63850`
- end: `0x638df`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Unprovision`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x63850`

## string_xrefs

- `0x63863`: `MetadataWebServiceApplication '{0}' unprovision started.`
- `0x638c8`: `MetadataWebServiceApplication '{0}' unprovision complete.`

## pseudocode

```c

```

## disassembly

```asm
0x63850  ldarg.0
0x63851  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x63856  stloc.0
0x63857  ldc.i4   0x61617234
0x6385c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x63861  ldc.i4.s 0x14
0x63863  ldstr    aMetadatawebser_29// "MetadataWebServiceApplication '{0}' unp"...
0x63868  ldc.i4.1
0x63869  newarr   [mscorlib]System.Object
0x6386e  stloc.2
0x6386f  ldloc.2
0x63870  ldc.i4.0
0x63871  ldloc.0
0x63872  stelem.ref
0x63873  ldloc.2
0x63874  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x63879  ldarg.0
0x6387a  ldarg.1
0x6387b  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::Unprovision(bool)
0x63880  ldarg.1
0x63881  brfalse.s loc_6389C
0x63883  ldarg.0
0x63884  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x63889  ldnull
0x6388a  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x6388f  brfalse.s loc_6389C
0x63891  ldarg.0
0x63892  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x63897  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Unprovision()
0x6389c  leave.s  loc_638BC
0x6389e  stloc.1
0x6389f  ldc.i4   0x10E653
0x638a4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x638a9  ldloc.1
0x638aa  ldstr    aFailedToUnprov// "Failed to Unprovision."
0x638af  ldc.i4.0
0x638b0  newarr   [mscorlib]System.Object
0x638b5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x638ba  rethrow
0x638bc  ldc.i4   0x61617235
0x638c1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x638c6  ldc.i4.s 0x14
0x638c8  ldstr    aMetadatawebser_30// "MetadataWebServiceApplication '{0}' unp"...
0x638cd  ldc.i4.1
0x638ce  newarr   [mscorlib]System.Object
0x638d3  stloc.3
0x638d4  ldloc.3
0x638d5  ldc.i4.0
0x638d6  ldloc.0
0x638d7  stelem.ref
0x638d8  ldloc.3
0x638d9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x638de  ret
```
