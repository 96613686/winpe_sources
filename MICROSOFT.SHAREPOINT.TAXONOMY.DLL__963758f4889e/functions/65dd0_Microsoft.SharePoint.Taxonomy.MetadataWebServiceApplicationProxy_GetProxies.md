# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetProxies

- ea: `0x65dd0`
- end: `0x65ea4`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetProxies`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xde00`
- `0x65eb0`

## callees

- `0x65dd0`

## string_xrefs

- `0x65e68`: `Failed to find metadata web service proxy`
- `0x65e80`: `Failed to find the metadata web service`

## pseudocode

```c

```

## disassembly

```asm
0x65dd0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::.ctor()
0x65dd5  stloc.0
0x65dd6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x65ddb  stloc.1
0x65ddc  ldloc.1
0x65ddd  ldnull
0x65dde  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65de3  brfalse  loc_65E8C
0x65de8  ldloc.1
0x65de9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x65dee  callvirt T0x2B000011
0x65df3  stloc.2
0x65df4  ldloc.2
0x65df5  ldnull
0x65df6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65dfb  brfalse.s loc_65E74
0x65dfd  ldloc.1
0x65dfe  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x65e03  callvirt T0x2B000004
0x65e08  stloc.3
0x65e09  ldloc.3
0x65e0a  ldnull
0x65e0b  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65e10  brfalse.s loc_65E5C
0x65e12  ldloc.3
0x65e13  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceProxy::get_ApplicationProxies()
0x65e18  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::GetEnumerator()
0x65e1d  stloc.s  6
0x65e1f  br.s     loc_65E45
0x65e21  ldloc.s  6
0x65e23  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::get_Current()
0x65e28  stloc.s  4
0x65e2a  ldloc.s  4
0x65e2c  isinst   Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy
0x65e31  stloc.s  5
0x65e33  ldloc.s  5
0x65e35  ldnull
0x65e36  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x65e3b  brfalse.s loc_65E45
0x65e3d  ldloc.0
0x65e3e  ldloc.s  5
0x65e40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::Add(var<u1>)
0x65e45  ldloc.s  6
0x65e47  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x65e4c  brtrue.s loc_65E21
0x65e4e  leave.s  loc_65EA2
0x65e50  ldloc.s  6
0x65e52  brfalse.s loc_65E5B
0x65e54  ldloc.s  6
0x65e56  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65e5b  endfinally
0x65e5c  ldc.i4   0x61306777
0x65e61  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65e66  ldc.i4.s 0xA
0x65e68  ldstr    aFailedToFindMe// "Failed to find metadata web service pro"...
0x65e6d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65e72  br.s     loc_65EA2
0x65e74  ldc.i4   0x61306778
0x65e79  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65e7e  ldc.i4.s 0xA
0x65e80  ldstr    aFailedToFindTh// "Failed to find the metadata web service"
0x65e85  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65e8a  br.s     loc_65EA2
0x65e8c  ldc.i4   0x61306779
0x65e91  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65e96  ldc.i4.s 0x64
0x65e98  ldstr    aFailedToFindAL_0// "Failed to find a local farm"
0x65e9d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x65ea2  ldloc.0
0x65ea3  ret
```
