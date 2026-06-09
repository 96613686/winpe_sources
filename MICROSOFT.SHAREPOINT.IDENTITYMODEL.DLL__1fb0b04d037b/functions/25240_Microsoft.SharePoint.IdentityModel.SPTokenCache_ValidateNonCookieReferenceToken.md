# Microsoft.SharePoint.IdentityModel.SPTokenCache::ValidateNonCookieReferenceToken

- ea: `0x25240`
- end: `0x253c0`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ValidateNonCookieReferenceToken`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x244f0`

## callees

- `0x25240`

## string_xrefs

- `0x25251`: `Token Cache: The token is null`
- `0x25276`: `Token Cache: The token has null claims principal.`
- `0x252a0`: `Token Cache: The token has null claims identities.`
- `0x252d0`: `Token Cache: The token has incorrect identity count.`
- `0x25300`: `Token Cache: The token has null claims identity.`
- `0x25335`: `Token Cache: The token has null claims.`
- `0x2536d`: `Token Cache: The token identity has incorrect claim count. Count: '{0}'.`
- `0x253b2`: `Token Cache: The token appears valid.`

## pseudocode

```c

```

## disassembly

```asm
0x25240  ldc.i4.0
0x25241  stloc.0
0x25242  ldarg.1
0x25243  brtrue.s loc_25262
0x25245  ldc.i4   0x119234F
0x2524a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2524f  ldc.i4.s 0xA
0x25251  ldstr    aTokenCacheTheT_4// "Token Cache: The token is null"
0x25256  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2525b  ldc.i4.0
0x2525c  stloc.0
0x2525d  br       loc_253BE
0x25262  ldarg.1
0x25263  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25268  brtrue.s loc_25287
0x2526a  ldc.i4   0x1192350
0x2526f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25274  ldc.i4.s 0xA
0x25276  ldstr    aTokenCacheTheT_5// "Token Cache: The token has null claims "...
0x2527b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25280  ldc.i4.0
0x25281  stloc.0
0x25282  br       loc_253BE
0x25287  ldarg.1
0x25288  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x2528d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x25292  brtrue.s loc_252B1
0x25294  ldc.i4   0x1192351
0x25299  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2529e  ldc.i4.s 0xA
0x252a0  ldstr    aTokenCacheTheT_6// "Token Cache: The token has null claims "...
0x252a5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x252aa  ldc.i4.0
0x252ab  stloc.0
0x252ac  br       loc_253BE
0x252b1  ldarg.1
0x252b2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x252b7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x252bc  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x252c1  ldc.i4.1
0x252c2  beq.s    loc_252E1
0x252c4  ldc.i4   0x1192352
0x252c9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x252ce  ldc.i4.s 0xA
0x252d0  ldstr    aTokenCacheTheT_7// "Token Cache: The token has incorrect id"...
0x252d5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x252da  ldc.i4.0
0x252db  stloc.0
0x252dc  br       loc_253BE
0x252e1  ldarg.1
0x252e2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x252e7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x252ec  ldc.i4.0
0x252ed  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x252f2  brtrue.s loc_25311
0x252f4  ldc.i4   0x1192353
0x252f9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x252fe  ldc.i4.s 0xA
0x25300  ldstr    aTokenCacheTheT_8// "Token Cache: The token has null claims "...
0x25305  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2530a  ldc.i4.0
0x2530b  stloc.0
0x2530c  br       loc_253BE
0x25311  ldarg.1
0x25312  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25317  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x2531c  ldc.i4.0
0x2531d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x25322  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x25327  brtrue.s loc_25343
0x25329  ldc.i4   0x1192354
0x2532e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25333  ldc.i4.s 0xA
0x25335  ldstr    aTokenCacheTheT_9// "Token Cache: The token has null claims."
0x2533a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2533f  ldc.i4.0
0x25340  stloc.0
0x25341  br.s     loc_253BE
0x25343  ldarg.1
0x25344  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25349  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x2534e  ldc.i4.0
0x2534f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x25354  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x25359  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::get_Count()
0x2535e  ldc.i4.5
0x2535f  bgt.s    loc_253A6
0x25361  ldc.i4   0x1192355
0x25366  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2536b  ldc.i4.s 0xA
0x2536d  ldstr    aTokenCacheTheT_10// "Token Cache: The token identity has inc"...
0x25372  ldc.i4.1
0x25373  newarr   [mscorlib]System.Object
0x25378  stloc.1
0x25379  ldloc.1
0x2537a  ldc.i4.0
0x2537b  ldarg.1
0x2537c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25381  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x25386  ldc.i4.0
0x25387  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x2538c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x25391  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::get_Count()
0x25396  box      [mscorlib]System.Int32
0x2539b  stelem.ref
0x2539c  ldloc.1
0x2539d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x253a2  ldc.i4.0
0x253a3  stloc.0
0x253a4  br.s     loc_253BE
0x253a6  ldc.i4   0x1192356
0x253ab  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x253b0  ldc.i4.s 0x32
0x253b2  ldstr    aTokenCacheTheT_11// "Token Cache: The token appears valid."
0x253b7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x253bc  ldc.i4.1
0x253bd  stloc.0
0x253be  ldloc.0
0x253bf  ret
```
