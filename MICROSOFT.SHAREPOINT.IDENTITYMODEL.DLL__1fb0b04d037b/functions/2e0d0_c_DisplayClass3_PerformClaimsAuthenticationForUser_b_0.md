# <>c__DisplayClass3::<PerformClaimsAuthenticationForUser>b__0

- ea: `0x2e0d0`
- end: `0x2e144`
- name: `<>c__DisplayClass3::<PerformClaimsAuthenticationForUser>b__0`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2e0d0`

## string_xrefs

- `0x2e0d5`: `SPTokenCacheDontCacheToken`
- `0x2e137`: `SPTokenCacheDontCacheToken`
- `0x2e0f1`: `Claims Windows Sign-In: For user '{0}' on request url '{1}' using cached token for authenticationession.`

## pseudocode

```c

```

## disassembly

```asm
0x2e0d0  call     class [mscorlib]System.Collections.IDictionary [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPThreadContext::get_Items()
0x2e0d5  ldstr    aSptokencachedo// "SPTokenCacheDontCacheToken"
0x2e0da  ldc.i4.1
0x2e0db  box      [mscorlib]System.Boolean
0x2e0e0  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x2e0e5  ldc.i4   0x15D696
0x2e0ea  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2e0ef  ldc.i4.s 0x64
0x2e0f1  ldstr    aClaimsWindowsS_3// "Claims Windows Sign-In: For user '{0}' "...
0x2e0f6  ldc.i4.2
0x2e0f7  newarr   [mscorlib]System.Object
0x2e0fc  stloc.0
0x2e0fd  ldloc.0
0x2e0fe  ldc.i4.0
0x2e0ff  ldarg.0
0x2e100  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity <>c__DisplayClass3::windowsIdentity
0x2e105  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x2e10a  stelem.ref
0x2e10b  ldloc.0
0x2e10c  ldc.i4.1
0x2e10d  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x2e112  stelem.ref
0x2e113  ldloc.0
0x2e114  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2e119  ldarg.0
0x2e11a  ldfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule <>c__DisplayClass3::sam
0x2e11f  ldarg.0
0x2e120  ldfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken <>c__DisplayClass3::sessionSecurityToken
0x2e125  ldarg.0
0x2e126  ldfld    bool <>c__DisplayClass3::writeCookie
0x2e12b  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::AuthenticateSessionSecurityToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken, bool)
0x2e130  leave.s  loc_2E143
0x2e132  call     class [mscorlib]System.Collections.IDictionary [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPThreadContext::get_Items()
0x2e137  ldstr    aSptokencachedo// "SPTokenCacheDontCacheToken"
0x2e13c  ldnull
0x2e13d  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x2e142  endfinally
0x2e143  ret
```
