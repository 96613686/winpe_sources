# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_ManageLink

- ea: `0x63690`
- end: `0x63711`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_ManageLink`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1bb90`
- `0x63690`
- `0x63a10`
- `0x64ba0`
- `0x64bb0`

## string_xrefs

- `0x636ac`: `?tsid=`
- `0x636e9`: `Failed to create ManageLink for service application '{0}'. Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x63690  ldnull
0x63691  stloc.0
0x63692  ldarg.0
0x63693  call     instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsPartitioned()
0x63698  brfalse.s loc_636A7
0x6369a  call     string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_SharedApplicationManageLink()
0x6369f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAdministrationLink::.ctor(string)
0x636a4  stloc.0
0x636a5  br.s     loc_636DA
0x636a7  call     string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_SharedApplicationManageLink()
0x636ac  ldstr    aTsid_1// "?tsid="
0x636b1  ldarg.0
0x636b2  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseMapper()
0x636b7  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPServiceApplicationUtilities::DefaultPartitionId
0x636bc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::GetTermStoreIdLocal(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x636c1  stloc.2
0x636c2  ldloca.s 2
0x636c4  constrained. [mscorlib]System.Guid
0x636ca  callvirt instance string [mscorlib]System.Object::ToString()
0x636cf  call     string [mscorlib]System.String::Concat(string, string, string)
0x636d4  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAdministrationLink::.ctor(string)
0x636d9  stloc.0
0x636da  leave.s  loc_6370F
0x636dc  stloc.1
0x636dd  ldc.i4   0x62766F32
0x636e2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x636e7  ldc.i4.s 0xA
0x636e9  ldstr    aFailedToCreate// "Failed to create ManageLink for service"...
0x636ee  ldc.i4.2
0x636ef  newarr   [mscorlib]System.Object
0x636f4  stloc.3
0x636f5  ldloc.3
0x636f6  ldc.i4.0
0x636f7  ldarg.0
0x636f8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x636fd  stelem.ref
0x636fe  ldloc.3
0x636ff  ldc.i4.1
0x63700  ldloc.1
0x63701  callvirt instance string [mscorlib]System.Object::ToString()
0x63706  stelem.ref
0x63707  ldloc.3
0x63708  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6370d  leave.s  loc_6370F
0x6370f  ldloc.0
0x63710  ret
```
