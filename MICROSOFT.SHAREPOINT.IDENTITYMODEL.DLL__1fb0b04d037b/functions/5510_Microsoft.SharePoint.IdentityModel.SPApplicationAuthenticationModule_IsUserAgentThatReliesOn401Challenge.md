# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsUserAgentThatReliesOn401Challenge

- ea: `0x5510`
- end: `0x5626`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsUserAgentThatReliesOn401Challenge`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5630`

## callees

- `0x5510`
- `0x2cd40`

## string_xrefs

- `0x55d4`: `UserAgent is empty so skipping excel add-in check.`
- `0x5600`: `UserAgent is reliant on 401. So skipping 401 suppression.`
- `0x561a`: `UserAgent is not reliant on 401. So performing other 401 suppression checks.`

## pseudocode

```c

```

## disassembly

```asm
0x5510  newobj   instance void <>c__DisplayClass11::.ctor()
0x5515  stloc.2
0x5516  ldloc.2
0x5517  ldarg.1
0x5518  stfld    class [System.Web]System.Web.HttpContext <>c__DisplayClass11::httpContext
0x551d  ldc.i4.2
0x551e  newarr   [mscorlib]System.String
0x5523  stloc.3
0x5524  ldloc.3
0x5525  ldc.i4.0
0x5526  ldstr    aMicrosoftDataM// "Microsoft.Data.Mashup"
0x552b  stelem.ref
0x552c  ldloc.3
0x552d  ldc.i4.1
0x552e  ldstr    aCloudvideoclie// "CloudVideoClient.iPhone"
0x5533  stelem.ref
0x5534  ldloc.3
0x5535  stloc.0
0x5536  ldc.i4.0
0x5537  stloc.1
0x5538  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::Avoid401SuppressionForExcelAddIn
0x553d  ldstr    a03092018// "03/09/2018"
0x5542  ldstr    aAvoid401Suppre// "Avoid 401 suppression for Excel add-in."
0x5547  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x554c  brfalse.s loc_5569
0x554e  ldc.i4   0x22D089D
0x5553  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5558  ldc.i4.s 0x64
0x555a  ldstr    aAvoid401suppre// "Avoid401SuppressionForExcelAddIn killsw"...
0x555f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5564  br       loc_5624
0x5569  ldloc.2
0x556a  ldfld    class [System.Web]System.Web.HttpContext <>c__DisplayClass11::httpContext
0x556f  brtrue.s loc_558C
0x5571  ldc.i4   0x22D089E
0x5576  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x557b  ldc.i4.s 0xA
0x557d  ldstr    aTheHttpcontext// "The httpContext is null so skipping exc"...
0x5582  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5587  br       loc_5624
0x558c  ldloc.2
0x558d  ldfld    class [System.Web]System.Web.HttpContext <>c__DisplayClass11::httpContext
0x5592  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5597  brtrue.s loc_55B1
0x5599  ldc.i4   0x22D089F
0x559e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x55a3  ldc.i4.s 0xA
0x55a5  ldstr    aTheHttpcontext_0// "The httpContext has null request proper"...
0x55aa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x55af  br.s     loc_5624
0x55b1  ldloc.2
0x55b2  ldfld    class [System.Web]System.Web.HttpContext <>c__DisplayClass11::httpContext
0x55b7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x55bc  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserAgent()
0x55c1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x55c6  brfalse.s loc_55E0
0x55c8  ldc.i4   0x22D08A0
0x55cd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x55d2  ldc.i4.s 0x64
0x55d4  ldstr    aUseragentIsEmp// "UserAgent is empty so skipping excel ad"...
0x55d9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x55de  br.s     loc_5624
0x55e0  ldloc.0
0x55e1  ldloc.2
0x55e2  ldftn    instance bool <>c__DisplayClass11::<IsUserAgentThatReliesOn401Challenge>b__10(string x)
0x55e8  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x55ed  call     T0x2B00000A
0x55f2  brfalse.s loc_560E
0x55f4  ldc.i4   0x22D08A1
0x55f9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x55fe  ldc.i4.s 0x32
0x5600  ldstr    aUseragentIsRel// "UserAgent is reliant on 401. So skippin"...
0x5605  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x560a  ldc.i4.1
0x560b  stloc.1
0x560c  br.s     loc_5624
0x560e  ldc.i4   0x22D08A2
0x5613  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5618  ldc.i4.s 0x64
0x561a  ldstr    aUseragentIsNot// "UserAgent is not reliant on 401. So per"...
0x561f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5624  ldloc.1
0x5625  ret
```
