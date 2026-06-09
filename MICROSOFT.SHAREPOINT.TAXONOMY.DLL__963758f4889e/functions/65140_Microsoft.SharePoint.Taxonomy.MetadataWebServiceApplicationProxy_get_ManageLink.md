# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::get_ManageLink

- ea: `0x65140`
- end: `0x651e8`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::get_ManageLink`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x64bb0`
- `0x65140`
- `0x653e0`
- `0x65460`
- `0x66050`

## string_xrefs

- `0x6516d`: `?tsid=`
- `0x651c0`: `Failed to create ManageLink for service proxy '{0}'. Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x65140  ldnull
0x65141  stloc.0
0x65142  ldarg.0
0x65143  call     instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::get_IsPartitioned()
0x65148  brfalse.s loc_65168
0x6514a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6514f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x65154  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x65159  brtrue.s loc_65168
0x6515b  call     string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_SharedApplicationManageLink()
0x65160  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAdministrationLink::.ctor(string)
0x65165  stloc.0
0x65166  br.s     loc_651B1
0x65168  call     string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_SharedApplicationManageLink()
0x6516d  ldstr    aTsid_1// "?tsid="
0x65172  ldarg.0
0x65173  ldarg.0
0x65174  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x65179  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6517e  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetRawPartitionId(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x65183  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetTermStoreId(valuetype [mscorlib]System.Guid rawPartitionId)
0x65188  stloc.2
0x65189  ldloca.s 2
0x6518b  constrained. [mscorlib]System.Guid
0x65191  callvirt instance string [mscorlib]System.Object::ToString()
0x65196  call     string [mscorlib]System.String::Concat(string, string, string)
0x6519b  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAdministrationLink::.ctor(string)
0x651a0  stloc.0
0x651a1  leave.s  loc_651B1
0x651a3  pop
0x651a4  call     string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_SharedApplicationManageLink()
0x651a9  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAdministrationLink::.ctor(string)
0x651ae  stloc.0
0x651af  leave.s  loc_651B1
0x651b1  leave.s  loc_651E6
0x651b3  stloc.1
0x651b4  ldc.i4   0x62766F35
0x651b9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x651be  ldc.i4.s 0xA
0x651c0  ldstr    aFailedToCreate_1// "Failed to create ManageLink for service"...
0x651c5  ldc.i4.2
0x651c6  newarr   [mscorlib]System.Object
0x651cb  stloc.3
0x651cc  ldloc.3
0x651cd  ldc.i4.0
0x651ce  ldarg.0
0x651cf  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x651d4  stelem.ref
0x651d5  ldloc.3
0x651d6  ldc.i4.1
0x651d7  ldloc.1
0x651d8  callvirt instance string [mscorlib]System.Object::ToString()
0x651dd  stelem.ref
0x651de  ldloc.3
0x651df  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x651e4  leave.s  loc_651E6
0x651e6  ldloc.0
0x651e7  ret
```
