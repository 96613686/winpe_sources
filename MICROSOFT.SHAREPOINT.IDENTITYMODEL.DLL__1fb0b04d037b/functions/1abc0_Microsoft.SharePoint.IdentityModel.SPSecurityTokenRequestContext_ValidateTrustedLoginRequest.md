# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::ValidateTrustedLoginRequest

- ea: `0x1abc0`
- end: `0x1acb3`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::ValidateTrustedLoginRequest`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19df0`

## callees

- `0x198e0`
- `0x198f0`
- `0x19950`
- `0x1abc0`

## string_xrefs

- `0x1ac40`: `Trusted login provider is not sending configured input identity claim type. ProviderName: '{0}', InputClaimType: '{1}'.`
- `0x1ac92`: `TrustedSecurityTokenDoesNotContainIdentityClaim`

## pseudocode

```c

```

## disassembly

```asm
0x1abc0  ldarg.1
0x1abc1  brfalse.s loc_1AC1A
0x1abc3  ldarg.1
0x1abc4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1abc9  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_IsOAuthRequest()
0x1abce  stloc.1
0x1abcf  ldloca.s 1
0x1abd1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1abd6  brfalse.s loc_1AC1A
0x1abd8  ldarg.1
0x1abd9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1abde  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_IsOAuthRequest()
0x1abe3  stloc.2
0x1abe4  ldloca.s 2
0x1abe6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1abeb  brfalse.s loc_1AC1A
0x1abed  ldc.i4   0x11D100C
0x1abf2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1abf7  ldc.i4.s 0x64
0x1abf9  ldstr    aTrustedLoginPr// "Trusted login provider is sending an oa"...
0x1abfe  ldc.i4.1
0x1abff  newarr   [mscorlib]System.Object
0x1ac04  stloc.3
0x1ac05  ldloc.3
0x1ac06  ldc.i4.0
0x1ac07  ldarg.0
0x1ac08  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_TrustedLoginProvider()
0x1ac0d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x1ac12  stelem.ref
0x1ac13  ldloc.3
0x1ac14  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1ac19  ret
0x1ac1a  ldarg.0
0x1ac1b  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Identity()
0x1ac20  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1ac25  ldarg.0
0x1ac26  call     instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_LogonIdentityClaimType()
0x1ac2b  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1ac30  stloc.0
0x1ac31  ldloc.0
0x1ac32  brtrue.s loc_1ACB2
0x1ac34  ldc.i4   0x11D100D
0x1ac39  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1ac3e  ldc.i4.s 0xF
0x1ac40  ldstr    aTrustedLoginPr_0// "Trusted login provider is not sending c"...
0x1ac45  ldc.i4.2
0x1ac46  newarr   [mscorlib]System.Object
0x1ac4b  stloc.s  4
0x1ac4d  ldloc.s  4
0x1ac4f  ldc.i4.0
0x1ac50  ldarg.0
0x1ac51  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_TrustedLoginProvider()
0x1ac56  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x1ac5b  stelem.ref
0x1ac5c  ldloc.s  4
0x1ac5e  ldc.i4.1
0x1ac5f  ldarg.0
0x1ac60  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_TrustedLoginProvider()
0x1ac65  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase::get_IdentityClaimTypeInformation()
0x1ac6a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation::get_InputClaimType()
0x1ac6f  stelem.ref
0x1ac70  ldloc.s  4
0x1ac72  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1ac77  ldc.i4   0x17093CA
0x1ac7c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1ac81  ldc.i4.s 0xA
0x1ac83  ldstr    aThrowingFaultE// "Throwing fault exception because there "...
0x1ac88  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1ac8d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ac92  ldstr    aTrustedsecurit// "TrustedSecurityTokenDoesNotContainIdent"...
0x1ac97  ldc.i4.0
0x1ac98  newarr   [mscorlib]System.Object
0x1ac9d  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x1aca2  ldstr    aTrustedmissing// "TrustedMissingIdentityClaim"
0x1aca7  newobj   instance void [System.ServiceModel]System.ServiceModel.FaultCode::.ctor(string)
0x1acac  newobj   instance void [System.ServiceModel]System.ServiceModel.FaultException::.ctor(string, class [System.ServiceModel]System.ServiceModel.FaultCode)
0x1acb1  throw
0x1acb2  ret
```
