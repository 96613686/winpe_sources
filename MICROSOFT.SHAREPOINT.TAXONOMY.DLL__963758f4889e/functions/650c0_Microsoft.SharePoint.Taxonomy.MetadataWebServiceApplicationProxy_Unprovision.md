# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Unprovision

- ea: `0x650c0`
- end: `0x65124`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Unprovision`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x650d3`: `MetadataWebServiceApplicationProxy '{0}' unprovision started.`
- `0x6510d`: `MetadataWebServiceApplicationProxy '{0}' unprovision complete.`

## pseudocode

```c

```

## disassembly

```asm
0x650c0  ldarg.0
0x650c1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x650c6  stloc.0
0x650c7  ldc.i4   0x61617339
0x650cc  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x650d1  ldc.i4.s 0x14
0x650d3  ldstr    aMetadatawebser_57// "MetadataWebServiceApplicationProxy '{0}"...
0x650d8  ldc.i4.1
0x650d9  newarr   [mscorlib]System.Object
0x650de  stloc.1
0x650df  ldloc.1
0x650e0  ldc.i4.0
0x650e1  ldloc.0
0x650e2  stelem.ref
0x650e3  ldloc.1
0x650e4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x650e9  ldarg.0
0x650ea  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancer Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::loadBalancer
0x650ef  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceLoadBalancer::Unprovision()
0x650f4  ldarg.0
0x650f5  ldarg.1
0x650f6  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy::Unprovision(bool)
0x650fb  ldarg.0
0x650fc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x65101  ldc.i4   0x61617430
0x65106  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6510b  ldc.i4.s 0x14
0x6510d  ldstr    aMetadatawebser_58// "MetadataWebServiceApplicationProxy '{0}"...
0x65112  ldc.i4.1
0x65113  newarr   [mscorlib]System.Object
0x65118  stloc.2
0x65119  ldloc.2
0x6511a  ldc.i4.0
0x6511b  ldloc.0
0x6511c  stelem.ref
0x6511d  ldloc.2
0x6511e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x65123  ret
```
