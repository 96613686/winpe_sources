# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Provision

- ea: `0x63780`
- end: `0x6384f`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Provision`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x63780`
- `0x63a30`

## string_xrefs

- `0x63793`: `MetadataWebServiceApplication '{0}' provision started.`
- `0x637d7`: `MetadataWebServiceApplication '{0}': Database provisioning skipped`
- `0x63834`: `MetadataWebServiceApplication '{0}' provision complete.`

## pseudocode

```c

```

## disassembly

```asm
0x63780  ldarg.0
0x63781  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x63786  stloc.0
0x63787  ldc.i4   0x61617232
0x6378c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x63791  ldc.i4.s 0x14
0x63793  ldstr    aMetadatawebser_26// "MetadataWebServiceApplication '{0}' pro"...
0x63798  ldc.i4.1
0x63799  newarr   [mscorlib]System.Object
0x6379e  stloc.2
0x6379f  ldloc.2
0x637a0  ldc.i4.0
0x637a1  ldloc.0
0x637a2  stelem.ref
0x637a3  ldloc.2
0x637a4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x637a9  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsServiceDatabaseEnabled()
0x637ae  brtrue.s loc_637BE
0x637b0  ldarg.0
0x637b1  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x637b6  ldnull
0x637b7  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x637bc  brfalse.s loc_637CB
0x637be  ldarg.0
0x637bf  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x637c4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x637c9  br.s     loc_637ED
0x637cb  ldc.i4   0x230D018
0x637d0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x637d5  ldc.i4.s 0x32
0x637d7  ldstr    aMetadatawebser_27// "MetadataWebServiceApplication '{0}': Da"...
0x637dc  ldc.i4.1
0x637dd  newarr   [mscorlib]System.Object
0x637e2  stloc.3
0x637e3  ldloc.3
0x637e4  ldc.i4.0
0x637e5  ldloc.0
0x637e6  stelem.ref
0x637e7  ldloc.3
0x637e8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x637ed  ldarg.0
0x637ee  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::Provision()
0x637f3  ldarg.0
0x637f4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x637f9  ldarg.0
0x637fa  ldc.i4.0
0x637fb  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::set_Status(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPObjectStatus)
0x63800  ldarg.0
0x63801  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x63806  leave.s  loc_63826
0x63808  stloc.1
0x63809  ldc.i4   0x10E652
0x6380e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x63813  ldloc.1
0x63814  ldstr    aFailedToProvis// "Failed to Provision."
0x63819  ldc.i4.0
0x6381a  newarr   [mscorlib]System.Object
0x6381f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x63824  rethrow
0x63826  leave.s  loc_6384E
0x63828  ldc.i4   0x61617233
0x6382d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x63832  ldc.i4.s 0x14
0x63834  ldstr    aMetadatawebser_28// "MetadataWebServiceApplication '{0}' pro"...
0x63839  ldc.i4.1
0x6383a  newarr   [mscorlib]System.Object
0x6383f  stloc.s  4
0x63841  ldloc.s  4
0x63843  ldc.i4.0
0x63844  ldloc.0
0x63845  stelem.ref
0x63846  ldloc.s  4
0x63848  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6384d  endfinally
0x6384e  ret
```
