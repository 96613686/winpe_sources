# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetIncomingApplicationScope

- ea: `0x4e90`
- end: `0x4f4a`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetIncomingApplicationScope`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3bb0`

## callees

- `0x4e90`
- `0x4f50`
- `0x28920`

## string_xrefs

- `0x4ea7`: `SPApplicationAuthenticationModule token doesn't have scope claim`
- `0x4ebc`: `Use of SPIncomingApplicationContext`
- `0x4f2e`: `SPApplicationAuthenticationModule token doesn't have appIdClaim claim`

## pseudocode

```c

```

## disassembly

```asm
0x4e90  ldarg.0
0x4e91  ldarg.1
0x4e92  call     instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::GetApplicationContextClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x4e97  stloc.0
0x4e98  ldloc.0
0x4e99  brtrue.s loc_4EB2
0x4e9b  ldc.i4   0x25919A
0x4ea0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4ea5  ldc.i4.s 0x64
0x4ea7  ldstr    aSpapplicationa_69// "SPApplicationAuthenticationModule token"...
0x4eac  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4eb1  ret
0x4eb2  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOAuthNativeClientAuthenticationService::MsTeamsAppIdKillSwitch
0x4eb7  ldstr    a4162018// "4/16/2018"
0x4ebc  ldstr    aUseOfSpincomin// "Use of SPIncomingApplicationContext"
0x4ec1  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x4ec6  brfalse.s loc_4F39
0x4ec8  ldc.i4   0x3BDD
0x4ecd  ldc.i4.3
0x4ece  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility::IsCodeEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility/FlightEnvironment)
0x4ed3  brfalse.s loc_4F49
0x4ed5  ldarg.1
0x4ed6  ldstr    aAppid// "appid"
0x4edb  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x4ee0  stloc.1
0x4ee1  ldloc.1
0x4ee2  brfalse.s loc_4F22
0x4ee4  ldc.i4   0x21602A0
0x4ee9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4eee  ldc.i4.s 0x32
0x4ef0  ldstr    aSpapplicationa_70// "SPApplicationAuthenticationModule has t"...
0x4ef5  ldc.i4.1
0x4ef6  newarr   [mscorlib]System.Object
0x4efb  stloc.2
0x4efc  ldloc.2
0x4efd  ldc.i4.0
0x4efe  ldloc.1
0x4eff  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4f04  stelem.ref
0x4f05  ldloc.2
0x4f06  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x4f0b  ldloc.0
0x4f0c  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4f11  ldloc.1
0x4f12  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4f17  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingApplicationContext::.ctor(string, string)
0x4f1c  call     T0x2B00000B
0x4f21  ret
0x4f22  ldc.i4   0x21602A1
0x4f27  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4f2c  ldc.i4.s 0x32
0x4f2e  ldstr    aSpapplicationa_71// "SPApplicationAuthenticationModule token"...
0x4f33  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4f38  ret
0x4f39  ldloc.0
0x4f3a  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4f3f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingApplicationContext::.ctor(string)
0x4f44  call     T0x2B00000B
0x4f49  ret
```
