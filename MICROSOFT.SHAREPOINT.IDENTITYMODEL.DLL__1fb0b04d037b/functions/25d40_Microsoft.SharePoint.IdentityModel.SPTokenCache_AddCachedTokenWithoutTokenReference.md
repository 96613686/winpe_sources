# Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedTokenWithoutTokenReference

- ea: `0x25d40`
- end: `0x25dbc`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedTokenWithoutTokenReference`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x22d70`
- `0x25990`
- `0x25d40`

## string_xrefs

- `0x25d4f`: `AddCachedTokenWithoutTokenReference: Failed to find a new sessionToken.`
- `0x25d59`: `sessionToken`
- `0x25d80`: `AddCachedTokenWithoutTokenReference: No token reference in claims identity on session token.`
- `0x25da1`: `AddCachedTokenWithoutTokenReference: Failed to remove token reference claim from the new session token.`

## pseudocode

```c

```

## disassembly

```asm
0x25d40  ldarg.1
0x25d41  brtrue.s loc_25D64
0x25d43  ldc.i4   0x121B35D
0x25d48  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25d4d  ldc.i4.s 0xA
0x25d4f  ldstr    aAddcachedtoken// "AddCachedTokenWithoutTokenReference: Fa"...
0x25d54  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25d59  ldstr    aSessiontoken// "sessionToken"
0x25d5e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x25d63  throw
0x25d64  ldarg.0
0x25d65  ldarg.1
0x25d66  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_TokenReference()
0x25d6b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSingleClaimFromToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken, string claimType)
0x25d70  dup
0x25d71  stloc.0
0x25d72  brtrue.s loc_25D8C
0x25d74  ldc.i4   0x121B35E
0x25d79  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25d7e  ldc.i4.s 0x32
0x25d80  ldstr    aAddcachedtoken_0// "AddCachedTokenWithoutTokenReference: No"...
0x25d85  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25d8a  br.s     loc_25DAB
0x25d8c  ldarg.1
0x25d8d  ldloc.0
0x25d8e  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSessionSecurityTokenExtensions::TryRemoveClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x25d93  brtrue.s loc_25DAB
0x25d95  ldc.i4   0x121B35F
0x25d9a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25d9f  ldc.i4.s 0xA
0x25da1  ldstr    aAddcachedtoken_1// "AddCachedTokenWithoutTokenReference: Fa"...
0x25da6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25dab  ldarg.1
0x25dac  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x25db1  stloc.1
0x25db2  ldarg.0
0x25db3  ldarg.2
0x25db4  ldarg.3
0x25db5  ldloc.1
0x25db6  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedToken(string subscriptionId, string identity, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry value)
0x25dbb  ret
```
