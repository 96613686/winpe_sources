# Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::ValidateCookieValue

- ea: `0x22280`
- end: `0x224a9`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::ValidateCookieValue`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x21d60`

## callees

- `0x20630`
- `0x20660`
- `0x20720`
- `0x20780`
- `0x208b0`
- `0x209b0`
- `0x21b70`
- `0x22130`
- `0x22280`

## string_xrefs

- `0x2229a`: `Token Request Data: CookieValue is null.`
- `0x222c4`: `Token Request Data: Cookie isn't valid. UserName: '{0}'.`
- `0x2230a`: `Token Request Data: Couldn't get IIS settings.`
- `0x22336`: `Token Request Data: Cookie has failed audience validation. Cookie validation mode: '{0}'.`
- `0x22381`: `Token Request Data: Found expired session authentication cookie for user so ignoring it. UserName: '{0}'.`
- `0x223ea`: `Token Request Data: Expired cookie found so signing the user out. UserName: '{0}'. Expiration date: '{1}'.`
- `0x2243b`: `Token Request Data: Expired cookie so marking the cookie as invalid. UserName: '{0}'. Expiration date: '{1}'.`
- `0x22482`: `Token Request Data: Cookie is valid. UserName: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x22280  ldc.i4.0
0x22281  stloc.0
0x22282  ldc.i4.0
0x22283  stloc.1
0x22284  ldnull
0x22285  stloc.2
0x22286  ldarg.0
0x22287  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2228c  brtrue.s loc_222AB
0x2228e  ldc.i4   0x5E341D
0x22293  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22298  ldc.i4.s 0xA
0x2229a  ldstr    aTokenRequestDa_26// "Token Request Data: CookieValue is null"...
0x2229f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x222a4  ldc.i4.0
0x222a5  stloc.0
0x222a6  br       loc_224A7
0x222ab  ldarg.0
0x222ac  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x222b1  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsValid()
0x222b6  brtrue.s loc_222EE
0x222b8  ldc.i4   0x5E341E
0x222bd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x222c2  ldc.i4.s 0xA
0x222c4  ldstr    aTokenRequestDa_27// "Token Request Data: Cookie isn't valid."...
0x222c9  ldc.i4.1
0x222ca  newarr   [mscorlib]System.Object
0x222cf  stloc.s  4
0x222d1  ldloc.s  4
0x222d3  ldc.i4.0
0x222d4  ldarg.0
0x222d5  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x222da  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x222df  stelem.ref
0x222e0  ldloc.s  4
0x222e2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x222e7  ldc.i4.0
0x222e8  stloc.0
0x222e9  br       loc_224A7
0x222ee  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x222f3  ldloca.s 2
0x222f5  ldloca.s 1
0x222f7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::GetSettingsForContext(class [System]System.Uri, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication&, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone&)
0x222fc  brtrue.s loc_2231B
0x222fe  ldc.i4   0x5E341F
0x22303  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22308  ldc.i4.s 0xA
0x2230a  ldstr    aTokenRequestDa_28// "Token Request Data: Couldn't get IIS se"...
0x2230f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x22314  ldc.i4.0
0x22315  stloc.0
0x22316  br       loc_224A7
0x2231b  ldarg.0
0x2231c  ldloc.2
0x2231d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x22322  ldloc.1
0x22323  call     instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::ValidateCookieAudience(valuetype [mscorlib]System.Guid webApplicationId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone urlZone)
0x22328  brtrue.s loc_22365
0x2232a  ldc.i4   0x12078C2
0x2232f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22334  ldc.i4.s 0xA
0x22336  ldstr    aTokenRequestDa_29// "Token Request Data: Cookie has failed a"...
0x2233b  ldc.i4.1
0x2233c  newarr   [mscorlib]System.Object
0x22341  stloc.s  5
0x22343  ldloc.s  5
0x22345  ldc.i4.0
0x22346  ldarg.0
0x22347  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2234c  callvirt instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_ValidationMode()
0x22351  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x22356  stelem.ref
0x22357  ldloc.s  5
0x22359  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2235e  ldc.i4.0
0x2235f  stloc.0
0x22360  br       loc_224A7
0x22365  ldarg.0
0x22366  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2236b  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsExpired()
0x22370  brfalse  loc_22476
0x22375  ldc.i4   0x5E3421
0x2237a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2237f  ldc.i4.s 0x64
0x22381  ldstr    aTokenRequestDa_30// "Token Request Data: Found expired sessi"...
0x22386  ldc.i4.1
0x22387  newarr   [mscorlib]System.Object
0x2238c  stloc.s  6
0x2238e  ldloc.s  6
0x22390  ldc.i4.0
0x22391  ldarg.0
0x22392  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x22397  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x2239c  stelem.ref
0x2239d  ldloc.s  6
0x2239f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x223a4  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x223a9  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x223ae  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x223b3  ldstr    aSpsessionauthe// "SPSessionAuthentication"
0x223b8  ldstr    aCookieExpired// "cookie-expired"
0x223bd  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x223c2  ldarg.0
0x223c3  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x223c8  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x223cd  brfalse.s loc_223DE
0x223cf  ldc.i4.s 0x74
0x223d1  ldarg.0
0x223d2  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x223d7  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x223dc  bne.un.s loc_2242F
0x223de  ldc.i4   0x5E3422
0x223e3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x223e8  ldc.i4.s 0x32
0x223ea  ldstr    aTokenRequestDa_31// "Token Request Data: Expired cookie foun"...
0x223ef  ldc.i4.2
0x223f0  newarr   [mscorlib]System.Object
0x223f5  stloc.s  7
0x223f7  ldloc.s  7
0x223f9  ldc.i4.0
0x223fa  ldarg.0
0x223fb  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x22400  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x22405  stelem.ref
0x22406  ldloc.s  7
0x22408  ldc.i4.1
0x22409  ldarg.0
0x2240a  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2240f  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_Expires()
0x22414  box      [mscorlib]System.DateTime
0x22419  stelem.ref
0x2241a  ldloc.s  7
0x2241c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22421  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_SessionAuthenticationModule()
0x22426  stloc.3
0x22427  ldloc.3
0x22428  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::SignOut()
0x2242d  br.s     loc_22472
0x2242f  ldc.i4   0x5E3423
0x22434  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22439  ldc.i4.s 0x32
0x2243b  ldstr    aTokenRequestDa_32// "Token Request Data: Expired cookie so m"...
0x22440  ldc.i4.2
0x22441  newarr   [mscorlib]System.Object
0x22446  stloc.s  8
0x22448  ldloc.s  8
0x2244a  ldc.i4.0
0x2244b  ldarg.0
0x2244c  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x22451  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x22456  stelem.ref
0x22457  ldloc.s  8
0x22459  ldc.i4.1
0x2245a  ldarg.0
0x2245b  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x22460  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_Expires()
0x22465  box      [mscorlib]System.DateTime
0x2246a  stelem.ref
0x2246b  ldloc.s  8
0x2246d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22472  ldc.i4.0
0x22473  stloc.0
0x22474  br.s     loc_224A7
0x22476  ldc.i4   0x5E3440
0x2247b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22480  ldc.i4.s 0x32
0x22482  ldstr    aTokenRequestDa_33// "Token Request Data: Cookie is valid. Us"...
0x22487  ldc.i4.1
0x22488  newarr   [mscorlib]System.Object
0x2248d  stloc.s  9
0x2248f  ldloc.s  9
0x22491  ldc.i4.0
0x22492  ldarg.0
0x22493  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x22498  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x2249d  stelem.ref
0x2249e  ldloc.s  9
0x224a0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x224a5  ldc.i4.1
0x224a6  stloc.0
0x224a7  ldloc.0
0x224a8  ret
```
