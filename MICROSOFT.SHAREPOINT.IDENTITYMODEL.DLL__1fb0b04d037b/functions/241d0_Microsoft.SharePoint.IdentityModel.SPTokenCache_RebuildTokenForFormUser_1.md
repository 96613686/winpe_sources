# Microsoft.SharePoint.IdentityModel.SPTokenCache::RebuildTokenForFormUser_1

- ea: `0x241d0`
- end: `0x2448c`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::RebuildTokenForFormUser_1`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x241b0`

## callees

- `0xba40`
- `0xbac0`
- `0x20660`
- `0x20800`
- `0x21b50`
- `0x21b70`
- `0x21d30`
- `0x241d0`

## string_xrefs

- `0x24435`: `http://schemas.microsoft.com/sharepoint/2014/06/signin/failure`
- `0x24241`: `Could not get SPIisSettings for url. Uri: '{0}'.`
- `0x24284`: `Not in claims forms auth for url. Uri: '{0}'.`
- `0x2421a`: `Token Cache: CookieValue is null.`
- `0x241ee`: `Token Cache: RequestData is null.`
- `0x2434d`: `Token Cache: Failed to rebuild a token for the user. Username: <name>'{0}'</name>.`
- `0x24390`: `Token Cache: Authenticating user. Username: <name>'{0}'</name>.`
- `0x243ca`: `Token Cache: Getting principal for user. Username: <name>'{0}'</name>.`
- `0x24458`: `Token Cache: Failed to rebuild the token for the user. Username: <name>'{0}'</name>: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x241d0  ldnull
0x241d1  stloc.0
0x241d2  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x241d7  stloc.1
0x241d8  ldloc.1
0x241d9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::GetSettingsForContext(class [System]System.Uri)
0x241de  stloc.2
0x241df  ldarg.1
0x241e0  brtrue.s loc_24206
0x241e2  ldc.i4   0x5E3463
0x241e7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x241ec  ldc.i4.s 0xA
0x241ee  ldstr    aTokenCacheRequ_2// "Token Cache: RequestData is null."
0x241f3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x241f8  ldnull
0x241f9  stloc.0
0x241fa  ldarg.1
0x241fb  ldnull
0x241fc  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewSessionToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken value)
0x24201  br       loc_2448A
0x24206  ldarg.1
0x24207  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2420c  brtrue.s loc_24232
0x2420e  ldc.i4   0x5E3480
0x24213  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24218  ldc.i4.s 0xA
0x2421a  ldstr    aTokenCacheCook_5// "Token Cache: CookieValue is null."
0x2421f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24224  ldnull
0x24225  stloc.0
0x24226  ldarg.1
0x24227  ldnull
0x24228  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewSessionToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken value)
0x2422d  br       loc_2448A
0x24232  ldloc.2
0x24233  brtrue.s loc_24268
0x24235  ldc.i4   0x5E3481
0x2423a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2423f  ldc.i4.s 0xA
0x24241  ldstr    aCouldNotGetSpi_0// "Could not get SPIisSettings for url. Ur"...
0x24246  ldc.i4.1
0x24247  newarr   [mscorlib]System.Object
0x2424c  stloc.s  8
0x2424e  ldloc.s  8
0x24250  ldc.i4.0
0x24251  ldloc.1
0x24252  stelem.ref
0x24253  ldloc.s  8
0x24255  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2425a  ldnull
0x2425b  stloc.0
0x2425c  ldarg.1
0x2425d  ldnull
0x2425e  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewSessionToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken value)
0x24263  br       loc_2448A
0x24268  ldloc.2
0x24269  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_UseClaimsAuthentication()
0x2426e  brfalse.s loc_24278
0x24270  ldloc.2
0x24271  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_UseFormsClaimsAuthenticationProvider()
0x24276  brtrue.s loc_242AB
0x24278  ldc.i4   0x5E3482
0x2427d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24282  ldc.i4.s 0xA
0x24284  ldstr    aNotInClaimsFor_0// "Not in claims forms auth for url. Uri: "...
0x24289  ldc.i4.1
0x2428a  newarr   [mscorlib]System.Object
0x2428f  stloc.s  9
0x24291  ldloc.s  9
0x24293  ldc.i4.0
0x24294  ldloc.1
0x24295  stelem.ref
0x24296  ldloc.s  9
0x24298  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2429d  ldnull
0x2429e  stloc.0
0x2429f  ldarg.1
0x242a0  ldnull
0x242a1  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewSessionToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken value)
0x242a6  br       loc_2448A
0x242ab  ldloc.2
0x242ac  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_FormsClaimsAuthenticationProvider()
0x242b1  stloc.3
0x242b2  ldnull
0x242b3  stloc.s  4
0x242b5  ldarg.2
0x242b6  brfalse.s loc_242EA
0x242b8  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::GetSafeAppliesToFromHttpContext()
0x242bd  ldloc.3
0x242be  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider::get_MembershipProvider()
0x242c3  ldloc.3
0x242c4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider::get_RoleProvider()
0x242c9  ldarg.1
0x242ca  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x242cf  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x242d4  ldarg.1
0x242d5  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieString()
0x242da  ldarg.3
0x242db  ldc.i4.0
0x242dc  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x242e1  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::SecurityTokenForFormsAuthentication(class [System]System.Uri, string, string, string, string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption, valuetype [mscorlib]System.Nullable`1<bool>)
0x242e6  stloc.s  4
0x242e8  br.s     loc_2433D
0x242ea  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::GetSafeAppliesToFromHttpContext()
0x242ef  ldloc.3
0x242f0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider::get_MembershipProvider()
0x242f5  ldloc.3
0x242f6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider::get_RoleProvider()
0x242fb  ldarg.1
0x242fc  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24301  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x24306  ldarg.1
0x24307  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieString()
0x2430c  ldarg.3
0x2430d  ldc.i4.1
0x2430e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x24313  ldarg.s  4
0x24315  ldarg.s  5
0x24317  ldnull
0x24318  ldloca.s 0xA
0x2431a  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0x24320  ldloc.s  0xA
0x24322  ldloca.s 0xB
0x24324  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x2432a  ldloc.s  0xB
0x2432c  ldloca.s 0xC
0x2432e  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x24334  ldloc.s  0xC
0x24336  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::SecurityTokenForFormsAuthentication(class [System]System.Uri, string, string, string, string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption, valuetype [mscorlib]System.Nullable`1<bool>, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes>, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes>, string, valuetype [mscorlib]System.Nullable`1<int64>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x2433b  stloc.s  4
0x2433d  ldloc.s  4
0x2433f  brtrue.s loc_2437E
0x24341  ldc.i4   0x5E3483
0x24346  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2434b  ldc.i4.s 0xA
0x2434d  ldstr    aTokenCacheFail_2// "Token Cache: Failed to rebuild a token "...
0x24352  ldc.i4.1
0x24353  newarr   [mscorlib]System.Object
0x24358  stloc.s  0xD
0x2435a  ldloc.s  0xD
0x2435c  ldc.i4.0
0x2435d  ldarg.1
0x2435e  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24363  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x24368  stelem.ref
0x24369  ldloc.s  0xD
0x2436b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24370  ldnull
0x24371  stloc.0
0x24372  ldarg.1
0x24373  ldnull
0x24374  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewSessionToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken value)
0x24379  br       loc_2442F
0x2437e  ldnull
0x2437f  stloc.s  5
0x24381  ldarg.2
0x24382  brfalse.s loc_243BE
0x24384  ldc.i4   0x1485044
0x24389  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2438e  ldc.i4.s 0x32
0x24390  ldstr    aTokenCacheAuth// "Token Cache: Authenticating user. Usern"...
0x24395  ldc.i4.1
0x24396  newarr   [mscorlib]System.Object
0x2439b  stloc.s  0xE
0x2439d  ldloc.s  0xE
0x2439f  ldc.i4.0
0x243a0  ldarg.1
0x243a1  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x243a6  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x243ab  stelem.ref
0x243ac  ldloc.s  0xE
0x243ae  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x243b3  ldloc.s  4
0x243b5  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::AuthenticateUser(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken)
0x243ba  stloc.s  5
0x243bc  br.s     loc_243F6
0x243be  ldc.i4   0x1485045
0x243c3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x243c8  ldc.i4.s 0x32
0x243ca  ldstr    aTokenCacheGett// "Token Cache: Getting principal for user"...
0x243cf  ldc.i4.1
0x243d0  newarr   [mscorlib]System.Object
0x243d5  stloc.s  0xF
0x243d7  ldloc.s  0xF
0x243d9  ldc.i4.0
0x243da  ldarg.1
0x243db  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x243e0  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x243e5  stelem.ref
0x243e6  ldloc.s  0xF
0x243e8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x243ed  ldloc.s  4
0x243ef  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::GetPrincipalFromToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken)
0x243f4  stloc.s  5
0x243f6  ldloc.s  5
0x243f8  ldnull
0x243f9  ldloc.s  4
0x243fb  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x24400  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x24405  ldloc.s  4
0x24407  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x2440c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x24411  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal, string, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x24416  stloc.0
0x24417  ldloc.0
0x24418  ldarg.1
0x24419  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2441e  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsPersistent()
0x24423  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::set_IsPersistent(bool)
0x24428  ldarg.1
0x24429  ldloc.0
0x2442a  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewSessionToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken value)
0x2442f  leave.s  loc_2448A
0x24431  stloc.s  6
0x24433  ldloc.s  6
0x24435  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sharepoint"...
0x2443a  ldstr    aSessionrevoked// "SessionRevokedByIdentityProvider"
0x2443f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceFailureUtilities::IsSpecificTokenIssuanceFailureException(class [mscorlib]System.Exception, string, string)
0x24444  stloc.s  7
0x24446  ldloc.s  7
0x24448  brfalse.s loc_2444C
0x2444a  rethrow
0x2444c  ldc.i4   0x5E3484
0x24451  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24456  ldc.i4.s 0xA
0x24458  ldstr    aTokenCacheFail_3// "Token Cache: Failed to rebuild the toke"...
0x2445d  ldc.i4.2
0x2445e  newarr   [mscorlib]System.Object
0x24463  stloc.s  0x10
0x24465  ldloc.s  0x10
0x24467  ldc.i4.0
0x24468  ldarg.1
0x24469  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2446e  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x24473  stelem.ref
0x24474  ldloc.s  0x10
0x24476  ldc.i4.1
0x24477  ldloc.s  6
0x24479  callvirt instance string [mscorlib]System.Object::ToString()
0x2447e  stelem.ref
0x2447f  ldloc.s  0x10
0x24481  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24486  ldnull
0x24487  stloc.0
0x24488  leave.s  loc_2448A
0x2448a  ldloc.0
0x2448b  ret
```
