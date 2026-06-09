# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TrySignInUsingUserLoginTokenCache

- ea: `0x4270`
- end: `0x44bc`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TrySignInUsingUserLoginTokenCache`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x3bb0`

## callees

- `0x41e0`
- `0x4210`
- `0x4240`
- `0x4270`
- `0x44c0`
- `0x4500`
- `0x11ca0`
- `0x13570`
- `0x13590`

## string_xrefs

- `0x4306`: `SPApplicationAuthenticationModule: Incoming token doesn't have user identity.`
- `0x43cf`: `SPApplicationAuthenticationModule: Tenant ID is null, so using incomingActorIdentity to get Tenant Id.`
- `0x44b0`: `SPApplicationAuthenticationModule: Incoming token does not contain an actor.`
- `0x4273`: `tokenContext`
- `0x4296`: `SPApplicationAuthenticationModule: Using user token cache is disabled.`
- `0x42c0`: `SPApplicationAuthenticationModule: OAuth request has to be either User or User+App to try to use user token cache. Current request type:{0}.`
- `0x4384`: `SPApplicationAuthenticationModule: App Asserted User V1 token, so make ClientAppId identity as incoming identity.`
- `0x43fb`: `SPApplicationAuthenticationModule: Client App ID is null, so using incomingActorIdentity to get Client App Id.`
- `0x4456`: `SPApplicationAuthenticationModule: This is not App Asserted User V1 token, so keep actor as incoming identity.`
- `0x446f`: `SPApplicationAuthenticationModule: Incoming token contains actor. Trying to attach it to current thread. Incoming Actor Identity:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x4270  ldarg.1
0x4271  brtrue.s loc_427E
0x4273  ldstr    aTokencontext// "tokenContext"
0x4278  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x427d  throw
0x427e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x4283  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_DisableCacheOptimizationForIncomingOAuthRequest()
0x4288  brfalse.s loc_42A2
0x428a  ldc.i4   0x2563D1
0x428f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4294  ldc.i4.s 0x64
0x4296  ldstr    aSpapplicationa_34// "SPApplicationAuthenticationModule: Usin"...
0x429b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x42a0  ldc.i4.0
0x42a1  ret
0x42a2  ldarg.1
0x42a3  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_IdentityType()
0x42a8  ldc.i4.1
0x42a9  beq.s    loc_42EA
0x42ab  ldarg.1
0x42ac  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_IdentityType()
0x42b1  ldc.i4.3
0x42b2  beq.s    loc_42EA
0x42b4  ldc.i4   0x2563D2
0x42b9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x42be  ldc.i4.s 0x64
0x42c0  ldstr    aSpapplicationa_35// "SPApplicationAuthenticationModule: OAut"...
0x42c5  ldc.i4.1
0x42c6  newarr   [mscorlib]System.Object
0x42cb  stloc.s  8
0x42cd  ldloc.s  8
0x42cf  ldc.i4.0
0x42d0  ldarg.1
0x42d1  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_IdentityType()
0x42d6  box      [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType
0x42db  callvirt instance string [mscorlib]System.Object::ToString()
0x42e0  stelem.ref
0x42e1  ldloc.s  8
0x42e3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x42e8  ldc.i4.0
0x42e9  ret
0x42ea  ldarg.1
0x42eb  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_Identity()
0x42f0  ldc.i4.0
0x42f1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x42f6  stloc.0
0x42f7  ldloc.0
0x42f8  brtrue.s loc_4312
0x42fa  ldc.i4   0x2563D3
0x42ff  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4304  ldc.i4.s 0xA
0x4306  ldstr    aSpapplicationa_19// "SPApplicationAuthenticationModule: Inco"...
0x430b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4310  ldc.i4.0
0x4311  ret
0x4312  ldarg.1
0x4313  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TrySignInUserFromCache(class Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext tokenContext)
0x4318  brtrue.s loc_431C
0x431a  ldc.i4.0
0x431b  ret
0x431c  ldc.i4   0x29BA
0x4321  ldc.i4.3
0x4322  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility::IsCodeEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility/FlightEnvironment)
0x4327  brtrue   loc_44BA
0x432c  ldloc.0
0x432d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x4332  stloc.1
0x4333  ldc.i4   0x2B3C
0x4338  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x433d  brfalse  loc_4460
0x4342  ldc.i4   0x2B36
0x4347  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x434c  stloc.2
0x434d  ldloc.0
0x434e  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsServiceAssertedAppV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x4353  stloc.3
0x4354  ldloc.0
0x4355  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsAppAssertedUserV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x435a  brtrue.s loc_4368
0x435c  ldloc.2
0x435d  brfalse  loc_444A
0x4362  ldloc.3
0x4363  brfalse  loc_444A
0x4368  ldloc.0
0x4369  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x436e  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsClientAppAssertionAllowed(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x4373  brfalse  loc_444A
0x4378  ldc.i4   0x10638CC
0x437d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4382  ldc.i4.s 0x32
0x4384  ldstr    aSpapplicationa_36// "SPApplicationAuthenticationModule: App "...
0x4389  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x438e  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity::.ctor()
0x4393  stloc.s  4
0x4395  ldloc.0
0x4396  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x439b  ldstr    aTid// "tid"
0x43a0  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x43a5  stloc.s  5
0x43a7  ldloc.0
0x43a8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x43ad  ldstr    aClientappid// "clientappid"
0x43b2  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x43b7  stloc.s  6
0x43b9  ldloc.2
0x43ba  brfalse.s loc_4417
0x43bc  ldloc.3
0x43bd  brfalse.s loc_4417
0x43bf  ldloc.s  5
0x43c1  brtrue.s loc_43EB
0x43c3  ldc.i4   0x141B863
0x43c8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x43cd  ldc.i4.s 0x32
0x43cf  ldstr    aSpapplicationa_21// "SPApplicationAuthenticationModule: Tena"...
0x43d4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x43d9  ldloc.1
0x43da  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x43df  ldstr    aTid// "tid"
0x43e4  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x43e9  stloc.s  5
0x43eb  ldloc.s  6
0x43ed  brtrue.s loc_4417
0x43ef  ldc.i4   0x141B880
0x43f4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x43f9  ldc.i4.s 0x32
0x43fb  ldstr    aSpapplicationa_37// "SPApplicationAuthenticationModule: Clie"...
0x4400  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4405  ldloc.1
0x4406  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x440b  ldstr    aClientappid// "clientappid"
0x4410  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x4415  stloc.s  6
0x4417  ldloc.s  4
0x4419  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x441e  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_NameId()
0x4423  ldloc.s  6
0x4425  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x442a  ldstr    asc_350C2// "@"
0x442f  ldloc.s  5
0x4431  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x4436  call     string [mscorlib]System.String::Concat(string, string, string)
0x443b  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string)
0x4440  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x4445  ldloc.s  4
0x4447  stloc.1
0x4448  br.s     loc_4460
0x444a  ldc.i4   0x10638CD
0x444f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4454  ldc.i4.s 0x32
0x4456  ldstr    aSpapplicationa_38// "SPApplicationAuthenticationModule: This"...
0x445b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4460  ldloc.1
0x4461  brfalse.s loc_44A4
0x4463  ldc.i4   0x2563D4
0x4468  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x446d  ldc.i4.s 0x32
0x446f  ldstr    aSpapplicationa_39// "SPApplicationAuthenticationModule: Inco"...
0x4474  ldc.i4.1
0x4475  newarr   [mscorlib]System.Object
0x447a  stloc.s  9
0x447c  ldloc.s  9
0x447e  ldc.i4.0
0x447f  ldloc.1
0x4480  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x4485  stelem.ref
0x4486  ldloc.s  9
0x4488  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x448d  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x4492  ldloc.1
0x4493  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CreateLocalActorIdentity(class [System]System.Uri contextUri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity incomingActorIdentity)
0x4498  stloc.s  7
0x449a  ldarg.0
0x449b  ldloc.s  7
0x449d  call     instance void Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::AttachActorIdentityToThread(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity actorIdentity)
0x44a2  br.s     loc_44BA
0x44a4  ldc.i4   0x2563D5
0x44a9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x44ae  ldc.i4.s 0x32
0x44b0  ldstr    aSpapplicationa_25// "SPApplicationAuthenticationModule: Inco"...
0x44b5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x44ba  ldc.i4.1
0x44bb  ret
```
