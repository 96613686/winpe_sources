# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::.cctor

- ea: `0x72b0`
- end: `0x7774`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::.cctor`
- size: `1220`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x7447`: `/_vti_bin/ExcelService.asmx`
- `0x754f`: `/_layouts/15/online/handlers/SpoSuiteLinks.ashx`
- `0x75e7`: `/_vti_bin/TaxonomyInternalService.json/GetSuggestions`

## pseudocode

```c

```

## disassembly

```asm
0x72b0  ldstr    aCeb20b8e257b4a// "ceb20b8e-257b-4a86-9c26-ab109e704be3"
0x72b5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x72ba  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShareByLinkWithProofToken
0x72bf  ldstr    aCe7ae541Acbf42// "CE7AE541-ACBF-4204-88B1-68E01F1A1C05"
0x72c4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x72c9  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::UseUtilityLoadForSiteSubscription
0x72ce  ldstr    aC594a671116844// "C594A671-1168-4461-867F-040A9C47F005"
0x72d3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x72d8  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::VroomErrorFormatting
0x72dd  ldstr    aB25cb297D03446// "b25cb297-d034-469d-83fb-f97625d0e898"
0x72e2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x72e7  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IgnoreAuthenticationFor308Redirect
0x72ec  ldstr    aE55817f2Bc2d4a// "e55817f2-bc2d-4ac0-b373-aa093692f8e2"
0x72f1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x72f6  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::LogClientIdAndTokenType
0x72fb  ldstr    a712b45252ac541// "712b4525-2ac5-4163-86ee-65e22457f45a"
0x7300  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7305  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::CheckClaimsForLoopbackTokens
0x730a  ldstr    a28615e16179047// "28615e16-1790-477d-9fe6-6663e66ec10c"
0x730f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7314  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::Avoid401SuppressionForExcelAddIn
0x7319  ldstr    aDab1cecc467c48// "dab1cecc-467c-486e-aa7f-7a6cb38671af"
0x731e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7323  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::CheckIsWorkflowClaim
0x7328  ldstr    a28bd9e51Acba43// "28bd9e51-acba-43e5-b8f1-d62445b5187c"
0x732d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7332  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TrustedNetworkStopSettingBypass
0x7337  ldstr    aBb00a0b149004f// "bb00a0b1-4900-4f05-a775-eb8763fc2eb9"
0x733c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7341  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ReadTokenFromBodyForDocAspx
0x7346  ldstr    aA5013c663d6f4d// "a5013c66-3d6f-4deb-aa95-3c17e4f36fd9"
0x734b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7350  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::MarkMediaServiceRequestsForPolicy
0x7355  ldstr    a51b8b44091a24b// "51b8b440-91a2-4b14-b16d-d90bf349e5c9"
0x735a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x735f  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetSiteLevelPolicyFlagsForAllMediaServiceRequests
0x7364  ldc.i4.s 0x15
0x7366  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint
0x736b  stloc.s  0x1A
0x736d  ldloc.s  0x1A
0x736f  ldc.i4.0
0x7370  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7375  stloc.0
0x7376  ldloc.0
0x7377  ldstr    aVtiBinClientSv// "/_vti_bin/client.svc"
0x737c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x7381  ldloc.0
0x7382  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x7387  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x738c  ldloc.0
0x738d  stelem.ref
0x738e  ldloc.s  0x1A
0x7390  ldc.i4.1
0x7391  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7396  stloc.1
0x7397  ldloc.1
0x7398  ldstr    aVtiBinListdata// "/_vti_bin/listdata.svc"
0x739d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x73a2  ldloc.1
0x73a3  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x73a8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x73ad  ldloc.1
0x73ae  stelem.ref
0x73af  ldloc.s  0x1A
0x73b1  ldc.i4.2
0x73b2  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x73b7  stloc.2
0x73b8  ldloc.2
0x73b9  ldstr    aVtiBinSitesAsm// "/_vti_bin/sites.asmx"
0x73be  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x73c3  ldloc.2
0x73c4  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x73c9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x73ce  ldloc.2
0x73cf  stelem.ref
0x73d0  ldloc.s  0x1A
0x73d2  ldc.i4.3
0x73d3  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x73d8  stloc.3
0x73d9  ldloc.3
0x73da  ldstr    aApi// "/_api/"
0x73df  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x73e4  ldloc.3
0x73e5  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x73ea  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x73ef  ldloc.3
0x73f0  stelem.ref
0x73f1  ldloc.s  0x1A
0x73f3  ldc.i4.4
0x73f4  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x73f9  stloc.s  4
0x73fb  ldloc.s  4
0x73fd  ldstr    aVtiBinExcelres// "/_vti_bin/ExcelRest.aspx"
0x7402  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x7407  ldloc.s  4
0x7409  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x740e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x7413  ldloc.s  4
0x7415  stelem.ref
0x7416  ldloc.s  0x1A
0x7418  ldc.i4.5
0x7419  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x741e  stloc.s  5
0x7420  ldloc.s  5
0x7422  ldstr    aVtiBinExcelres_0// "/_vti_bin/ExcelRest.ashx"
0x7427  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x742c  ldloc.s  5
0x742e  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x7433  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x7438  ldloc.s  5
0x743a  stelem.ref
0x743b  ldloc.s  0x1A
0x743d  ldc.i4.6
0x743e  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7443  stloc.s  6
0x7445  ldloc.s  6
0x7447  ldstr    aVtiBinExcelser// "/_vti_bin/ExcelService.asmx"
0x744c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x7451  ldloc.s  6
0x7453  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x7458  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x745d  ldloc.s  6
0x745f  stelem.ref
0x7460  ldloc.s  0x1A
0x7462  ldc.i4.7
0x7463  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7468  stloc.s  7
0x746a  ldloc.s  7
0x746c  ldstr    aVtiBinPowerpiv// "/_vti_bin/PowerPivot16/UsageReporting.s"...
0x7471  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x7476  ldloc.s  7
0x7478  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x747d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x7482  ldloc.s  7
0x7484  stelem.ref
0x7485  ldloc.s  0x1A
0x7487  ldc.i4.8
0x7488  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x748d  stloc.s  8
0x748f  ldloc.s  8
0x7491  ldstr    aVtiBinDelveapi// "/_vti_bin/DelveApi.ashx"
0x7496  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x749b  ldloc.s  8
0x749d  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x74a2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x74a7  ldloc.s  8
0x74a9  stelem.ref
0x74aa  ldloc.s  0x1A
0x74ac  ldc.i4.s 9
0x74ae  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x74b3  stloc.s  9
0x74b5  ldloc.s  9
0x74b7  ldstr    aVtiBinDelveemb// "/_vti_bin/DelveEmbed.ashx"
0x74bc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x74c1  ldloc.s  9
0x74c3  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x74c8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x74cd  ldloc.s  9
0x74cf  stelem.ref
0x74d0  ldloc.s  0x1A
0x74d2  ldc.i4.s 0xA
0x74d4  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x74d9  stloc.s  0xA
0x74db  ldloc.s  0xA
0x74dd  ldstr    aLayouts15Getpr// "/_layouts/15/getpreview.ashx"
0x74e2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x74e7  ldloc.s  0xA
0x74e9  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x74ee  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x74f3  ldloc.s  0xA
0x74f5  stelem.ref
0x74f6  ldloc.s  0x1A
0x74f8  ldc.i4.s 0xB
0x74fa  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x74ff  stloc.s  0xB
0x7501  ldloc.s  0xB
0x7503  ldstr    aVtiBinWopiAshx// "/_vti_bin/wopi.ashx"
0x7508  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x750d  ldloc.s  0xB
0x750f  ldstr    aWopi// "wopi"
0x7514  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x7519  ldloc.s  0xB
0x751b  stelem.ref
0x751c  ldloc.s  0x1A
0x751e  ldc.i4.s 0xC
0x7520  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7525  stloc.s  0xC
0x7527  ldloc.s  0xC
0x7529  ldstr    aLayouts15Userp// "/_layouts/15/userphoto.aspx"
0x752e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x7533  ldloc.s  0xC
0x7535  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x753a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x753f  ldloc.s  0xC
0x7541  stelem.ref
0x7542  ldloc.s  0x1A
0x7544  ldc.i4.s 0xD
0x7546  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x754b  stloc.s  0xD
0x754d  ldloc.s  0xD
0x754f  ldstr    aLayouts15Onlin// "/_layouts/15/online/handlers/SpoSuiteLi"...
0x7554  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x7559  ldloc.s  0xD
0x755b  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x7560  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x7565  ldloc.s  0xD
0x7567  stelem.ref
0x7568  ldloc.s  0x1A
0x756a  ldc.i4.s 0xE
0x756c  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7571  stloc.s  0xE
0x7573  ldloc.s  0xE
0x7575  ldstr    aLayouts15Wopie// "/_layouts/15/wopiembedframe.aspx"
0x757a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x757f  ldloc.s  0xE
0x7581  ldstr    aWopi// "wopi"
0x7586  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x758b  ldloc.s  0xE
0x758d  stelem.ref
0x758e  ldloc.s  0x1A
0x7590  ldc.i4.s 0xF
0x7592  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7597  stloc.s  0xF
0x7599  ldloc.s  0xF
0x759b  ldstr    aVtiBinHomeapiA// "/_vti_bin/homeapi.ashx"
0x75a0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x75a5  ldloc.s  0xF
0x75a7  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x75ac  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x75b1  ldloc.s  0xF
0x75b3  stelem.ref
0x75b4  ldloc.s  0x1A
0x75b6  ldc.i4.s 0x10
0x75b8  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x75bd  stloc.s  0x10
0x75bf  ldloc.s  0x10
0x75c1  ldstr    aVtiBinPubliccd// "/_vti_bin/publiccdn.ashx"
0x75c6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x75cb  ldloc.s  0x10
0x75cd  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x75d2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x75d7  ldloc.s  0x10
0x75d9  stelem.ref
0x75da  ldloc.s  0x1A
0x75dc  ldc.i4.s 0x11
0x75de  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x75e3  stloc.s  0x11
0x75e5  ldloc.s  0x11
0x75e7  ldstr    aVtiBinTaxonomy// "/_vti_bin/TaxonomyInternalService.json/"...
0x75ec  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x75f1  ldloc.s  0x11
0x75f3  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x75f8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x75fd  ldloc.s  0x11
0x75ff  stelem.ref
0x7600  ldloc.s  0x1A
0x7602  ldc.i4.s 0x12
0x7604  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7609  stloc.s  0x12
0x760b  ldloc.s  0x12
0x760d  ldstr    aLayouts15Downl// "/_layouts/15/download.aspx"
0x7612  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x7617  ldloc.s  0x12
0x7619  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x761e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x7623  ldloc.s  0x12
0x7625  stelem.ref
0x7626  ldloc.s  0x1A
0x7628  ldc.i4.s 0x13
0x762a  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x762f  stloc.s  0x13
0x7631  ldloc.s  0x13
0x7633  ldstr    aLayouts15DocAs// "/_layouts/15/doc.aspx"
0x7638  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x763d  ldloc.s  0x13
0x763f  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x7644  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x7649  ldloc.s  0x13
0x764b  stelem.ref
0x764c  ldloc.s  0x1A
0x764e  ldc.i4.s 0x14
0x7650  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7655  stloc.s  0x14
0x7657  ldloc.s  0x14
0x7659  ldstr    aLayouts15Wopif// "/_layouts/15/WopiFrame.aspx"
0x765e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_RelativeEndPoint(string)
0x7663  ldloc.s  0x14
0x7665  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x766a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::set_ApplicationId(string)
0x766f  ldloc.s  0x14
0x7671  stelem.ref
0x7672  ldloc.s  0x1A
0x7674  stsfld   class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint[] Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::s_AllowedEndPoints
0x7679  ldc.i4.3
0x767a  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint
0x767f  stloc.s  0x1B
0x7681  ldloc.s  0x1B
0x7683  ldc.i4.0
0x7684  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::.ctor()
0x7689  stloc.s  0x15
  ... truncated ...
```
