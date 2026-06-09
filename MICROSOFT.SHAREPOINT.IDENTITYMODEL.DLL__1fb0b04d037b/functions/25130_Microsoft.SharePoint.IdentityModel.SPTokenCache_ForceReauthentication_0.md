# Microsoft.SharePoint.IdentityModel.SPTokenCache::ForceReauthentication_0

- ea: `0x25130`
- end: `0x2523c`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ForceReauthentication_0`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x244f0`
- `0x24c50`

## callees

- `0x20660`
- `0x208b0`
- `0x21b70`
- `0x22ad0`
- `0x25130`

## string_xrefs

- `0x2513f`: `Token Cache: The RequestData is null.`
- `0x25168`: `Token Cache: The CookieValue is null.`
- `0x251b8`: `Token Cache: Forcing reauthentication by using windows authentication challenge. UserName: <name>'{0}'</name>`
- `0x251f9`: `Token Cache: Forcing reauthentication by clearing the FedAuth cookie. UserName: <name>'{0}'</name>. SessionId: '{1}', SignIn: '{2}', Renewal: '{3}'.`

## pseudocode

```c

```

## disassembly

```asm
0x25130  ldarg.1
0x25131  brtrue.s loc_25154
0x25133  ldc.i4   0x5E34D1
0x25138  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2513d  ldc.i4.s 0xA
0x2513f  ldstr    aTokenCacheTheR_0// "Token Cache: The RequestData is null."
0x25144  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25149  ldstr    aRequestdata// "requestData"
0x2514e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x25153  throw
0x25154  ldarg.1
0x25155  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2515a  brtrue.s loc_25178
0x2515c  ldc.i4   0x5E34D2
0x25161  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25166  ldc.i4.s 0xA
0x25168  ldstr    aTokenCacheTheC_5// "Token Cache: The CookieValue is null."
0x2516d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25172  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x25177  throw
0x25178  ldarg.0
0x25179  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x2517e  stloc.0
0x2517f  ldc.i4.s 0x77
0x25181  ldarg.1
0x25182  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x25187  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x2518c  bne.un.s loc_251E3
0x2518e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x25193  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x25198  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x2519d  ldstr    aAuthForceWindo// "AUTH_FORCE_WINDOWS_MODE"
0x251a2  ldstr    aTrue_0// "TRUE"
0x251a7  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x251ac  ldc.i4   0x5E34D3
0x251b1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x251b6  ldc.i4.s 0x32
0x251b8  ldstr    aTokenCacheForc_0// "Token Cache: Forcing reauthentication b"...
0x251bd  ldc.i4.1
0x251be  newarr   [mscorlib]System.Object
0x251c3  stloc.1
0x251c4  ldloc.1
0x251c5  ldc.i4.0
0x251c6  ldarg.1
0x251c7  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x251cc  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x251d1  dup
0x251d2  brtrue.s loc_251DA
0x251d4  pop
0x251d5  ldsfld   string [mscorlib]System.String::Empty
0x251da  stelem.ref
0x251db  ldloc.1
0x251dc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x251e1  br.s     loc_2523A
0x251e3  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_SessionAuthenticationModule()
0x251e8  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::SignOut()
0x251ed  ldc.i4   0x13D7857
0x251f2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x251f7  ldc.i4.s 0x32
0x251f9  ldstr    aTokenCacheForc_1// "Token Cache: Forcing reauthentication b"...
0x251fe  ldc.i4.4
0x251ff  newarr   [mscorlib]System.Object
0x25204  stloc.2
0x25205  ldloc.2
0x25206  ldc.i4.0
0x25207  ldarg.1
0x25208  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2520d  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x25212  dup
0x25213  brtrue.s loc_2521B
0x25215  pop
0x25216  ldsfld   string [mscorlib]System.String::Empty
0x2521b  stelem.ref
0x2521c  ldloc.2
0x2521d  ldc.i4.1
0x2521e  ldstr    aNA// "N/A"
0x25223  stelem.ref
0x25224  ldloc.2
0x25225  ldc.i4.2
0x25226  ldstr    aNA// "N/A"
0x2522b  stelem.ref
0x2522c  ldloc.2
0x2522d  ldc.i4.3
0x2522e  ldstr    aNA// "N/A"
0x25233  stelem.ref
0x25234  ldloc.2
0x25235  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2523a  ldloc.0
0x2523b  ret
```
