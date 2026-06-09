# Microsoft.SharePoint.IdentityModel.SPTokenCache::ValidateCookieReferenceToken

- ea: `0x253c0`
- end: `0x2556d`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ValidateCookieReferenceToken`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x25570`

## callees

- `0x22d70`
- `0x253c0`

## string_xrefs

- `0x253d1`: `Token Cache: The cookie token is null.`
- `0x253f6`: `Token Cache: The cookie token has null claims principal.`
- `0x25420`: `Token Cache: The cookie token has null claims identities.`
- `0x25450`: `Token Cache: The cookie token has incorrect identity count.`
- `0x25480`: `Token Cache: The cookie token has null claims identity.`
- `0x254b5`: `Token Cache: The cookie token claims identity has null claims.`
- `0x254f0`: `Token Cache: The cookie token claims identity has incorrect claim count. Count: '{0}'.`
- `0x25545`: `Token Cache: The cookie token identity does not have token reference claim.`
- `0x2555f`: `Token Cache: The cookie token appears valid.`

## pseudocode

```c

```

## disassembly

```asm
0x253c0  ldc.i4.0
0x253c1  stloc.0
0x253c2  ldarg.1
0x253c3  brtrue.s loc_253E2
0x253c5  ldc.i4   0x1192357
0x253ca  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x253cf  ldc.i4.s 0xA
0x253d1  ldstr    aTokenCacheTheC_6// "Token Cache: The cookie token is null."
0x253d6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x253db  ldc.i4.0
0x253dc  stloc.0
0x253dd  br       loc_2556B
0x253e2  ldarg.1
0x253e3  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x253e8  brtrue.s loc_25407
0x253ea  ldc.i4   0x1192358
0x253ef  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x253f4  ldc.i4.s 0xA
0x253f6  ldstr    aTokenCacheTheC_7// "Token Cache: The cookie token has null "...
0x253fb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25400  ldc.i4.0
0x25401  stloc.0
0x25402  br       loc_2556B
0x25407  ldarg.1
0x25408  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x2540d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x25412  brtrue.s loc_25431
0x25414  ldc.i4   0x1192359
0x25419  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2541e  ldc.i4.s 0xA
0x25420  ldstr    aTokenCacheTheC_8// "Token Cache: The cookie token has null "...
0x25425  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2542a  ldc.i4.0
0x2542b  stloc.0
0x2542c  br       loc_2556B
0x25431  ldarg.1
0x25432  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25437  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x2543c  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x25441  ldc.i4.1
0x25442  beq.s    loc_25461
0x25444  ldc.i4   0x119235A
0x25449  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2544e  ldc.i4.s 0xA
0x25450  ldstr    aTokenCacheTheC_9// "Token Cache: The cookie token has incor"...
0x25455  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2545a  ldc.i4.0
0x2545b  stloc.0
0x2545c  br       loc_2556B
0x25461  ldarg.1
0x25462  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25467  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x2546c  ldc.i4.0
0x2546d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x25472  brtrue.s loc_25491
0x25474  ldc.i4   0x119235B
0x25479  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2547e  ldc.i4.s 0xA
0x25480  ldstr    aTokenCacheTheC_10// "Token Cache: The cookie token has null "...
0x25485  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2548a  ldc.i4.0
0x2548b  stloc.0
0x2548c  br       loc_2556B
0x25491  ldarg.1
0x25492  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25497  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x2549c  ldc.i4.0
0x2549d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x254a2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x254a7  brtrue.s loc_254C6
0x254a9  ldc.i4   0x119235C
0x254ae  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x254b3  ldc.i4.s 0xA
0x254b5  ldstr    aTokenCacheTheC_11// "Token Cache: The cookie token claims id"...
0x254ba  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x254bf  ldc.i4.0
0x254c0  stloc.0
0x254c1  br       loc_2556B
0x254c6  ldarg.1
0x254c7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x254cc  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x254d1  ldc.i4.0
0x254d2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x254d7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x254dc  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::get_Count()
0x254e1  ldc.i4.1
0x254e2  beq.s    loc_25529
0x254e4  ldc.i4   0x119235D
0x254e9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x254ee  ldc.i4.s 0xA
0x254f0  ldstr    aTokenCacheTheC_12// "Token Cache: The cookie token claims id"...
0x254f5  ldc.i4.1
0x254f6  newarr   [mscorlib]System.Object
0x254fb  stloc.2
0x254fc  ldloc.2
0x254fd  ldc.i4.0
0x254fe  ldarg.1
0x254ff  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25504  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x25509  ldc.i4.0
0x2550a  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x2550f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x25514  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::get_Count()
0x25519  box      [mscorlib]System.Int32
0x2551e  stelem.ref
0x2551f  ldloc.2
0x25520  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25525  ldc.i4.0
0x25526  stloc.0
0x25527  br.s     loc_2556B
0x25529  ldarg.0
0x2552a  ldarg.1
0x2552b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_TokenReference()
0x25530  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSingleClaimFromToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken, string claimType)
0x25535  stloc.1
0x25536  ldloc.1
0x25537  brtrue.s loc_25553
0x25539  ldc.i4   0x119235E
0x2553e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25543  ldc.i4.s 0xA
0x25545  ldstr    aTokenCacheTheC_13// "Token Cache: The cookie token identity "...
0x2554a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2554f  ldc.i4.0
0x25550  stloc.0
0x25551  br.s     loc_2556B
0x25553  ldc.i4   0x119235F
0x25558  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2555d  ldc.i4.s 0x32
0x2555f  ldstr    aTokenCacheTheC_14// "Token Cache: The cookie token appears v"...
0x25564  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25569  ldc.i4.1
0x2556a  stloc.0
0x2556b  ldloc.0
0x2556c  ret
```
