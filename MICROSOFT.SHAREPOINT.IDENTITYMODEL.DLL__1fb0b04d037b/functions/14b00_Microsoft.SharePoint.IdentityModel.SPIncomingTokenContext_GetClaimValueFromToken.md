# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromToken

- ea: `0x14b00`
- end: `0x14bb6`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromToken`
- size: `182`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x149b0`
- `0x14a60`
- `0x14bc0`
- `0x14cb0`
- `0x28110`

## callees

- `0x14b00`

## string_xrefs

- `0x14b0f`: `token is null.`
- `0x14b68`: `Did not find token claim in token. ClaimType: '{0}'.`
- `0x14b8c`: `Found claim with value in token. ClaimType: '{0}' Value: '{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x14b00  ldarg.0
0x14b01  brtrue.s loc_14B1B
0x14b03  ldc.i4   0x100184B
0x14b08  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14b0d  ldc.i4.s 0x14
0x14b0f  ldstr    aTokenIsNull// "token is null."
0x14b14  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14b19  ldnull
0x14b1a  ret
0x14b1b  ldnull
0x14b1c  stloc.0
0x14b1d  ldarg.0
0x14b1e  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x14b23  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim>::GetEnumerator()
0x14b28  stloc.2
0x14b29  br.s     loc_14B45
0x14b2b  ldloc.2
0x14b2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim>::get_Current()
0x14b31  stloc.1
0x14b32  ldloc.1
0x14b33  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_ClaimType()
0x14b38  ldarg.1
0x14b39  ldc.i4.4
0x14b3a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x14b3f  brfalse.s loc_14B45
0x14b41  ldloc.1
0x14b42  stloc.0
0x14b43  br.s     loc_14B4D
0x14b45  ldloc.2
0x14b46  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14b4b  brtrue.s loc_14B2B
0x14b4d  leave.s  loc_14B59
0x14b4f  ldloc.2
0x14b50  brfalse.s loc_14B58
0x14b52  ldloc.2
0x14b53  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14b58  endfinally
0x14b59  ldloc.0
0x14b5a  brtrue.s loc_14B80
0x14b5c  ldc.i4   0x100184C
0x14b61  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14b66  ldc.i4.s 0x14
0x14b68  ldstr    aDidNotFindToke// "Did not find token claim in token. Clai"...
0x14b6d  ldc.i4.1
0x14b6e  newarr   [mscorlib]System.Object
0x14b73  stloc.3
0x14b74  ldloc.3
0x14b75  ldc.i4.0
0x14b76  ldarg.1
0x14b77  stelem.ref
0x14b78  ldloc.3
0x14b79  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x14b7e  ldnull
0x14b7f  ret
0x14b80  ldc.i4   0x100184D
0x14b85  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14b8a  ldc.i4.s 0x32
0x14b8c  ldstr    aFoundClaimWith// "Found claim with value in token. ClaimT"...
0x14b91  ldc.i4.2
0x14b92  newarr   [mscorlib]System.Object
0x14b97  stloc.s  4
0x14b99  ldloc.s  4
0x14b9b  ldc.i4.0
0x14b9c  ldarg.1
0x14b9d  stelem.ref
0x14b9e  ldloc.s  4
0x14ba0  ldc.i4.1
0x14ba1  ldloc.0
0x14ba2  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x14ba7  stelem.ref
0x14ba8  ldloc.s  4
0x14baa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x14baf  ldloc.0
0x14bb0  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x14bb5  ret
```
