# Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteCookie

- ea: `0x24740`
- end: `0x2483c`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteCookie`
- size: `252`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x24840`
- `0x248f0`

## callees

- `0x20720`
- `0x20800`
- `0x224b0`
- `0x22570`
- `0x226f0`
- `0x23bd0`
- `0x24740`

## string_xrefs

- `0x2474f`: `Token Cache: The requestData is null.`
- `0x24769`: `Token Cache: The cookieKind is None.`
- `0x24789`: `Token Cache: The cookie data is missing.`
- `0x247aa`: `Token Cache: The cookie value to write isn't valid.`
- `0x247e5`: `Token Cache: Writing cookie. CookieOperationKind: '{0}', Persistance: '{1}', Expiration: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x24740  ldarg.1
0x24741  brtrue.s loc_2475A
0x24743  ldc.i4   0x6D31CF
0x24748  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2474d  ldc.i4.s 0xA
0x2474f  ldstr    aTokenCacheTheR// "Token Cache: The requestData is null."
0x24754  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24759  ret
0x2475a  ldarg.2
0x2475b  brtrue.s loc_24774
0x2475d  ldc.i4   0x6D31D0
0x24762  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24767  ldc.i4.s 0xA
0x24769  ldstr    aTokenCacheTheC_0// "Token Cache: The cookieKind is None."
0x2476e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24773  ret
0x24774  ldarg.1
0x24775  ldarg.2
0x24776  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::CheckCookieData(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x2477b  brtrue.s loc_24794
0x2477d  ldc.i4   0x6D31D1
0x24782  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24787  ldc.i4.s 0xA
0x24789  ldstr    aTokenCacheTheC_2// "Token Cache: The cookie data is missing"...
0x2478e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24793  ret
0x24794  ldarg.0
0x24795  ldarg.1
0x24796  ldarg.2
0x24797  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::IsCookieDataValidForWrite(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind cookieKind)
0x2479c  brtrue.s loc_247B5
0x2479e  ldc.i4   0x6D31D2
0x247a3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x247a8  ldc.i4.s 0xA
0x247aa  ldstr    aTokenCacheTheC_3// "Token Cache: The cookie value to write "...
0x247af  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x247b4  ret
0x247b5  ldarg.1
0x247b6  ldarg.2
0x247b7  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCookieValue(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x247bc  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsPersistent()
0x247c1  stloc.0
0x247c2  ldloc.0
0x247c3  brtrue.s loc_247CC
0x247c5  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x247ca  br.s     loc_247D8
0x247cc  ldarg.1
0x247cd  ldarg.2
0x247ce  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCookieValue(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x247d3  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_Expires()
0x247d8  stloc.1
0x247d9  ldc.i4   0x6D31D3
0x247de  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x247e3  ldc.i4.s 0x32
0x247e5  ldstr    aTokenCacheWrit_0// "Token Cache: Writing cookie. CookieOper"...
0x247ea  ldc.i4.3
0x247eb  newarr   [mscorlib]System.Object
0x247f0  stloc.3
0x247f1  ldloc.3
0x247f2  ldc.i4.0
0x247f3  ldarg.2
0x247f4  box      Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind
0x247f9  stelem.ref
0x247fa  ldloc.3
0x247fb  ldc.i4.1
0x247fc  ldloc.0
0x247fd  box      [mscorlib]System.Boolean
0x24802  stelem.ref
0x24803  ldloc.3
0x24804  ldc.i4.2
0x24805  ldloc.1
0x24806  box      [mscorlib]System.DateTime
0x2480b  stelem.ref
0x2480c  ldloc.3
0x2480d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24812  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_SessionAuthenticationModule()
0x24817  stloc.2
0x24818  ldloc.2
0x24819  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.CookieHandler [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::get_CookieHandler()
0x2481e  ldarg.1
0x2481f  ldarg.2
0x24820  callvirt instance unsigned int8[] Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCookieBinaryData(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x24825  ldloc.2
0x24826  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.CookieHandler [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::get_CookieHandler()
0x2482b  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.CookieHandler::get_Name()
0x24830  ldloc.1
0x24831  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x24836  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.CookieHandler::Write(unsigned int8[], string, valuetype [mscorlib]System.DateTime, class [System.Web]System.Web.HttpContext)
0x2483b  ret
```
