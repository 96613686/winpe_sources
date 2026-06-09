# Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::ValidateCookieAudience

- ea: `0x22130`
- end: `0x22222`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::ValidateCookieAudience`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x22280`

## callees

- `0x8c40`
- `0x207c0`
- `0x209b0`
- `0x21b70`
- `0x22130`

## string_xrefs

- `0x22164`: `Token Request Data: Cookie does not have audience Uri set.`
- `0x22196`: `Token Request Data: Cookie has failed audience validation. AudienceUri: '{0}'.`
- `0x221c6`: `Token Request Data: Cookie audience validation was successful. AudienceUri: '{0}'.`
- `0x221f6`: `Token Request Data: Cookie has failed audience validation. Validation mode not supported: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x22130  ldc.i4.0
0x22131  stloc.0
0x22132  ldarg.0
0x22133  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x22138  callvirt instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_ValidationMode()
0x2213d  stloc.1
0x2213e  ldloc.1
0x2213f  ldc.i4.1
0x22140  bne.un   loc_221EA
0x22145  ldarg.0
0x22146  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2214b  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AudienceUri()
0x22150  ldnull
0x22151  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x22156  brfalse.s loc_22175
0x22158  ldc.i4   0x12078A2
0x2215d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22162  ldc.i4.s 0xA
0x22164  ldstr    aTokenRequestDa_21// "Token Request Data: Cookie does not hav"...
0x22169  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2216e  ldc.i4.0
0x2216f  stloc.0
0x22170  br       loc_22220
0x22175  ldarg.0
0x22176  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2217b  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AudienceUri()
0x22180  ldarg.1
0x22181  ldarg.2
0x22182  ldnull
0x22183  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateSingleAudienceCondition(class [System]System.Uri audienceUri, valuetype [mscorlib]System.Guid requestWebAppId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone requestZone, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> trustedLoginProviderNames)
0x22188  brtrue.s loc_221BA
0x2218a  ldc.i4   0x12078A3
0x2218f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22194  ldc.i4.s 0xA
0x22196  ldstr    aTokenRequestDa_22// "Token Request Data: Cookie has failed a"...
0x2219b  ldc.i4.1
0x2219c  newarr   [mscorlib]System.Object
0x221a1  stloc.2
0x221a2  ldloc.2
0x221a3  ldc.i4.0
0x221a4  ldarg.0
0x221a5  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x221aa  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AudienceUri()
0x221af  stelem.ref
0x221b0  ldloc.2
0x221b1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x221b6  ldc.i4.0
0x221b7  stloc.0
0x221b8  br.s     loc_22220
0x221ba  ldc.i4   0x12078C0
0x221bf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x221c4  ldc.i4.s 0x64
0x221c6  ldstr    aTokenRequestDa_23// "Token Request Data: Cookie audience val"...
0x221cb  ldc.i4.1
0x221cc  newarr   [mscorlib]System.Object
0x221d1  stloc.3
0x221d2  ldloc.3
0x221d3  ldc.i4.0
0x221d4  ldarg.0
0x221d5  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x221da  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AudienceUri()
0x221df  stelem.ref
0x221e0  ldloc.3
0x221e1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x221e6  ldc.i4.1
0x221e7  stloc.0
0x221e8  br.s     loc_22220
0x221ea  ldc.i4   0x12078C1
0x221ef  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x221f4  ldc.i4.s 0xA
0x221f6  ldstr    aTokenRequestDa_24// "Token Request Data: Cookie has failed a"...
0x221fb  ldc.i4.1
0x221fc  newarr   [mscorlib]System.Object
0x22201  stloc.s  4
0x22203  ldloc.s  4
0x22205  ldc.i4.0
0x22206  ldarg.0
0x22207  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2220c  callvirt instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_ValidationMode()
0x22211  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x22216  stelem.ref
0x22217  ldloc.s  4
0x22219  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2221e  ldc.i4.0
0x2221f  stloc.0
0x22220  ldloc.0
0x22221  ret
```
