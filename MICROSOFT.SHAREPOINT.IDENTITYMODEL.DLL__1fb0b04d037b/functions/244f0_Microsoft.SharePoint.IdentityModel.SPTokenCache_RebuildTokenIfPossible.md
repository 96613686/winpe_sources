# Microsoft.SharePoint.IdentityModel.SPTokenCache::RebuildTokenIfPossible

- ea: `0x244f0`
- end: `0x2473e`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::RebuildTokenIfPossible`
- size: `590`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x24980`
- `0x249e0`

## callees

- `0x20640`
- `0x20660`
- `0x208b0`
- `0x21b70`
- `0x21c00`
- `0x21d40`
- `0x21d50`
- `0x22ad0`
- `0x24490`
- `0x244f0`
- `0x24840`
- `0x24f40`
- `0x25130`
- `0x25240`
- `0x25990`

## string_xrefs

- `0x245b5`: `http://schemas.microsoft.com/sharepoint/2014/06/signin/failure`
- `0x2452b`: `Token Cache: CookieValue is null.`
- `0x24501`: `Token Cache: RequestData is null.`
- `0x2455c`: `Token Cache: Identity is for windows so no rebuild is possible.`
- `0x245d6`: `Token cache: Received session revocation signal for user. Forcing reauthentication. Username: <name>'{0}'</name>.`
- `0x2461f`: `Token refresh SCOM monitor event. This event is expected and should not be used by itself for SPO incident diagnosis. Exception: '{0}'.`
- `0x24659`: `Token Cache: Failed to rebuild forms user token for user. Username: <name>'{0}'</name>.`
- `0x2468d`: `Token Cache: Successfully rebuilt forms user token for user. Username: <name>'{0}'</name>.`
- `0x24704`: `Token Cache: Failed to find token for user so signing out the user. Username: <name>'{0}'</name>.`

## pseudocode

```c

```

## disassembly

```asm
0x244f0  ldnull
0x244f1  stloc.0
0x244f2  ldarg.1
0x244f3  brtrue.s loc_24517
0x244f5  ldc.i4   0x5E3487
0x244fa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x244ff  ldc.i4.s 0xA
0x24501  ldstr    aTokenCacheRequ_2// "Token Cache: RequestData is null."
0x24506  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2450b  ldarg.0
0x2450c  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24511  stloc.0
0x24512  br       loc_2473C
0x24517  ldarg.1
0x24518  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2451d  brtrue.s loc_24541
0x2451f  ldc.i4   0x5E3488
0x24524  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24529  ldc.i4.s 0xA
0x2452b  ldstr    aTokenCacheCook_5// "Token Cache: CookieValue is null."
0x24530  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24535  ldarg.0
0x24536  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x2453b  stloc.0
0x2453c  br       loc_2473C
0x24541  ldc.i4.s 0x77
0x24543  ldarg.1
0x24544  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24549  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x2454e  bne.un.s loc_24590
0x24550  ldc.i4   0x15D61DD
0x24555  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2455a  ldc.i4.s 0x32
0x2455c  ldstr    aTokenCacheIden// "Token Cache: Identity is for windows so"...
0x24561  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24566  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2456b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x24570  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x24575  ldstr    aAuthForceWindo// "AUTH_FORCE_WINDOWS_MODE"
0x2457a  ldstr    aTrue_0// "TRUE"
0x2457f  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x24584  ldarg.0
0x24585  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x2458a  stloc.0
0x2458b  br       loc_2473C
0x24590  ldc.i4.s 0x66
0x24592  ldarg.1
0x24593  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24598  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x2459d  bne.un   loc_246F8
0x245a2  ldnull
0x245a3  stloc.1
0x245a4  ldc.i4.0
0x245a5  stloc.2
0x245a6  ldarg.0
0x245a7  ldarg.1
0x245a8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::RebuildTokenForFormUser(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x245ad  stloc.1
0x245ae  leave    loc_2463A
0x245b3  stloc.3
0x245b4  ldloc.3
0x245b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sharepoint"...
0x245ba  ldstr    aSessionrevoked// "SessionRevokedByIdentityProvider"
0x245bf  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceFailureUtilities::IsSpecificTokenIssuanceFailureException(class [mscorlib]System.Exception, string, string)
0x245c4  stloc.s  4
0x245c6  ldloc.s  4
0x245c8  brfalse.s loc_245FD
0x245ca  ldc.i4   0x60A0D1
0x245cf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x245d4  ldc.i4.s 0x32
0x245d6  ldstr    aTokenCacheRece// "Token cache: Received session revocatio"...
0x245db  ldc.i4.1
0x245dc  newarr   [mscorlib]System.Object
0x245e1  stloc.s  6
0x245e3  ldloc.s  6
0x245e5  ldc.i4.0
0x245e6  ldarg.1
0x245e7  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x245ec  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x245f1  stelem.ref
0x245f2  ldloc.s  6
0x245f4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x245f9  ldc.i4.1
0x245fa  stloc.2
0x245fb  br.s     loc_24638
0x245fd  ldarg.0
0x245fe  ldloc.1
0x245ff  call     instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::ValidateNonCookieReferenceToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken token)
0x24604  brtrue.s loc_2460A
0x24606  ldnull
0x24607  stloc.1
0x24608  br.s     loc_24638
0x2460a  ldc.i4   0x5E3489
0x2460f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSEventTemplates.ULSEvent_s [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSEvent::get_eventAuthentication_TokenRefreshFailed_EventId_8347()
0x24614  ldc.i4.2
0x24615  newarr   [mscorlib]System.Object
0x2461a  stloc.s  7
0x2461c  ldloc.s  7
0x2461e  ldc.i4.0
0x2461f  ldstr    aTokenRefreshSc// "Token refresh SCOM monitor event. This "...
0x24624  stelem.ref
0x24625  ldloc.s  7
0x24627  ldc.i4.1
0x24628  ldloc.3
0x24629  callvirt instance string [mscorlib]System.Object::ToString()
0x2462e  stelem.ref
0x2462f  ldloc.s  7
0x24631  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendMappedEventTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSEventBase, object[])
0x24636  rethrow
0x24638  leave.s  loc_2463A
0x2463a  ldloc.2
0x2463b  brfalse.s loc_2464A
0x2463d  ldarg.0
0x2463e  ldarg.1
0x2463f  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::ForceReauthentication(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24644  stloc.0
0x24645  br       loc_2473C
0x2464a  ldloc.1
0x2464b  brtrue.s loc_24681
0x2464d  ldc.i4   0x5E348A
0x24652  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24657  ldc.i4.s 0xA
0x24659  ldstr    aTokenCacheFail_4// "Token Cache: Failed to rebuild forms us"...
0x2465e  ldc.i4.1
0x2465f  newarr   [mscorlib]System.Object
0x24664  stloc.s  8
0x24666  ldloc.s  8
0x24668  ldc.i4.0
0x24669  ldarg.1
0x2466a  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2466f  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x24674  stelem.ref
0x24675  ldloc.s  8
0x24677  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2467c  br       loc_2473C
0x24681  ldc.i4   0x5E348B
0x24686  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2468b  ldc.i4.s 0x32
0x2468d  ldstr    aTokenCacheSucc_1// "Token Cache: Successfully rebuilt forms"...
0x24692  ldc.i4.1
0x24693  newarr   [mscorlib]System.Object
0x24698  stloc.s  9
0x2469a  ldloc.s  9
0x2469c  ldc.i4.0
0x2469d  ldarg.1
0x2469e  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x246a3  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x246a8  stelem.ref
0x246a9  ldloc.s  9
0x246ab  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x246b0  ldarg.1
0x246b1  ldloc.1
0x246b2  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x246b7  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCacheEntry(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry value)
0x246bc  ldarg.0
0x246bd  ldarg.1
0x246be  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_SubscriptionId()
0x246c3  ldarg.1
0x246c4  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x246c9  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserKey()
0x246ce  ldarg.1
0x246cf  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_NewCacheEntry()
0x246d4  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedToken(string subscriptionId, string identity, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry value)
0x246d9  ldarg.0
0x246da  ldarg.1
0x246db  ldc.i4.2
0x246dc  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::ShouldForceReauthentication(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind tokenKind)
0x246e1  brfalse.s loc_246ED
0x246e3  ldarg.0
0x246e4  ldarg.1
0x246e5  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::ForceReauthentication(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x246ea  stloc.0
0x246eb  br.s     loc_2473C
0x246ed  ldarg.0
0x246ee  ldarg.1
0x246ef  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::ReplaceCookieFromNewToken(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x246f4  ldloc.1
0x246f5  stloc.0
0x246f6  br.s     loc_2473C
0x246f8  ldc.i4   0x5E348C
0x246fd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24702  ldc.i4.s 0x64
0x24704  ldstr    aTokenCacheFail_5// "Token Cache: Failed to find token for u"...
0x24709  ldc.i4.1
0x2470a  newarr   [mscorlib]System.Object
0x2470f  stloc.s  0xA
0x24711  ldloc.s  0xA
0x24713  ldc.i4.0
0x24714  ldarg.1
0x24715  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2471a  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x2471f  stelem.ref
0x24720  ldloc.s  0xA
0x24722  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24727  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_SessionAuthenticationModule()
0x2472c  stloc.s  5
0x2472e  ldloc.s  5
0x24730  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::SignOut()
0x24735  ldarg.0
0x24736  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x2473b  stloc.0
0x2473c  ldloc.0
0x2473d  ret
```
