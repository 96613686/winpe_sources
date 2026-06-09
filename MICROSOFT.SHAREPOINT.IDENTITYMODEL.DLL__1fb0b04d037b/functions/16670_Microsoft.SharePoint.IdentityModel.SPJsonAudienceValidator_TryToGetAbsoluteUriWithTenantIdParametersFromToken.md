# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAbsoluteUriWithTenantIdParametersFromToken

- ea: `0x16670`
- end: `0x1676f`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAbsoluteUriWithTenantIdParametersFromToken`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16770`

## callees

- `0x97b0`
- `0x97d0`
- `0x98c0`
- `0x16670`
- `0x1bf90`

## string_xrefs

- `0x1667f`: `The token is null.`
- `0x166b7`: `The token audience is not an absolute URI.`
- `0x166e5`: `The token has no tenant identifier claim. ClaimType: '{0}'.`
- `0x16730`: `The token has an absolute audience uri and a tenant id.`

## pseudocode

```c

```

## disassembly

```asm
0x16670  ldarg.1
0x16671  brtrue.s loc_1668E
0x16673  ldc.i4   0x80934B
0x16678  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1667d  ldc.i4.s 0xA
0x1667f  ldstr    aTheTokenIsNull// "The token is null."
0x16684  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16689  ldarg.2
0x1668a  ldnull
0x1668b  stind.ref
0x1668c  ldc.i4.0
0x1668d  ret
0x1668e  ldc.i4.0
0x1668f  stloc.0
0x16690  ldarg.2
0x16691  ldnull
0x16692  stind.ref
0x16693  ldnull
0x16694  stloc.1
0x16695  ldsfld   string [mscorlib]System.String::Empty
0x1669a  pop
0x1669b  ldarg.1
0x1669c  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x166a1  ldc.i4.1
0x166a2  ldloca.s 1
0x166a4  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x166a9  brtrue.s loc_166C5
0x166ab  ldc.i4   0x80934C
0x166b0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x166b5  ldc.i4.s 0x32
0x166b7  ldstr    aTheTokenAudien_0// "The token audience is not an absolute U"...
0x166bc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x166c1  ldc.i4.0
0x166c2  stloc.0
0x166c3  br.s     loc_1673A
0x166c5  ldarg.1
0x166c6  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x166cb  ldstr    aTid// "tid"
0x166d0  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x166d5  stloc.2
0x166d6  ldloc.2
0x166d7  brtrue.s loc_16706
0x166d9  ldc.i4   0x80934D
0x166de  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x166e3  ldc.i4.s 0xA
0x166e5  ldstr    aTheTokenHasNoT// "The token has no tenant identifier clai"...
0x166ea  ldc.i4.1
0x166eb  newarr   [mscorlib]System.Object
0x166f0  stloc.s  5
0x166f2  ldloc.s  5
0x166f4  ldc.i4.0
0x166f5  ldstr    aTid// "tid"
0x166fa  stelem.ref
0x166fb  ldloc.s  5
0x166fd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16702  ldc.i4.0
0x16703  stloc.0
0x16704  br.s     loc_1673A
0x16706  ldarg.2
0x16707  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::.ctor()
0x1670c  stloc.3
0x1670d  ldloc.3
0x1670e  ldloc.1
0x1670f  callvirt instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::set_AudienceUri(class [System]System.Uri value)
0x16714  ldloc.3
0x16715  ldloc.2
0x16716  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1671b  callvirt instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::set_TenantId(string value)
0x16720  ldloc.3
0x16721  stind.ref
0x16722  ldc.i4.1
0x16723  stloc.0
0x16724  ldc.i4   0x80934E
0x16729  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1672e  ldc.i4.s 0x64
0x16730  ldstr    aTheTokenHasAnA_0// "The token has an absolute audience uri "...
0x16735  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1673a  leave.s  loc_1676D
0x1673c  stloc.s  4
0x1673e  ldc.i4   0x80934F
0x16743  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16748  ldc.i4.s 0xA
0x1674a  ldstr    aExceptionBuild// "Exception building audience paramters. "...
0x1674f  ldc.i4.1
0x16750  newarr   [mscorlib]System.Object
0x16755  stloc.s  6
0x16757  ldloc.s  6
0x16759  ldc.i4.0
0x1675a  ldloc.s  4
0x1675c  callvirt instance string [mscorlib]System.Object::ToString()
0x16761  stelem.ref
0x16762  ldloc.s  6
0x16764  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16769  ldc.i4.0
0x1676a  stloc.0
0x1676b  leave.s  loc_1676D
0x1676d  ldloc.0
0x1676e  ret
```
