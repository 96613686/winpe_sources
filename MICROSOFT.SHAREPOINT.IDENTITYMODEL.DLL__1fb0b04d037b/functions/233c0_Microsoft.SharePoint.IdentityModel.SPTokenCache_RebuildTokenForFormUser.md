# Microsoft.SharePoint.IdentityModel.SPTokenCache::RebuildTokenForFormUser

- ea: `0x233c0`
- end: `0x23532`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::RebuildTokenForFormUser`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0xba40`
- `0x20660`
- `0x20800`
- `0x233b0`
- `0x233c0`

## string_xrefs

- `0x234e1`: `http://schemas.microsoft.com/sharepoint/2014/06/signin/failure`
- `0x233ea`: `Could not get SPIisSettings for url. Uri: '{0}'.`
- `0x2343a`: `Not in claims forms auth for url. Uri: '{0}'.`
- `0x23504`: `Token Cache: Failed to rebuild the token for the user. UserName: <name>'{0}'</name>, Exception: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x233c0  ldarg.1
0x233c1  brtrue.s loc_233CE
0x233c3  ldstr    aCookievalue// "cookieValue"
0x233c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x233cd  throw
0x233ce  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x233d3  stloc.0
0x233d4  ldloc.0
0x233d5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::GetSettingsForContext(class [System]System.Uri)
0x233da  stloc.1
0x233db  ldloc.1
0x233dc  brtrue.s loc_2341E
0x233de  ldc.i4   0x21A5C7
0x233e3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x233e8  ldc.i4.s 0xA
0x233ea  ldstr    aCouldNotGetSpi_0// "Could not get SPIisSettings for url. Ur"...
0x233ef  ldc.i4.1
0x233f0  newarr   [mscorlib]System.Object
0x233f5  stloc.s  9
0x233f7  ldloc.s  9
0x233f9  ldc.i4.0
0x233fa  ldloc.0
0x233fb  stelem.ref
0x233fc  ldloc.s  9
0x233fe  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x23403  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23408  ldstr    aIissettingsnot// "IISSettingsNotFound"
0x2340d  ldc.i4.0
0x2340e  newarr   [mscorlib]System.Object
0x23413  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x23418  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2341d  throw
0x2341e  ldloc.1
0x2341f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_UseClaimsAuthentication()
0x23424  brfalse.s loc_2342E
0x23426  ldloc.1
0x23427  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_UseFormsClaimsAuthenticationProvider()
0x2342c  brtrue.s loc_2346E
0x2342e  ldc.i4   0x21A5C8
0x23433  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23438  ldc.i4.s 0xA
0x2343a  ldstr    aNotInClaimsFor_0// "Not in claims forms auth for url. Uri: "...
0x2343f  ldc.i4.1
0x23440  newarr   [mscorlib]System.Object
0x23445  stloc.s  0xA
0x23447  ldloc.s  0xA
0x23449  ldc.i4.0
0x2344a  ldloc.0
0x2344b  stelem.ref
0x2344c  ldloc.s  0xA
0x2344e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x23453  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23458  ldstr    aFormsnotenable// "FormsNotEnabledForContext"
0x2345d  ldc.i4.0
0x2345e  newarr   [mscorlib]System.Object
0x23463  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x23468  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2346d  throw
0x2346e  ldloc.1
0x2346f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_FormsClaimsAuthenticationProvider()
0x23474  stloc.2
0x23475  ldnull
0x23476  stloc.3
0x23477  ldnull
0x23478  stloc.s  4
0x2347a  ldarg.0
0x2347b  ldarg.1
0x2347c  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption Microsoft.SharePoint.IdentityModel.SPTokenCache::GetRebuildTokenForFormsUserOptions(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue cookieValue)
0x23481  stloc.s  5
0x23483  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::GetSafeAppliesToFromHttpContext()
0x23488  ldloc.2
0x23489  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider::get_MembershipProvider()
0x2348e  ldloc.2
0x2348f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider::get_RoleProvider()
0x23494  ldarg.1
0x23495  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x2349a  ldarg.2
0x2349b  ldloc.s  5
0x2349d  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::SecurityTokenForFormsAuthentication(class [System]System.Uri, string, string, string, string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption)
0x234a2  stloc.3
0x234a3  ldloc.3
0x234a4  brfalse.s loc_234DB
0x234a6  ldloc.3
0x234a7  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::AuthenticateUser(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken)
0x234ac  stloc.s  6
0x234ae  ldloc.s  6
0x234b0  ldnull
0x234b1  ldloc.3
0x234b2  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x234b7  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x234bc  ldloc.3
0x234bd  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x234c2  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x234c7  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal, string, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x234cc  stloc.s  4
0x234ce  ldloc.s  4
0x234d0  ldarg.1
0x234d1  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsPersistent()
0x234d6  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::set_IsPersistent(bool)
0x234db  leave.s  loc_2352F
0x234dd  stloc.s  7
0x234df  ldloc.s  7
0x234e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sharepoint"...
0x234e6  ldstr    aSessionrevoked// "SessionRevokedByIdentityProvider"
0x234eb  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceFailureUtilities::IsSpecificTokenIssuanceFailureException(class [mscorlib]System.Exception, string, string)
0x234f0  stloc.s  8
0x234f2  ldloc.s  8
0x234f4  brfalse.s loc_234F8
0x234f6  rethrow
0x234f8  ldc.i4   0xDB41F
0x234fd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23502  ldc.i4.s 0xA
0x23504  ldstr    aTokenCacheFail_1// "Token Cache: Failed to rebuild the toke"...
0x23509  ldc.i4.2
0x2350a  newarr   [mscorlib]System.Object
0x2350f  stloc.s  0xB
0x23511  ldloc.s  0xB
0x23513  ldc.i4.0
0x23514  ldarg.1
0x23515  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x2351a  stelem.ref
0x2351b  ldloc.s  0xB
0x2351d  ldc.i4.1
0x2351e  ldloc.s  7
0x23520  callvirt instance string [mscorlib]System.Object::ToString()
0x23525  stelem.ref
0x23526  ldloc.s  0xB
0x23528  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2352d  leave.s  loc_2352F
0x2352f  ldloc.s  4
0x23531  ret
```
