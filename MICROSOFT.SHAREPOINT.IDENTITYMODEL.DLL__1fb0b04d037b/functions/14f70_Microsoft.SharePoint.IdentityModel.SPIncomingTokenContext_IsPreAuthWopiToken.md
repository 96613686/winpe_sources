# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsPreAuthWopiToken

- ea: `0x14f70`
- end: `0x14ff5`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsPreAuthWopiToken`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x16b90`

## callees

- `0x50d0`
- `0x14f70`
- `0x28110`

## string_xrefs

- `0x14f89`: `token`
- `0x14f9e`: `ConsolidateWopiTokens`
- `0x14f7f`: `token is null.`
- `0x14fbd`: `IsPreAuthWopiToken: wopitokentype: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x14f70  ldarg.0
0x14f71  brtrue.s loc_14F94
0x14f73  ldc.i4   0x100184E
0x14f78  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14f7d  ldc.i4.s 0x14
0x14f7f  ldstr    aTokenIsNull// "token is null."
0x14f84  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14f89  ldstr    aToken// "token"
0x14f8e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14f93  throw
0x14f94  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::WopiTokenConsolidationFeature
0x14f99  ldstr    a04192016// "04/19/2016"
0x14f9e  ldstr    aConsolidatewop// "ConsolidateWopiTokens"
0x14fa3  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x14fa8  brtrue.s loc_14FE3
0x14faa  ldarg.0
0x14fab  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenType Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetWopiTokenType(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x14fb0  stloc.0
0x14fb1  ldc.i4   0x11D3751
0x14fb6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14fbb  ldc.i4.s 0x32
0x14fbd  ldstr    aIspreauthwopit// "IsPreAuthWopiToken: wopitokentype: {0}"
0x14fc2  ldc.i4.1
0x14fc3  newarr   [mscorlib]System.Object
0x14fc8  stloc.2
0x14fc9  ldloc.2
0x14fca  ldc.i4.0
0x14fcb  ldloc.0
0x14fcc  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenType
0x14fd1  callvirt instance string [mscorlib]System.Object::ToString()
0x14fd6  stelem.ref
0x14fd7  ldloc.2
0x14fd8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x14fdd  ldloc.0
0x14fde  ldc.i4.2
0x14fdf  bne.un.s loc_14FE3
0x14fe1  ldc.i4.1
0x14fe2  ret
0x14fe3  ldc.i4.0
0x14fe4  stloc.1
0x14fe5  ldarg.0
0x14fe6  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::PreAuthTokenClaimType
0x14feb  ldloca.s 1
0x14fed  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryReadBooleanValueClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType, [out] bool& booleanClaimValue)
0x14ff2  pop
0x14ff3  ldloc.1
0x14ff4  ret
```
