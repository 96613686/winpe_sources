# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::PreSendRequestHeaders

- ea: `0x5190`
- end: `0x5501`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::PreSendRequestHeaders`
- size: `881`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5190`
- `0x5630`
- `0x5700`
- `0x5840`
- `0x5910`
- `0x5920`
- `0x6780`
- `0x10ee0`
- `0x10f60`
- `0x10fe0`
- `0x111e0`

## string_xrefs

- `0x5196`: `X-MS-CookieUri-Requested`
- `0x5326`: `IsClaimsTrustedAuthenticationOnly: '{0}', IsOfficeClientIDCRLRequest: '{1}', HasSPTrustedSecurityTokenIssuer: '{2}', ForceIdcrlForOfficeClients: '{3}'.`
- `0x539d`: `Suppressing 401 Bearer challenge for Office Client since SP has configured MultiAuth.`
- `0x53c4`: `Suppressing 401 Bearer challenge for Office Client since there is no SPTrustedSecurityTokenIssuer.`
- `0x5421`: `Couldn't retrieve SPServiceContext, it could be the site doesn't exist or the tenant didn't provision correctly.`
- `0x5436`: `Couldn't retrieve SPServiceContext, it could be the site doesn't exist or the tenant didn't provision correctly.`

## pseudocode

```c

```

## disassembly

```asm
0x5190  ldarg.1
0x5191  isinst   [System.Web]System.Web.HttpApplication
0x5196  ldstr    aXMsCookieuriRe// "X-MS-CookieUri-Requested"
0x519b  newobj   instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorChallengeRequest::.ctor(class [System.Web]System.Web.HttpApplication httpApplication, string pattern)
0x51a0  stloc.0
0x51a1  ldarg.1
0x51a2  brtrue.s loc_51C4
0x51a4  ldloc.0
0x51a5  ldc.i4   0x11D44E0
0x51aa  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x51af  ldstr    aSenderIsNull// "Sender is null"
0x51b4  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message)
0x51b9  ldstr    aSender// "sender"
0x51be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x51c3  throw
0x51c4  ldarg.1
0x51c5  isinst   [System.Web]System.Web.HttpApplication
0x51ca  stloc.1
0x51cb  ldloc.1
0x51cc  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x51d1  stloc.2
0x51d2  ldloc.2
0x51d3  brtrue.s loc_51EF
0x51d5  ldloc.0
0x51d6  ldc.i4   0x11D44E1
0x51db  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x51e0  ldstr    aHttpcontextIsN// "httpContext is null"
0x51e5  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message)
0x51ea  leave    loc_5500
0x51ef  ldloc.2
0x51f0  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x51f5  brfalse.s loc_5219
0x51f7  ldloc.2
0x51f8  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x51fd  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x5202  brfalse.s loc_5219
0x5204  ldloc.2
0x5205  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x520a  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x520f  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x5214  brtrue   loc_54C2
0x5219  ldarg.0
0x521a  ldloc.2
0x521b  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsBearerChallengeRequested(class [System.Web]System.Web.HttpContext httpContext)
0x5220  stloc.3
0x5221  call     T0x2B00000E
0x5226  ldnull
0x5227  ceq
0x5229  ldc.i4.0
0x522a  ceq
0x522c  stloc.s  4
0x522e  ldloc.2
0x522f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x5234  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x5239  ldstr    aSpRequestDiagn// "SP-REQUEST-DIAGNOSTIC-BODY"
0x523e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5243  stloc.s  5
0x5245  ldloc.2
0x5246  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x524b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x5250  ldstr    aSpRequestDiagn// "SP-REQUEST-DIAGNOSTIC-BODY"
0x5255  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x525a  ldc.i4.0
0x525b  stloc.s  6
0x525d  ldc.i4   0x3776
0x5262  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x5267  brfalse.s loc_52B3
0x5269  ldarg.0
0x526a  ldloc.2
0x526b  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShouldIgnoreAuthentication(class [System.Web]System.Web.HttpContext httpContext)
0x5270  stloc.s  6
0x5272  ldc.i4   0x200365F
0x5277  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x527c  ldc.i4.s 0x32
0x527e  ldstr    aShouldBlockOau// "Should block OAuth challenge: {0}; curr"...
0x5283  ldc.i4.2
0x5284  newarr   [mscorlib]System.Object
0x5289  stloc.s  0x10
0x528b  ldloc.s  0x10
0x528d  ldc.i4.0
0x528e  ldloc.s  6
0x5290  box      [mscorlib]System.Boolean
0x5295  stelem.ref
0x5296  ldloc.s  0x10
0x5298  ldc.i4.1
0x5299  ldloc.2
0x529a  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x529f  callvirt instance int32 [System.Web]System.Web.HttpResponse::get_StatusCode()
0x52a4  box      [mscorlib]System.Int32
0x52a9  stelem.ref
0x52aa  ldloc.s  0x10
0x52ac  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x52b1  br.s     loc_52D4
0x52b3  ldarg.0
0x52b4  ldloc.2
0x52b5  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShouldIgnoreAuthenticationForLayouts(class [System.Web]System.Web.HttpContext httpContext)
0x52ba  ldarg.0
0x52bb  ldloc.2
0x52bc  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShouldIgnoreAuthenticationForPolicyEnforcement(class [System.Web]System.Web.HttpContext httpContext)
0x52c1  or
0x52c2  ldarg.0
0x52c3  ldloc.2
0x52c4  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShouldIgnoreAuthenticationForRedirects(class [System.Web]System.Web.HttpContext httpContext)
0x52c9  or
0x52ca  ldarg.0
0x52cb  ldloc.2
0x52cc  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShouldIgnoreAuthenticationForThrottlingForVroom(class [System.Web]System.Web.HttpContext httpContext)
0x52d1  or
0x52d2  stloc.s  6
0x52d4  ldloc.2
0x52d5  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::IncomingOAuthIdentityType(class [System.Web]System.Web.HttpContext)
0x52da  stloc.s  7
0x52dc  ldc.i4.1
0x52dd  stloc.s  8
0x52df  ldc.i4   0x373C
0x52e4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x52e9  brfalse  loc_53D1
0x52ee  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x52f3  brtrue   loc_53D1
0x52f8  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x52fd  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::IsClaimsTrustedAuthenticationOnly(class [System]System.Uri)
0x5302  stloc.s  9
0x5304  ldloc.2
0x5305  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::IsOfficeClientIDCRLRequest(class [System.Web]System.Web.HttpContext)
0x530a  stloc.s  0xA
0x530c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::HasSPTrustedSecurityTokenIssuer()
0x5311  stloc.s  0xB
0x5313  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::IsBearerSuppressedForOfficeClients()
0x5318  stloc.s  0xC
0x531a  ldc.i4   0x124A513
0x531f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5324  ldc.i4.s 0x32
0x5326  ldstr    aIsclaimstruste// "IsClaimsTrustedAuthenticationOnly: '{0}"...
0x532b  ldc.i4.4
0x532c  newarr   [mscorlib]System.Object
0x5331  stloc.s  0x11
0x5333  ldloc.s  0x11
0x5335  ldc.i4.0
0x5336  ldloc.s  9
0x5338  box      [mscorlib]System.Boolean
0x533d  stelem.ref
0x533e  ldloc.s  0x11
0x5340  ldc.i4.1
0x5341  ldloc.s  0xA
0x5343  box      [mscorlib]System.Boolean
0x5348  stelem.ref
0x5349  ldloc.s  0x11
0x534b  ldc.i4.2
0x534c  ldloc.s  0xB
0x534e  box      [mscorlib]System.Boolean
0x5353  stelem.ref
0x5354  ldloc.s  0x11
0x5356  ldc.i4.3
0x5357  ldloc.s  0xC
0x5359  box      [mscorlib]System.Boolean
0x535e  stelem.ref
0x535f  ldloc.s  0x11
0x5361  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5366  ldloc.s  0xC
0x5368  brfalse.s loc_5389
0x536a  ldloc.s  0xA
0x536c  brfalse.s loc_5389
0x536e  ldc.i4   0x244F414
0x5373  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x5378  ldc.i4.s 0x32
0x537a  ldstr    aSuppressing401// "Suppressing 401 Bearer challenge for Of"...
0x537f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5384  ldc.i4.0
0x5385  stloc.s  8
0x5387  br.s     loc_53D1
0x5389  ldloc.s  9
0x538b  brtrue.s loc_53AC
0x538d  ldloc.s  0xA
0x538f  brfalse.s loc_53AC
0x5391  ldc.i4   0x124A514
0x5396  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x539b  ldc.i4.s 0x32
0x539d  ldstr    aSuppressing401_0// "Suppressing 401 Bearer challenge for Of"...
0x53a2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x53a7  ldc.i4.0
0x53a8  stloc.s  8
0x53aa  br.s     loc_53D1
0x53ac  ldloc.s  9
0x53ae  brfalse.s loc_53D1
0x53b0  ldloc.s  0xA
0x53b2  brfalse.s loc_53D1
0x53b4  ldloc.s  0xB
0x53b6  brtrue.s loc_53D1
0x53b8  ldc.i4   0x124A515
0x53bd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x53c2  ldc.i4.s 0x32
0x53c4  ldstr    aSuppressing401_1// "Suppressing 401 Bearer challenge for Of"...
0x53c9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x53ce  ldc.i4.0
0x53cf  stloc.s  8
0x53d1  ldloc.3
0x53d2  brfalse  loc_54F4
0x53d7  ldloc.s  4
0x53d9  brtrue   loc_54F4
0x53de  ldc.i4.4
0x53df  ldloc.s  7
0x53e1  beq      loc_54F4
0x53e6  ldc.i4.5
0x53e7  ldloc.s  7
0x53e9  beq      loc_54F4
0x53ee  ldloc.s  6
0x53f0  brtrue   loc_54F4
0x53f5  ldloc.s  8
0x53f7  brfalse  loc_54F4
0x53fc  ldc.i4   0x29D0
0x5401  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x5406  brfalse.s loc_5446
0x5408  ldnull
0x5409  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x540e  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext)
0x5413  brfalse.s loc_5446
0x5415  ldc.i4   0x7E1205
0x541a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x541f  ldc.i4.s 0x32
0x5421  ldstr    aCouldnTRetriev// "Couldn't retrieve SPServiceContext, it "...
0x5426  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x542b  ldloc.0
0x542c  ldc.i4   0x11D44E2
0x5431  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x5436  ldstr    aCouldnTRetriev// "Couldn't retrieve SPServiceContext, it "...
0x543b  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message)
0x5440  ldloc.2
0x5441  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtilityInternal::Send404(class [System.Web]System.Web.HttpContext)
0x5446  ldloc.s  5
0x5448  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x544d  brtrue.s loc_549A
0x544f  ldloc.0
0x5450  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5455  stloc.s  0xD
0x5457  ldloc.s  0xD
0x5459  ldstr    aSuccess// "Success"
0x545e  ldstr    aDiagnosticbody// "diagnosticBodyRequest != IsNullOrEmpty"
0x5463  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5468  ldloc.s  0xD
0x546a  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> messages)
0x546f  ldloc.2
0x5470  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x5475  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0x547a  ldloc.2
0x547b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x5480  call     void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthHttpChallenge::SetOAuthChallenge(class [System.Web]System.Web.HttpResponse)
0x5485  ldloc.2
0x5486  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x548b  ldloc.s  5
0x548d  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x5492  ldloc.1
0x5493  callvirt instance void [System.Web]System.Web.HttpApplication::CompleteRequest()
0x5498  br.s     loc_54F4
0x549a  ldloc.0
0x549b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x54a0  stloc.s  0xE
0x54a2  ldloc.s  0xE
0x54a4  ldstr    aSuccess// "Success"
0x54a9  ldstr    aSending401Oaut// "Sending 401 OAuth Challenge"
0x54ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x54b3  ldloc.s  0xE
0x54b5  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> messages)
0x54ba  ldloc.1
0x54bb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::Send401OAuthChallenge(class [System.Web]System.Web.HttpApplication)
0x54c0  br.s     loc_54F4
0x54c2  ldloc.2
0x54c3  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x54c8  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x54cd  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x54d2  brfalse.s loc_54F4
0x54d4  ldloc.0
0x54d5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x54da  stloc.s  0xF
0x54dc  ldloc.s  0xF
0x54de  ldstr    aSuccess// "Success"
0x54e3  ldstr    aUserIsAuthenti// "User is authenticated"
0x54e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x54ed  ldloc.s  0xF
0x54ef  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorChallengeRequest::SuccessAndCleanup([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> messages)
0x54f4  leave.s  loc_5500
0x54f6  ldloc.0
0x54f7  brfalse.s loc_54FF
0x54f9  ldloc.0
0x54fa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54ff  endfinally
0x5500  ret
```
