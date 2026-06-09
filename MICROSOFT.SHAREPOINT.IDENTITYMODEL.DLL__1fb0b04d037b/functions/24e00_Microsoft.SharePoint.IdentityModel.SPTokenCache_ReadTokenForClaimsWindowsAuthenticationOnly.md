# Microsoft.SharePoint.IdentityModel.SPTokenCache::ReadTokenForClaimsWindowsAuthenticationOnly

- ea: `0x24e00`
- end: `0x24f35`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ReadTokenForClaimsWindowsAuthenticationOnly`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x23320`

## callees

- `0x22ad0`
- `0x22c40`
- `0x23040`
- `0x23540`
- `0x235d0`
- `0x24e00`
- `0x258a0`
- `0x26d00`

## string_xrefs

- `0x24e6f`: `Token Cache: Could not get user key so can't look up token. Username: <name>'{0}'</name>`
- `0x24ef5`: `Token Cache: Found entry for user but discarding to force windows auth because we need the windows identity object. Username: <name>'{0}'</name>.`

## pseudocode

```c

```

## disassembly

```asm
0x24e00  ldnull
0x24e01  stloc.0
0x24e02  ldnull
0x24e03  stloc.1
0x24e04  ldnull
0x24e05  stloc.2
0x24e06  ldarg.1
0x24e07  brfalse.s loc_24E11
0x24e09  ldarg.0
0x24e0a  ldarg.1
0x24e0b  call     instance string Microsoft.SharePoint.IdentityModel.SPTokenCache::ReadTokenFromBytes(unsigned int8[] tokenValue)
0x24e10  pop
0x24e11  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x24e16  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetWindowsUserNameFromContext(class [System.Web]System.Web.HttpContext context)
0x24e1b  dup
0x24e1c  stloc.1
0x24e1d  brfalse.s loc_24E27
0x24e1f  ldloc.1
0x24e20  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24e25  brfalse.s loc_24E51
0x24e27  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x24e2c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x24e31  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x24e36  ldstr    aAuthForceWindo// "AUTH_FORCE_WINDOWS_MODE"
0x24e3b  ldstr    aTrue_0// "TRUE"
0x24e40  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x24e45  ldarg.0
0x24e46  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24e4b  stloc.0
0x24e4c  br       loc_24F33
0x24e51  ldloc.1
0x24e52  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetWindowsUserKey(string userName)
0x24e57  dup
0x24e58  stloc.2
0x24e59  brfalse.s loc_24E63
0x24e5b  ldloc.2
0x24e5c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24e61  brfalse.s loc_24E94
0x24e63  ldc.i4   0x5E34C8
0x24e68  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24e6d  ldc.i4.s 0xA
0x24e6f  ldstr    aTokenCacheCoul_8// "Token Cache: Could not get user key so "...
0x24e74  ldc.i4.1
0x24e75  newarr   [mscorlib]System.Object
0x24e7a  stloc.s  5
0x24e7c  ldloc.s  5
0x24e7e  ldc.i4.0
0x24e7f  ldloc.1
0x24e80  stelem.ref
0x24e81  ldloc.s  5
0x24e83  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24e88  ldarg.0
0x24e89  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24e8e  stloc.0
0x24e8f  br       loc_24F33
0x24e94  ldarg.0
0x24e95  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x24e9a  callvirt instance string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSiteSubscriptionIdFromUri(class [System]System.Uri context)
0x24e9f  stloc.3
0x24ea0  ldarg.0
0x24ea1  ldloc.3
0x24ea2  ldloc.2
0x24ea3  call     instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCachedToken(string subscriptionId, string identity)
0x24ea8  stloc.0
0x24ea9  ldloc.0
0x24eaa  brtrue.s loc_24ED3
0x24eac  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x24eb1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x24eb6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x24ebb  ldstr    aAuthForceWindo// "AUTH_FORCE_WINDOWS_MODE"
0x24ec0  ldstr    aTrue_0// "TRUE"
0x24ec5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x24eca  ldarg.0
0x24ecb  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24ed0  stloc.0
0x24ed1  br.s     loc_24F33
0x24ed3  ldloc.1
0x24ed4  newobj   instance void [mscorlib]System.Security.Principal.NTAccount::.ctor(string)
0x24ed9  stloc.s  4
0x24edb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x24ee0  ldloc.s  4
0x24ee2  call     bool Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::IsWindowsIdentityNeededAndMissing(class [System.Web]System.Web.HttpContext context, class [mscorlib]System.Security.Principal.NTAccount ntAccount)
0x24ee7  brfalse.s loc_24F33
0x24ee9  ldc.i4   0x5E34C9
0x24eee  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24ef3  ldc.i4.s 0x64
0x24ef5  ldstr    aTokenCacheFoun_1// "Token Cache: Found entry for user but d"...
0x24efa  ldc.i4.1
0x24efb  newarr   [mscorlib]System.Object
0x24f00  stloc.s  6
0x24f02  ldloc.s  6
0x24f04  ldc.i4.0
0x24f05  ldloc.1
0x24f06  stelem.ref
0x24f07  ldloc.s  6
0x24f09  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24f0e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x24f13  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x24f18  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x24f1d  ldstr    aAuthForceWindo// "AUTH_FORCE_WINDOWS_MODE"
0x24f22  ldstr    aTrue_0// "TRUE"
0x24f27  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x24f2c  ldarg.0
0x24f2d  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x24f32  stloc.0
0x24f33  ldloc.0
0x24f34  ret
```
