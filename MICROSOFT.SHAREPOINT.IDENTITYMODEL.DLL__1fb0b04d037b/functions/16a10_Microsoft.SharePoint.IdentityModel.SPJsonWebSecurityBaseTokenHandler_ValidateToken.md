# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateToken

- ea: `0x16a10`
- end: `0x16b14`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateToken`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18370`
- `0x183e0`

## callees

- `0x10da0`
- `0x118a0`
- `0x169b0`
- `0x169c0`
- `0x16a10`
- `0x16b20`
- `0x16b90`
- `0x16e80`
- `0x17070`
- `0x176e0`
- `0x283e0`
- `0x28530`

## string_xrefs

- `0x16a29`: `token`
- `0x16a1f`: `The token is null.`

## pseudocode

```c

```

## disassembly

```asm
0x16a10  ldarg.1
0x16a11  brtrue.s loc_16A34
0x16a13  ldc.i4   0x6503DC
0x16a18  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16a1d  ldc.i4.s 0xA
0x16a1f  ldstr    aTheTokenIsNull// "The token is null."
0x16a24  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16a29  ldstr    aToken// "token"
0x16a2e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16a33  throw
0x16a34  ldarg.0
0x16a35  ldarg.1
0x16a36  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x16a3b  stloc.0
0x16a3c  ldloc.0
0x16a3d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity> [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::GetEnumerator()
0x16a42  stloc.s  4
0x16a44  br.s     loc_16A56
0x16a46  ldloc.s  4
0x16a48  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity>::get_Current()
0x16a4d  stloc.1
0x16a4e  ldarg.0
0x16a4f  ldloc.1
0x16a50  ldarg.1
0x16a51  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::SetBootstrapToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token)
0x16a56  ldloc.s  4
0x16a58  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16a5d  brtrue.s loc_16A46
0x16a5f  leave.s  loc_16A6D
0x16a61  ldloc.s  4
0x16a63  brfalse.s loc_16A6C
0x16a65  ldloc.s  4
0x16a67  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16a6c  endfinally
0x16a6d  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::IsEnableOldHashedProofTokenFormat()
0x16a72  brtrue.s loc_16A92
0x16a74  ldarg.1
0x16a75  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x16a7a  stloc.2
0x16a7b  ldarg.0
0x16a7c  ldloc.2
0x16a7d  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x16a82  ldloc.2
0x16a83  call     bool Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::IsHashedProofToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x16a88  brfalse.s loc_16A9E
0x16a8a  ldloc.2
0x16a8b  call     void Microsoft.SharePoint.IdentityModel.SPClaimsUtility::VerifyProofTokenEndPointUrl(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken identityToken)
0x16a90  br.s     loc_16A9E
0x16a92  ldarg.0
0x16a93  ldarg.1
0x16a94  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x16a99  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x16a9e  ldc.i4.1
0x16a9f  ldarg.0
0x16aa0  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Mode()
0x16aa5  bne.un.s loc_16AC3
0x16aa7  ldloca.s 0
0x16aa9  call     void Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateAndEnsureIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection& result)
0x16aae  ldarg.0
0x16aaf  ldarg.1
0x16ab0  ldloc.0
0x16ab1  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateActorIsSelfIssuer(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection tokenIdentities)
0x16ab6  ldarg.1
0x16ab7  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x16abc  call     void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateActor(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken identity)
0x16ac1  br.s     loc_16B12
0x16ac3  ldc.i4.2
0x16ac4  ldarg.0
0x16ac5  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Mode()
0x16aca  bne.un.s loc_16ADD
0x16acc  ldarg.1
0x16acd  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x16ad2  stloc.3
0x16ad3  ldarg.0
0x16ad4  ldloc.3
0x16ad5  ldloc.0
0x16ad6  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateLackOfActorAndIdentityCount(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection tokenIdentities)
0x16adb  br.s     loc_16B12
0x16add  ldc.i4   0x809354
0x16ae2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16ae7  ldc.i4.s 0xA
0x16ae9  ldstr    aModePropertyIs// "Mode property is not set to a handled v"...
0x16aee  ldc.i4.1
0x16aef  newarr   [mscorlib]System.Object
0x16af4  stloc.s  5
0x16af6  ldloc.s  5
0x16af8  ldc.i4.0
0x16af9  ldarg.0
0x16afa  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Mode()
0x16aff  box      Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode
0x16b04  stelem.ref
0x16b05  ldloc.s  5
0x16b07  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16b0c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x16b11  throw
0x16b12  ldloc.0
0x16b13  ret
```
