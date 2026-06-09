# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_PropertiesLink

- ea: `0x63720`
- end: `0x6377d`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_PropertiesLink`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x63720`

## string_xrefs

- `0x63722`: `/_admin/ManageMetadataService.aspx?appid=`
- `0x63755`: `Failed to create PropertiesLink for service application '{0}'. Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x63720  ldnull
0x63721  stloc.0
0x63722  ldstr    aAdminManagemet_0// "/_admin/ManageMetadataService.aspx?appi"...
0x63727  ldarg.0
0x63728  call     instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x6372d  stloc.2
0x6372e  ldloca.s 2
0x63730  constrained. [mscorlib]System.Guid
0x63736  callvirt instance string [mscorlib]System.Object::ToString()
0x6373b  call     string [mscorlib]System.String::Concat(string, string)
0x63740  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAdministrationLink::.ctor(string)
0x63745  stloc.0
0x63746  leave.s  loc_6377B
0x63748  stloc.1
0x63749  ldc.i4   0x62766F33
0x6374e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x63753  ldc.i4.s 0xA
0x63755  ldstr    aFailedToCreate_0// "Failed to create PropertiesLink for ser"...
0x6375a  ldc.i4.2
0x6375b  newarr   [mscorlib]System.Object
0x63760  stloc.3
0x63761  ldloc.3
0x63762  ldc.i4.0
0x63763  ldarg.0
0x63764  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x63769  stelem.ref
0x6376a  ldloc.3
0x6376b  ldc.i4.1
0x6376c  ldloc.1
0x6376d  callvirt instance string [mscorlib]System.Object::ToString()
0x63772  stelem.ref
0x63773  ldloc.3
0x63774  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x63779  leave.s  loc_6377B
0x6377b  ldloc.0
0x6377c  ret
```
