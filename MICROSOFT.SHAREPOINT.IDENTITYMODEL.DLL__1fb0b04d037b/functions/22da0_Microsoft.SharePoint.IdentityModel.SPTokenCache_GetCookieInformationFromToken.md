# Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCookieInformationFromToken

- ea: `0x22da0`
- end: `0x22e80`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCookieInformationFromToken`
- size: `224`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x22e80`
- `0x22ed0`
- `0x24840`
- `0x25570`

## callees

- `0x20660`
- `0x20b10`
- `0x22d70`
- `0x22da0`
- `0x28160`

## string_xrefs

- `0x22dc5`: `Token Cache: No token reference in claims identity on session token.`
- `0x22ded`: `Token Cache: No token reference value in claims identity on session token.`
- `0x22e14`: `Token Cache: Could not get cookie value handler.`
- `0x22e3c`: `Token Cache: Could not parse token reference.`
- `0x22e57`: `Token Cache: Got cookie information for user token. Username: <name>'{0}'</name>.`

## pseudocode

```c

```

## disassembly

```asm
0x22da0  ldc.i4.0
0x22da1  stloc.0
0x22da2  ldarg.0
0x22da3  ldarg.1
0x22da4  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_TokenReference()
0x22da9  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSingleClaimFromToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken, string claimType)
0x22dae  stloc.1
0x22daf  ldarg.3
0x22db0  ldnull
0x22db1  stind.ref
0x22db2  ldarg.s  4
0x22db4  ldnull
0x22db5  stind.ref
0x22db6  ldloc.1
0x22db7  brtrue.s loc_22DD4
0x22db9  ldc.i4   0x55570D
0x22dbe  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22dc3  ldc.i4.s 0xA
0x22dc5  ldstr    aTokenCacheNoTo// "Token Cache: No token reference in clai"...
0x22dca  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x22dcf  br       loc_22E7E
0x22dd4  ldloc.1
0x22dd5  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x22dda  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22ddf  brfalse.s loc_22DFC
0x22de1  ldc.i4   0x55570E
0x22de6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22deb  ldc.i4.s 0xA
0x22ded  ldstr    aTokenCacheNoTo_0// "Token Cache: No token reference value i"...
0x22df2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x22df7  br       loc_22E7E
0x22dfc  ldarg.3
0x22dfd  call     class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetCookieValueHandler()
0x22e02  dup
0x22e03  stloc.2
0x22e04  stind.ref
0x22e05  ldloc.2
0x22e06  brtrue.s loc_22E20
0x22e08  ldc.i4   0x55570F
0x22e0d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22e12  ldc.i4.s 0xA
0x22e14  ldstr    aTokenCacheCoul_1// "Token Cache: Could not get cookie value"...
0x22e19  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x22e1e  br.s     loc_22E7E
0x22e20  ldarg.3
0x22e21  ldind.ref
0x22e22  ldloc.1
0x22e23  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x22e28  ldarg.2
0x22e29  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::Initialize(string cookieValue, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValueOption options)
0x22e2e  brtrue.s loc_22E4B
0x22e30  ldc.i4   0x555710
0x22e35  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22e3a  ldc.i4.s 0xA
0x22e3c  ldstr    aTokenCacheCoul_2// "Token Cache: Could not parse token refe"...
0x22e41  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x22e46  ldarg.3
0x22e47  ldnull
0x22e48  stind.ref
0x22e49  br.s     loc_22E7E
0x22e4b  ldc.i4   0x555711
0x22e50  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22e55  ldc.i4.s 0x64
0x22e57  ldstr    aTokenCacheGotC// "Token Cache: Got cookie information for"...
0x22e5c  ldc.i4.1
0x22e5d  newarr   [mscorlib]System.Object
0x22e62  stloc.3
0x22e63  ldloc.3
0x22e64  ldc.i4.0
0x22e65  ldarg.3
0x22e66  ldind.ref
0x22e67  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x22e6c  stelem.ref
0x22e6d  ldloc.3
0x22e6e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22e73  ldarg.s  4
0x22e75  ldloc.1
0x22e76  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x22e7b  stind.ref
0x22e7c  ldc.i4.1
0x22e7d  stloc.0
0x22e7e  ldloc.0
0x22e7f  ret
```
