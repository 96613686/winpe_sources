# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::CreateIdentityTokenString

- ea: `0x10190`
- end: `0x1021e`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::CreateIdentityTokenString`
- size: `142`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf950`
- `0xfa00`
- `0xfb30`
- `0xfbf0`

## callees

- `0x10190`
- `0x13200`
- `0x13450`

## string_xrefs

- `0x101d1`: `http://www.w3.org/2001/04/xmldsig-more#hmac-sha256`
- `0x101d6`: `http://www.w3.org/2001/04/xmlenc#sha256`
- `0x101a6`: `securityKey`
- `0x101fe`: `SPIdentityProofTokenManager: Issued Identity token. Token: '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x10190  ldarg.0
0x10191  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x10196  brfalse.s loc_101A3
0x10198  ldstr    aAudience// "audience"
0x1019d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x101a2  throw
0x101a3  ldarg.1
0x101a4  brtrue.s loc_101B1
0x101a6  ldstr    aSecuritykey// "securityKey"
0x101ab  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x101b0  throw
0x101b1  ldarg.2
0x101b2  brtrue.s loc_101BF
0x101b4  ldstr    aClaims// "claims"
0x101b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x101be  throw
0x101bf  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x101c4  stloc.0
0x101c5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x101ca  stloc.1
0x101cb  ldloc.0
0x101cc  ldarg.0
0x101cd  ldloc.1
0x101ce  ldarg.3
0x101cf  ldarg.2
0x101d0  ldarg.1
0x101d1  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/04/xmldsig-more#"...
0x101d6  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/04/xmlenc#sha256"
0x101db  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SigningCredentials::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey, string, string)
0x101e0  newobj   instance void Microsoft.SharePoint.IdentityModel.SPIntegerDatesWritingJsonWebSecurityToken::.ctor(string issuer, string audience, valuetype [mscorlib]System.DateTime validFrom, valuetype [mscorlib]System.DateTime validTo, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims, class [System.IdentityModel]System.IdentityModel.Tokens.SigningCredentials signingCredentials)
0x101e5  stloc.2
0x101e6  newobj   instance void Microsoft.SharePoint.IdentityModel.SPIntegerDatesWritingJsonWebSecurityTokenHandler::.ctor()
0x101eb  ldloc.2
0x101ec  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::WriteTokenAsString(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x101f1  stloc.3
0x101f2  ldc.i4   0x35F7C6
0x101f7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x101fc  ldc.i4.s 0x32
0x101fe  ldstr    aSpidentityproo_16// "SPIdentityProofTokenManager: Issued Ide"...
0x10203  ldc.i4.1
0x10204  newarr   [mscorlib]System.Object
0x10209  stloc.s  4
0x1020b  ldloc.s  4
0x1020d  ldc.i4.0
0x1020e  ldloc.3
0x1020f  call     string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHelper::GetSafeForLoggingTokenString(string)
0x10214  stelem.ref
0x10215  ldloc.s  4
0x10217  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1021c  ldloc.3
0x1021d  ret
```
