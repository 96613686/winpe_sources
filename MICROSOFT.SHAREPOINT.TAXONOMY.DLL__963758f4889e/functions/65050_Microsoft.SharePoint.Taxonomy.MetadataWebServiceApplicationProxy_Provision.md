# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Provision

- ea: `0x65050`
- end: `0x650b3`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Provision`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x65063`: `MetadataWebServiceApplicationProxy '{0}' provision started.`
- `0x6509c`: `MetadataWebServiceApplicationProxy '{0}' provision complete.`

## pseudocode

```c

```

## disassembly

```asm
0x65050  ldarg.0
0x65051  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x65056  stloc.0
0x65057  ldc.i4   0x61617337
0x6505c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65061  ldc.i4.s 0x14
0x65063  ldstr    aMetadatawebser_55// "MetadataWebServiceApplicationProxy '{0}"...
0x65068  ldc.i4.1
0x65069  newarr   [mscorlib]System.Object
0x6506e  stloc.1
0x6506f  ldloc.1
0x65070  ldc.i4.0
0x65071  ldloc.0
0x65072  stelem.ref
0x65073  ldloc.1
0x65074  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x65079  ldarg.0
0x6507a  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancer Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::loadBalancer
0x6507f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancer::Provision()
0x65084  ldarg.0
0x65085  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy::Provision()
0x6508a  ldarg.0
0x6508b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x65090  ldc.i4   0x61617338
0x65095  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6509a  ldc.i4.s 0x14
0x6509c  ldstr    aMetadatawebser_56// "MetadataWebServiceApplicationProxy '{0}"...
0x650a1  ldc.i4.1
0x650a2  newarr   [mscorlib]System.Object
0x650a7  stloc.2
0x650a8  ldloc.2
0x650a9  ldc.i4.0
0x650aa  ldloc.0
0x650ab  stelem.ref
0x650ac  ldloc.2
0x650ad  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x650b2  ret
```
