# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsAppPlusUserWopiToken

- ea: `0x15000`
- end: `0x15085`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsAppPlusUserWopiToken`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x16b90`

## callees

- `0x50d0`
- `0x15000`
- `0x28110`

## string_xrefs

- `0x15019`: `token`
- `0x1502e`: `ConsolidateWopiTokens`
- `0x1500f`: `token is null.`
- `0x1504d`: `IsAppPlusUserWopiToken: wopitokentype: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15000  ldarg.0
0x15001  brtrue.s loc_15024
0x15003  ldc.i4   0x111E543
0x15008  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1500d  ldc.i4.s 0x14
0x1500f  ldstr    aTokenIsNull// "token is null."
0x15014  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15019  ldstr    aToken// "token"
0x1501e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x15023  throw
0x15024  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::WopiTokenConsolidationFeature
0x15029  ldstr    a04192016// "04/19/2016"
0x1502e  ldstr    aConsolidatewop// "ConsolidateWopiTokens"
0x15033  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x15038  brtrue.s loc_15073
0x1503a  ldarg.0
0x1503b  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenType Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetWopiTokenType(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x15040  stloc.0
0x15041  ldc.i4   0x11D3752
0x15046  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1504b  ldc.i4.s 0x32
0x1504d  ldstr    aIsappplususerw_0// "IsAppPlusUserWopiToken: wopitokentype: "...
0x15052  ldc.i4.1
0x15053  newarr   [mscorlib]System.Object
0x15058  stloc.2
0x15059  ldloc.2
0x1505a  ldc.i4.0
0x1505b  ldloc.0
0x1505c  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenType
0x15061  callvirt instance string [mscorlib]System.Object::ToString()
0x15066  stelem.ref
0x15067  ldloc.2
0x15068  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1506d  ldloc.0
0x1506e  ldc.i4.1
0x1506f  bne.un.s loc_15073
0x15071  ldc.i4.1
0x15072  ret
0x15073  ldc.i4.0
0x15074  stloc.1
0x15075  ldarg.0
0x15076  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::AppPlusUserWopiTokenClaimType
0x1507b  ldloca.s 1
0x1507d  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryReadBooleanValueClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType, [out] bool& booleanClaimValue)
0x15082  pop
0x15083  ldloc.1
0x15084  ret
```
