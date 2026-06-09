# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::BlockPreAuthProofToken

- ea: `0x2420`
- end: `0x24bb`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::BlockPreAuthProofToken`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2370`

## callees

- `0x2420`
- `0x1bf90`

## string_xrefs

- `0x242a`: `SPPOP_AuthBlockPreAuthProofToken`
- `0x247d`: `ProofTokenSignIn: Token is pre-auth proof token so throwing`
- `0x2499`: `ProofTokenSignIn: Token is not pre-auth proof token.`
- `0x24b0`: `ProofTokenSignIn: Identity Token is null.`

## pseudocode

```c

```

## disassembly

```asm
0x2420  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::BlockPreAuthProofTokenKillSwitchId
0x2425  ldstr    a01242017// "01/24/2017"
0x242a  ldstr    aSppopAuthblock// "SPPOP_AuthBlockPreAuthProofToken"
0x242f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x2434  brtrue   loc_24BA
0x2439  ldarg.1
0x243a  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_IdentityToken()
0x243f  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x2444  stloc.0
0x2445  ldloc.0
0x2446  brfalse.s loc_24A4
0x2448  ldloc.0
0x2449  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x244e  brfalse.s loc_24A4
0x2450  ldloc.0
0x2451  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x2456  ldstr    aEndpointurl// "endpointurl"
0x245b  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x2460  stloc.1
0x2461  ldloc.1
0x2462  brfalse.s loc_248D
0x2464  ldloc.1
0x2465  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x246a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x246f  brtrue.s loc_248D
0x2471  ldc.i4   0x1463241
0x2476  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x247b  ldc.i4.s 0xA
0x247d  ldstr    aProoftokensign_23// "ProofTokenSignIn: Token is pre-auth pro"...
0x2482  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2487  newobj   instance void [mscorlib]System.Exception::.ctor()
0x248c  throw
0x248d  ldc.i4   0x1463242
0x2492  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2497  ldc.i4.s 0x32
0x2499  ldstr    aProoftokensign_24// "ProofTokenSignIn: Token is not pre-auth"...
0x249e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24a3  ret
0x24a4  ldc.i4   0x1463243
0x24a9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x24ae  ldc.i4.s 0xA
0x24b0  ldstr    aProoftokensign_25// "ProofTokenSignIn: Identity Token is nul"...
0x24b5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24ba  ret
```
