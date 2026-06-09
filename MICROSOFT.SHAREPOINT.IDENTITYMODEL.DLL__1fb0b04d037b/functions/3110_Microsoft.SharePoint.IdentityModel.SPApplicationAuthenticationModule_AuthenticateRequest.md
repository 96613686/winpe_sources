# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::AuthenticateRequest

- ea: `0x3110`
- end: `0x35f8`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::AuthenticateRequest`
- size: `1256`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x3110`
- `0x36a0`
- `0x3960`
- `0x3bb0`
- `0x7790`
- `0x77d0`
- `0xbe30`
- `0x10ee0`
- `0x10f60`
- `0x11220`

## string_xrefs

- `0x3171`: `Clear Evo outgoing token context on thread.`
- `0x3189`: `SPApplicationAuthenticationModule: Clear outgoing token context from SpThreadContext `
- `0x31c5`: `SPApplicationAuthenticationModule: Clear cross tenant token context from SpThreadContext `
- `0x32e1`: `Log Client Id and Token Type.`
- `0x3300`: `Client Id : {0}. Token Type : {1}.`
- `0x3366`: `Can't sign in using token.`

## pseudocode

```c

```

## disassembly

```asm
0x3110  ldarg.1
0x3111  brtrue.s loc_311E
0x3113  ldstr    aSender// "sender"
0x3118  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x311d  throw
0x311e  ldc.i4   0x271C
0x3123  ldstr    aAuthenticatere// "AuthenticateRequest"
0x3128  ldstr    aDDbsElZltDevSt// "d:\\dbs\\el\\zlt\\dev\\sts\\identitymod"...
0x312d  ldc.i4   0xE3
0x3132  call     class [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer::Create(valuetype [Microsoft.Cobalt.Base]Cobalt.ComponentId, string, string, int32)
0x3137  stloc.s  0x11
0x3139  ldarg.1
0x313a  isinst   [System.Web]System.Web.HttpApplication
0x313f  ldstr    aSpOauthNativec// "/SP.OAuth.NativeClient/Authenticate"
0x3144  newobj   instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorAuthenticateRequest::.ctor(class [System.Web]System.Web.HttpApplication httpApplication, string pattern)
0x3149  stloc.0
0x314a  ldarg.1
0x314b  isinst   [System.Web]System.Web.HttpApplication
0x3150  stloc.1
0x3151  ldloc.1
0x3152  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x3157  stloc.2
0x3158  call     class Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::get_Current()
0x315d  stloc.3
0x315e  ldloca.s 4
0x3160  ldstr    aAd8eafc49c6d45// "ad8eafc4-9c6d-45f4-89a2-eb28c5f59c85"
0x3165  call     instance void [mscorlib]System.Guid::.ctor(string)
0x316a  ldloc.s  4
0x316c  ldstr    a6042016// "6/04/2016"
0x3171  ldstr    aClearEvoOutgoi// "Clear Evo outgoing token context on thr"...
0x3176  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x317b  brtrue.s loc_31A3
0x317d  ldc.i4   0x1255606
0x3182  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3187  ldc.i4.s 0x32
0x3189  ldstr    aSpapplicationa// "SPApplicationAuthenticationModule: Clea"...
0x318e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3193  ldnull
0x3194  stloc.s  5
0x3196  ldloc.s  5
0x3198  call     T0x2B000006
0x319d  call     T0x2B000007
0x31a2  pop
0x31a3  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::OAuthCrossTenantFeature
0x31a8  ldstr    a09162016// "09/16/2016"
0x31ad  ldstr    aOauthCrossTena// "OAuth Cross Tenant Call."
0x31b2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x31b7  brtrue.s loc_31DF
0x31b9  ldc.i4   0x134A48A
0x31be  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x31c3  ldc.i4.s 0x32
0x31c5  ldstr    aSpapplicationa_0// "SPApplicationAuthenticationModule: Clea"...
0x31ca  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x31cf  ldnull
0x31d0  stloc.s  6
0x31d2  ldloc.s  6
0x31d4  call     T0x2B000008
0x31d9  call     T0x2B000009
0x31de  pop
0x31df  ldloc.2
0x31e0  ldloc.3
0x31e1  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShouldTryApplicationAuthentication(class [System.Web]System.Web.HttpContext httpContext, class Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule fam)
0x31e6  brtrue.s loc_3226
0x31e8  ldloc.0
0x31e9  ldc.i4   0x121C618
0x31ee  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x31f3  ldstr    aNotAnOauthrequ// "Not an OAuthRequest."
0x31f8  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message)
0x31fd  ldc.i4   0x3776
0x3202  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3207  brfalse.s loc_3221
0x3209  ldloc.2
0x320a  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::IsOfficeClientIDCRLRequest(class [System.Web]System.Web.HttpContext)
0x320f  brfalse.s loc_3221
0x3211  ldstr    aApplicationAut// "Application_AuthenticatenModule_Engaged"
0x3216  ldc.i4.1
0x3217  box      [mscorlib]System.Boolean
0x321c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPThreadContext::Set(string, object)
0x3221  leave    loc_35F7
0x3226  ldc.i4   0x3776
0x322b  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3230  brfalse.s loc_3258
0x3232  ldc.i4   0x200365E
0x3237  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x323c  ldc.i4.s 0x32
0x323e  ldstr    aSpapplicationa_1// "SPApplicationAuthenticationModule: Shou"...
0x3243  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3248  ldstr    aApplicationAut// "Application_AuthenticatenModule_Engaged"
0x324d  ldc.i4.1
0x324e  box      [mscorlib]System.Boolean
0x3253  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPThreadContext::Set(string, object)
0x3258  ldstr    asc_336C0// ""
0x325d  stloc.s  7
0x325f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPClaimsCounterScope::.ctor()
0x3264  stloc.s  0x12
0x3266  ldstr    aApplicationAut_0// "Application Authentication Pipeline"
0x326b  ldc.i4.s 0x32
0x326d  ldc.i4.0
0x326e  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x3273  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x3278  stloc.s  0x13
0x327a  ldarg.0
0x327b  ldloc.1
0x327c  ldloc.2
0x327d  ldloc.3
0x327e  ldloca.s 7
0x3280  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ConstructIClaimsPrincipalAndSetThreadIdentity(class [System.Web]System.Web.HttpApplication httpApplication, class [System.Web]System.Web.HttpContext httpContext, class Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule fam, [out] string& tokenType)
0x3285  stloc.s  8
0x3287  ldloc.s  8
0x3289  brfalse  loc_3363
0x328e  ldloc.s  7
0x3290  ldc.i4.0
0x3291  ldnull
0x3292  call     void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.OAuthMetricsEventHelper::LogOAuthMetricsEvent(string, valuetype [Cil.Core]Cil.QosErrorType, string)
0x3297  ldnull
0x3298  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x329d  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x32a2  brfalse.s loc_32D7
0x32a4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x32a9  callvirt instance class [System]System.Collections.Generic.ISet`1<int32> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_ServerDebugFlags()
0x32ae  brfalse.s loc_32D7
0x32b0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x32b5  callvirt instance class [System]System.Collections.Generic.ISet`1<int32> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_ServerDebugFlags()
0x32ba  ldc.i4   0xCF17
0x32bf  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<int32>::Contains(var<u1>)
0x32c4  brtrue.s loc_32D7
0x32c6  ldloc.2
0x32c7  brtrue.s loc_32CC
0x32c9  ldnull
0x32ca  br.s     loc_32D2
0x32cc  ldloc.2
0x32cd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x32d2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::SetIsAuthenticatedOAuthRequest(class [System.Web]System.Web.HttpRequest)
0x32d7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::LogClientIdAndTokenType
0x32dc  ldstr    a01102018// "01/10/2018"
0x32e1  ldstr    aLogClientIdAnd// "Log Client Id and Token Type."
0x32e6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x32eb  brtrue.s loc_3328
0x32ed  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_Current()
0x32f2  brfalse.s loc_3328
0x32f4  ldc.i4   0x215150D
0x32f9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x32fe  ldc.i4.s 0x32
0x3300  ldstr    aClientId0Token// "Client Id : {0}. Token Type : {1}."
0x3305  ldc.i4.2
0x3306  newarr   [mscorlib]System.Object
0x330b  stloc.s  0x14
0x330d  ldloc.s  0x14
0x330f  ldc.i4.0
0x3310  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_Current()
0x3315  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_ClientId()
0x331a  stelem.ref
0x331b  ldloc.s  0x14
0x331d  ldc.i4.1
0x331e  ldloc.s  7
0x3320  stelem.ref
0x3321  ldloc.s  0x14
0x3323  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x3328  ldc.i4   0x1CA3D3
0x332d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3332  ldc.i4.s 0x32
0x3334  ldstr    aSpapplicationa_2// "SPApplicationAuthenticationModule Authe"...
0x3339  ldc.i4.2
0x333a  newarr   [mscorlib]System.Object
0x333f  stloc.s  0x15
0x3341  ldloc.s  0x15
0x3343  ldc.i4.0
0x3344  call     string SPApplicationAuthenticationHelper::GetLoggedInUserNameOrDefault()
0x3349  stelem.ref
0x334a  ldloc.s  0x15
0x334c  ldc.i4.1
0x334d  call     string SPApplicationAuthenticationHelper::GetLoggedInActorNameOrDefault()
0x3352  stelem.ref
0x3353  ldloc.s  0x15
0x3355  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x335a  ldloc.0
0x335b  ldnull
0x335c  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> messages)
0x3361  br.s     loc_3370
0x3363  ldloc.s  7
0x3365  ldc.i4.1
0x3366  ldstr    aCanTSignInUsin// "Can't sign in using token."
0x336b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.OAuthMetricsEventHelper::LogOAuthMetricsEvent(string, valuetype [Cil.Core]Cil.QosErrorType, string)
0x3370  leave.s  loc_337E
0x3372  ldloc.s  0x13
0x3374  brfalse.s loc_337D
0x3376  ldloc.s  0x13
0x3378  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x337d  endfinally
0x337e  leave.s  loc_338C
0x3380  ldloc.s  0x12
0x3382  brfalse.s loc_338B
0x3384  ldloc.s  0x12
0x3386  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x338b  endfinally
0x338c  leave    loc_35DD
0x3391  stloc.s  9
0x3393  ldc.i4   0x379C
0x3398  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x339d  brfalse.s loc_33AC
0x339f  ldloc.2
0x33a0  ldloc.s  9
0x33a2  call     void Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryHandleAuthenticateRequestError(class [System.Web]System.Web.HttpContext httpContext, class [mscorlib]System.Exception exception)
0x33a7  br       loc_3455
0x33ac  ldloc.s  9
0x33ae  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthExceptionSerializationData [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::GetSerializationData()
0x33b3  stloc.s  0xA
0x33b5  ldloc.2
0x33b6  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x33bb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x33c0  ldstr    aXMsDiagnostics// "x-ms-diagnostics"
0x33c5  ldloc.s  0xA
0x33c7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthExceptionSerializationData::get_DiagnosticHeader()
0x33cc  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x33d1  ldloc.2
0x33d2  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x33d7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x33dc  ldstr    aSpRequestDiagn// "SP-REQUEST-DIAGNOSTIC-BODY"
0x33e1  ldloc.s  0xA
0x33e3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthExceptionSerializationData::get_ErrorResponseBody()
0x33e8  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x33ed  ldc.i4   0x244650
0x33f2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x33f7  ldc.i4.s 0x14
0x33f9  ldstr    aSpapplicationa_3// "SPApplicationAuthenticationModule: Erro"...
0x33fe  ldc.i4.2
0x33ff  newarr   [mscorlib]System.Object
0x3404  stloc.s  0x16
0x3406  ldloc.s  0x16
0x3408  ldc.i4.0
0x3409  ldloc.s  0xA
0x340b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthExceptionSerializationData::get_DiagnosticHeader()
0x3410  stelem.ref
0x3411  ldloc.s  0x16
0x3413  ldc.i4.1
0x3414  ldloc.s  0xA
0x3416  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthExceptionSerializationData::get_ErrorResponseBody()
0x341b  stelem.ref
0x341c  ldloc.s  0x16
0x341e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x3423  leave.s  loc_3455
0x3425  stloc.s  0xB
0x3427  ldc.i4   0x244651
0x342c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3431  ldc.i4.s 0xA
0x3433  ldstr    aSpapplicationa_4// "SPApplicationAuthenticationModule: Erro"...
0x3438  ldc.i4.2
0x3439  newarr   [mscorlib]System.Object
0x343e  stloc.s  0x17
0x3440  ldloc.s  0x17
0x3442  ldc.i4.0
0x3443  ldloc.s  9
0x3445  stelem.ref
0x3446  ldloc.s  0x17
0x3448  ldc.i4.1
0x3449  ldloc.s  0xB
0x344b  stelem.ref
0x344c  ldloc.s  0x17
0x344e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x3453  leave.s  loc_3455
0x3455  ldloc.0
0x3456  ldc.i4   0x11D44DD
0x345b  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x3460  ldloc.s  9
0x3462  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3467  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message)
0x346c  ldloc.s  7
0x346e  ldc.i4.1
0x346f  ldloc.s  9
0x3471  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3476  call     void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.OAuthMetricsEventHelper::LogOAuthMetricsEvent(string, valuetype [Cil.Core]Cil.QosErrorType, string)
0x347b  rethrow
0x347d  stloc.s  0xC
0x347f  ldc.i4   0x379C
0x3484  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3489  brfalse.s loc_34A1
0x348b  ldloc.s  0xC
0x348d  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPGenericOAuthException::.ctor(class [mscorlib]System.Exception)
0x3492  stloc.s  0xD
0x3494  ldloc.2
0x3495  ldloc.s  0xD
0x3497  call     void Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryHandleAuthenticateRequestError(class [System.Web]System.Web.HttpContext httpContext, class [mscorlib]System.Exception exception)
0x349c  br       loc_354F
0x34a1  ldloc.s  0xC
0x34a3  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPGenericOAuthException::.ctor(class [mscorlib]System.Exception)
0x34a8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthExceptionSerializationData [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::GetSerializationData()
0x34ad  stloc.s  0xE
0x34af  ldloc.2
0x34b0  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x34b5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x34ba  ldstr    aXMsDiagnostics// "x-ms-diagnostics"
0x34bf  ldloc.s  0xE
0x34c1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthExceptionSerializationData::get_DiagnosticHeader()
0x34c6  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x34cb  ldloc.2
0x34cc  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x34d1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x34d6  ldstr    aSpRequestDiagn// "SP-REQUEST-DIAGNOSTIC-BODY"
0x34db  ldloc.s  0xE
0x34dd  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthExceptionSerializationData::get_ErrorResponseBody()
  ... truncated ...
```
