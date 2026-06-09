# Microsoft.SharePoint.IdentityModel.SPTokenCache::ReadTokenForCookieBasedAuthentication

- ea: `0x24c50`
- end: `0x24dfe`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ReadTokenForCookieBasedAuthentication`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x23320`

## callees

- `0x20660`
- `0x20800`
- `0x208b0`
- `0x21b70`
- `0x21b90`
- `0x21bd0`
- `0x22ad0`
- `0x238b0`
- `0x24080`
- `0x24980`
- `0x249e0`
- `0x24a40`
- `0x24b00`
- `0x24b90`
- `0x24c50`
- `0x24f40`
- `0x25130`
- `0x26d00`

## string_xrefs

- `0x24cb5`: `Token Cache: Found entry for user but we need the windows identity so force full windows auth cycle so we can cache the windows identity when we get it. Username: <name>'{0}'</name>.`
- `0x24d63`: `Checking to see if we need to update the requestor's cookie.`
- `0x24da1`: `Token Cache: Failed handle missing token for user. Username: <name>'{0}'</name>. SessionId: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x24c50  ldnull
0x24c51  stloc.0
0x24c52  ldarg.0
0x24c53  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData Microsoft.SharePoint.IdentityModel.SPTokenCache::CreateSessionSecurityTokenRequestData()
0x24c58  stloc.1
0x24c59  ldc.i4.0
0x24c5a  stloc.2
0x24c5b  ldarg.0
0x24c5c  ldloc.1
0x24c5d  ldarg.1
0x24c5e  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::InitializeAndValidateRequest(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData, unsigned int8[] cookieBinaryData)
0x24c63  brtrue.s loc_24C71
0x24c65  ldarg.0
0x24c66  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24c6b  stloc.0
0x24c6c  br       loc_24D37
0x24c71  ldloc.1
0x24c72  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedToken()
0x24c77  brfalse  loc_24D08
0x24c7c  ldc.i4.s 0x77
0x24c7e  ldloc.1
0x24c7f  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24c84  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x24c89  bne.un.s loc_24D08
0x24c8b  ldloc.1
0x24c8c  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24c91  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x24c96  newobj   instance void [mscorlib]System.Security.Principal.NTAccount::.ctor(string)
0x24c9b  stloc.3
0x24c9c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x24ca1  ldloc.3
0x24ca2  call     bool Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::IsWindowsIdentityNeededAndMissing(class [System.Web]System.Web.HttpContext context, class [mscorlib]System.Security.Principal.NTAccount ntAccount)
0x24ca7  brfalse.s loc_24CFF
0x24ca9  ldc.i4   0x5E34C4
0x24cae  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24cb3  ldc.i4.s 0x64
0x24cb5  ldstr    aTokenCacheFoun_0// "Token Cache: Found entry for user but w"...
0x24cba  ldc.i4.1
0x24cbb  newarr   [mscorlib]System.Object
0x24cc0  stloc.s  4
0x24cc2  ldloc.s  4
0x24cc4  ldc.i4.0
0x24cc5  ldloc.1
0x24cc6  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24ccb  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x24cd0  stelem.ref
0x24cd1  ldloc.s  4
0x24cd3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24cd8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x24cdd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x24ce2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x24ce7  ldstr    aAuthForceWindo// "AUTH_FORCE_WINDOWS_MODE"
0x24cec  ldstr    aTrue_0// "TRUE"
0x24cf1  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x24cf6  ldarg.0
0x24cf7  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24cfc  stloc.0
0x24cfd  br.s     loc_24D37
0x24cff  ldloc.1
0x24d00  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedToken()
0x24d05  stloc.0
0x24d06  br.s     loc_24D37
0x24d08  ldloc.1
0x24d09  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedToken()
0x24d0e  brtrue.s loc_24D1A
0x24d10  ldarg.0
0x24d11  ldloc.1
0x24d12  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::RebuildTokenForCacheMiss(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24d17  stloc.0
0x24d18  br.s     loc_24D37
0x24d1a  ldloc.1
0x24d1b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x24d20  brfalse.s loc_24D35
0x24d22  ldarg.0
0x24d23  ldloc.1
0x24d24  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesTokenNeedToBeRefreshed(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24d29  brfalse.s loc_24D35
0x24d2b  ldarg.0
0x24d2c  ldloc.1
0x24d2d  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::RefreshToken(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24d32  stloc.0
0x24d33  br.s     loc_24D37
0x24d35  ldc.i4.1
0x24d36  stloc.2
0x24d37  ldloc.2
0x24d38  ldloc.1
0x24d39  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x24d3e  brfalse.s loc_24D51
0x24d40  ldloc.0
0x24d41  brfalse.s loc_24D51
0x24d43  ldloc.0
0x24d44  ldarg.0
0x24d45  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24d4a  ceq
0x24d4c  ldc.i4.0
0x24d4d  ceq
0x24d4f  br.s     loc_24D52
0x24d51  ldc.i4.0
0x24d52  or
0x24d53  stloc.2
0x24d54  ldloc.2
0x24d55  brfalse.s loc_24D92
0x24d57  ldc.i4   0x121B35C
0x24d5c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24d61  ldc.i4.s 0x64
0x24d63  ldstr    aCheckingToSeeI// "Checking to see if we need to update th"...
0x24d68  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24d6d  ldarg.0
0x24d6e  ldloc.1
0x24d6f  ldc.i4.1
0x24d70  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::ShouldForceReauthentication(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind tokenKind)
0x24d75  brfalse.s loc_24D81
0x24d77  ldarg.0
0x24d78  ldloc.1
0x24d79  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::ForceReauthentication(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24d7e  stloc.0
0x24d7f  br.s     loc_24D92
0x24d81  ldarg.0
0x24d82  ldloc.1
0x24d83  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::UpdateCookieIfNecessary(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24d88  ldloc.0
0x24d89  brtrue.s loc_24D92
0x24d8b  ldloc.1
0x24d8c  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedToken()
0x24d91  stloc.0
0x24d92  ldloc.0
0x24d93  brtrue.s loc_24DE3
0x24d95  ldc.i4   0x5E34C7
0x24d9a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24d9f  ldc.i4.s 0xA
0x24da1  ldstr    aTokenCacheFail_6// "Token Cache: Failed handle missing toke"...
0x24da6  ldc.i4.2
0x24da7  newarr   [mscorlib]System.Object
0x24dac  stloc.s  5
0x24dae  ldloc.s  5
0x24db0  ldc.i4.0
0x24db1  ldloc.1
0x24db2  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24db7  brtrue.s loc_24DC0
0x24db9  ldstr    aNA// "N/A"
0x24dbe  br.s     loc_24DCB
0x24dc0  ldloc.1
0x24dc1  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24dc6  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x24dcb  stelem.ref
0x24dcc  ldloc.s  5
0x24dce  ldc.i4.1
0x24dcf  ldstr    aNA// "N/A"
0x24dd4  stelem.ref
0x24dd5  ldloc.s  5
0x24dd7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24ddc  ldarg.0
0x24ddd  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24de2  stloc.0
0x24de3  ldloc.1
0x24de4  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24de9  brfalse.s loc_24DFC
0x24deb  ldarg.0
0x24dec  ldloc.1
0x24ded  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24df2  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsPersistent()
0x24df7  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::CachePersistencyState(bool isPersisted)
0x24dfc  ldloc.0
0x24dfd  ret
```
