# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetTermSets

- ea: `0x69620`
- end: `0x6970e`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyClientService::GetTermSets`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x243f0`
- `0x244f0`
- `0x24560`
- `0x4baa0`
- `0x4cc20`
- `0x69620`

## string_xrefs

- `0x6962c`: `TaxonomyClientService: Get term sets started`
- `0x696af`: `TaxonomyClientService: Get term sets did not finish with client time stamps and termset id counts matching`
- `0x696d8`: `TaxonomyClientService: Get term sets failed: {0}`
- `0x69700`: `TaxonomyClientService: Get term sets finished`

## pseudocode

```c

```

## disassembly

```asm
0x69620  ldc.i4   0x66363775
0x69625  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6962a  ldc.i4.s 0x64
0x6962c  ldstr    aTaxonomyclient// "TaxonomyClientService: Get term sets st"...
0x69631  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x69636  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6963b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x69640  stloc.0
0x69641  ldloc.0
0x69642  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x69647  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::EnsureAuthentication(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x6964c  ldarg.1
0x6964d  call     valuetype [mscorlib]System.Guid[] Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetGuidsFromXml(string guids)
0x69652  stloc.1
0x69653  ldarg.2
0x69654  call     valuetype [mscorlib]System.Guid[] Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetGuidsFromXml(string guids)
0x69659  stloc.2
0x6965a  ldarg.s  4
0x6965c  call     valuetype [mscorlib]System.DateTime[] Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetDateTimesFromXmlTicks(string dateTimes)
0x69661  stloc.3
0x69662  ldarg.s  5
0x69664  call     int32[] Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetIntsFromXml(string ints)
0x69669  stloc.s  4
0x6966b  ldloc.1
0x6966c  ldlen
0x6966d  conv.i4
0x6966e  ldloc.2
0x6966f  ldlen
0x69670  conv.i4
0x69671  bne.un.s loc_696A3
0x69673  ldloc.1
0x69674  ldlen
0x69675  conv.i4
0x69676  ldloc.3
0x69677  ldlen
0x69678  conv.i4
0x69679  bne.un.s loc_696A3
0x6967b  ldloc.1
0x6967c  ldlen
0x6967d  conv.i4
0x6967e  ldloc.s  4
0x69680  ldlen
0x69681  conv.i4
0x69682  bne.un.s loc_696A3
0x69684  ldloc.0
0x69685  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x6968a  stloc.s  5
0x6968c  ldloc.s  5
0x6968e  ldloc.1
0x6968f  ldloc.2
0x69690  ldarg.3
0x69691  ldloc.3
0x69692  ldloc.s  4
0x69694  ldarg.s  6
0x69696  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomySession::GetTermSetsWithAllTerms(valuetype [mscorlib]System.Guid[] termStoreIds, valuetype [mscorlib]System.Guid[] termSetIds, int32 lcid, valuetype [mscorlib]System.DateTime[] clientTimes, int32[] clientVersions, [out] string& serverTimes)
0x6969b  stloc.s  6
0x6969d  ldloc.s  6
0x6969f  stloc.s  8
0x696a1  leave.s  loc_6970B
0x696a3  ldc.i4   0x66363777
0x696a8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x696ad  ldc.i4.s 0xA
0x696af  ldstr    aTaxonomyclient_0// "TaxonomyClientService: Get term sets di"...
0x696b4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x696b9  ldarg.s  6
0x696bb  ldsfld   string [mscorlib]System.String::Empty
0x696c0  stind.ref
0x696c1  ldsfld   string [mscorlib]System.String::Empty
0x696c6  stloc.s  8
0x696c8  leave.s  loc_6970B
0x696ca  stloc.s  7
0x696cc  ldc.i4   0x66363778
0x696d1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x696d6  ldc.i4.s 0xA
0x696d8  ldstr    aTaxonomyclient_1// "TaxonomyClientService: Get term sets fa"...
0x696dd  ldc.i4.1
0x696de  newarr   [mscorlib]System.Object
0x696e3  stloc.s  9
0x696e5  ldloc.s  9
0x696e7  ldc.i4.0
0x696e8  ldloc.s  7
0x696ea  stelem.ref
0x696eb  ldloc.s  9
0x696ed  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x696f2  rethrow
0x696f4  ldc.i4   0x66363776
0x696f9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x696fe  ldc.i4.s 0x64
0x69700  ldstr    aTaxonomyclient_2// "TaxonomyClientService: Get term sets fi"...
0x69705  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6970a  endfinally
0x6970b  ldloc.s  8
0x6970d  ret
```
