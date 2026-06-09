# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Update_0

- ea: `0x65f60`
- end: `0x66049`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Update_0`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3c260`
- `0x65f40`

## callees

- `0x2acd0`
- `0x65300`
- `0x65340`
- `0x65380`
- `0x653c0`
- `0x653e0`
- `0x65f60`

## string_xrefs

- `0x65f73`: `MetadataWebServiceApplicationProxy '{0}' property update started.`
- `0x6602f`: `MetadataWebServiceApplicationProxy '{0}' property update complete.`

## pseudocode

```c

```

## disassembly

```asm
0x65f60  ldarg.0
0x65f61  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x65f66  stloc.0
0x65f67  ldc.i4   0x61617433
0x65f6c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65f71  ldc.i4.s 0x14
0x65f73  ldstr    aMetadatawebser_64// "MetadataWebServiceApplicationProxy '{0}"...
0x65f78  ldc.i4.1
0x65f79  newarr   [mscorlib]System.Object
0x65f7e  stloc.3
0x65f7f  ldloc.3
0x65f80  ldc.i4.0
0x65f81  ldloc.0
0x65f82  stelem.ref
0x65f83  ldloc.3
0x65f84  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x65f89  ldarg.1
0x65f8a  brfalse.s loc_65F93
0x65f8c  ldarg.0
0x65f8d  ldarg.2
0x65f8e  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::set_IsDefaultKeywordTaxonomy(bool value)
0x65f93  ldarg.3
0x65f94  brfalse.s loc_65F9E
0x65f96  ldarg.0
0x65f97  ldarg.s  4
0x65f99  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::set_IsDefaultSiteCollectionTaxonomy(bool value)
0x65f9e  ldarg.s  0xA
0x65fa0  brfalse.s loc_65FDF
0x65fa2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup::get_Default()
0x65fa7  stloc.1
0x65fa8  ldloc.1
0x65fa9  ldarg.0
0x65faa  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup::Contains(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy)
0x65faf  stloc.2
0x65fb0  ldarg.s  0xB
0x65fb2  brfalse.s loc_65FC6
0x65fb4  ldloc.2
0x65fb5  brtrue.s loc_65FC6
0x65fb7  ldloc.1
0x65fb8  ldarg.0
0x65fb9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup::Add(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy)
0x65fbe  ldloc.1
0x65fbf  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x65fc4  br.s     loc_65FDF
0x65fc6  ldarg.s  0xB
0x65fc8  brtrue.s loc_65FDF
0x65fca  ldloc.2
0x65fcb  brfalse.s loc_65FDF
0x65fcd  ldloc.1
0x65fce  ldarg.0
0x65fcf  call     instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x65fd4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup::Remove(valuetype [mscorlib]System.Guid)
0x65fd9  ldloc.1
0x65fda  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x65fdf  ldarg.s  8
0x65fe1  brfalse.s loc_65FEB
0x65fe3  ldarg.0
0x65fe4  ldarg.s  9
0x65fe6  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::set_IsContentTypePushdownEnabled(bool value)
0x65feb  ldarg.0
0x65fec  call     instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::get_IsPartitioned()
0x65ff1  brtrue.s loc_6601D
0x65ff3  ldarg.s  5
0x65ff5  brfalse.s loc_6601D
0x65ff7  ldarg.0
0x65ff8  ldarg.s  6
0x65ffa  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::set_IsNPContentTypeSyndicationEnabled(bool value)
0x65fff  ldarg.s  6
0x66001  brfalse.s loc_6601D
0x66003  ldarg.s  7
0x66005  ldnull
0x66006  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x6600b  brfalse.s loc_6601D
0x6600d  ldstr    aErrorsyndicati// "ErrorSyndicationEnabledWithoutHub"
0x66012  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x66017  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6601c  throw
0x6601d  ldarg.0
0x6601e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x66023  ldc.i4   0x61617434
0x66028  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6602d  ldc.i4.s 0x14
0x6602f  ldstr    aMetadatawebser_65// "MetadataWebServiceApplicationProxy '{0}"...
0x66034  ldc.i4.1
0x66035  newarr   [mscorlib]System.Object
0x6603a  stloc.s  4
0x6603c  ldloc.s  4
0x6603e  ldc.i4.0
0x6603f  ldloc.0
0x66040  stelem.ref
0x66041  ldloc.s  4
0x66043  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x66048  ret
```
