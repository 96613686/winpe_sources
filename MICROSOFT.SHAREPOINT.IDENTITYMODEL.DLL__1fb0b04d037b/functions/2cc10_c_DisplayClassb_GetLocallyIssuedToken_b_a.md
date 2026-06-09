# <>c__DisplayClassb::<GetLocallyIssuedToken>b__a

- ea: `0x2cc10`
- end: `0x2cd2f`
- name: `<>c__DisplayClassb::<GetLocallyIssuedToken>b__a`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xba40`
- `0x22ae0`
- `0x2cc10`

## string_xrefs

- `0x2cc7b`: `SPApplicationAuthenticationModule: Incoming token doesn't have user identity.`
- `0x2ccf3`: `SPApplicationAuthenticationModule: Calling AuthenticateSessionSecurityToken`
- `0x2cd1a`: `SPApplicationAuthenticationModule: Calling WriteToken`
- `0x2cc93`: `SPApplicationAuthenticationModule: Removing Actor from incoming token.`

## pseudocode

```c

```

## disassembly

```asm
0x2cc10  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x2cc15  stloc.0
0x2cc16  ldloc.0
0x2cc17  ldarg.0
0x2cc18  ldfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken <>c__DisplayClassb::token
0x2cc1d  ldc.i4.0
0x2cc1e  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::SecurityTokenForApplicationAuthentication(class [System]System.Uri, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, bool)
0x2cc23  stloc.1
0x2cc24  ldc.i4   0x1D16C1
0x2cc29  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2cc2e  ldc.i4.s 0x64
0x2cc30  ldstr    aSpapplicationa_52// "SPApplicationAuthenticationModule: Call"...
0x2cc35  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2cc3a  ldloc.1
0x2cc3b  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::AuthenticateUser(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken)
0x2cc40  stloc.2
0x2cc41  ldc.i4   0x29BA
0x2cc46  ldc.i4.3
0x2cc47  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility::IsCodeEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility/FlightEnvironment)
0x2cc4c  brfalse.s loc_2CCBC
0x2cc4e  ldloc.2
0x2cc4f  brfalse.s loc_2CCA6
0x2cc51  ldloc.2
0x2cc52  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x2cc57  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x2cc5c  ldc.i4.0
0x2cc5d  ble.s    loc_2CCA6
0x2cc5f  ldloc.2
0x2cc60  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x2cc65  ldc.i4.0
0x2cc66  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x2cc6b  stloc.3
0x2cc6c  ldloc.3
0x2cc6d  brtrue.s loc_2CC87
0x2cc6f  ldc.i4   0x782441
0x2cc74  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2cc79  ldc.i4.s 0x32
0x2cc7b  ldstr    aSpapplicationa_19// "SPApplicationAuthenticationModule: Inco"...
0x2cc80  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2cc85  br.s     loc_2CCBC
0x2cc87  ldc.i4   0x782442
0x2cc8c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2cc91  ldc.i4.s 0x32
0x2cc93  ldstr    aSpapplicationa_76// "SPApplicationAuthenticationModule: Remo"...
0x2cc98  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2cc9d  ldloc.3
0x2cc9e  ldnull
0x2cc9f  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::set_Actor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x2cca4  br.s     loc_2CCBC
0x2cca6  ldc.i4   0x782443
0x2ccab  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2ccb0  ldc.i4.s 0x32
0x2ccb2  ldstr    aCanTGetUseride// "Can't get userIdentity from claimsPrinc"...
0x2ccb7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2ccbc  ldloc.2
0x2ccbd  ldnull
0x2ccbe  ldloc.1
0x2ccbf  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x2ccc4  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x2ccc9  ldloc.1
0x2ccca  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x2cccf  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x2ccd4  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal, string, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x2ccd9  stloc.s  4
0x2ccdb  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_SessionAuthenticationModule()
0x2cce0  isinst   Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule
0x2cce5  stloc.s  5
0x2cce7  ldc.i4   0x1D16C3
0x2ccec  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2ccf1  ldc.i4.s 0x64
0x2ccf3  ldstr    aSpapplicationa_53// "SPApplicationAuthenticationModule: Call"...
0x2ccf8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2ccfd  ldloc.s  5
0x2ccff  ldloc.s  4
0x2cd01  ldc.i4.0
0x2cd02  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::AuthenticateSessionSecurityToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken, bool)
0x2cd07  call     class Microsoft.SharePoint.IdentityModel.SPTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_Current()
0x2cd0c  stloc.s  6
0x2cd0e  ldc.i4   0x1D16C5
0x2cd13  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2cd18  ldc.i4.s 0x64
0x2cd1a  ldstr    aSpapplicationa_54// "SPApplicationAuthenticationModule: Call"...
0x2cd1f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2cd24  ldloc.s  6
0x2cd26  ldloc.s  4
0x2cd28  callvirt instance unsigned int8[] [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityTokenHandler::WriteToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken)
0x2cd2d  pop
0x2cd2e  ret
```
