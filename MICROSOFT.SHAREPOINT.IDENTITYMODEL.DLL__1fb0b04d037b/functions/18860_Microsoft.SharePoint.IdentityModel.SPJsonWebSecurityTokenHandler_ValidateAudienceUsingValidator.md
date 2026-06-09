# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateAudienceUsingValidator

- ea: `0x18860`
- end: `0x1896a`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateAudienceUsingValidator`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x181b0`

## callees

- `0x16770`
- `0x18180`
- `0x18860`

## string_xrefs

- `0x18879`: `token`
- `0x1886f`: `The token is null.`
- `0x188ef`: `SPJsonWebSecurityTokenHandler: Audience Validation succeeded.`
- `0x18908`: `Got SPAudienceValidatorInitializationException tying to validate audience for json token.`
- `0x18921`: `Got NullReferenceException tying to validate audience for json token.`

## pseudocode

```c

```

## disassembly

```asm
0x18860  ldarg.1
0x18861  brtrue.s loc_18884
0x18863  ldc.i4   0x80935D
0x18868  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1886d  ldc.i4.s 0xA
0x1886f  ldstr    aTheTokenIsNull// "The token is null."
0x18874  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18879  ldstr    aToken// "token"
0x1887e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18883  throw
0x18884  ldarg.0
0x18885  ldfld    class Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::m_AudienceValidator
0x1888a  brtrue.s loc_188A8
0x1888c  ldc.i4   0x128F4D9
0x18891  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18896  ldc.i4.s 0xA
0x18898  ldstr    aMAudiencevalid// "m_AudienceValidator is null."
0x1889d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x188a2  newobj   instance void [mscorlib]System.NullReferenceException::.ctor()
0x188a7  throw
0x188a8  ldarg.0
0x188a9  ldfld    class Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::m_AudienceValidator
0x188ae  ldarg.1
0x188af  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::ValidateAudience(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x188b4  brtrue.s loc_188E3
0x188b6  ldc.i4   0x80935E
0x188bb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x188c0  ldc.i4.s 0xA
0x188c2  ldstr    aAudienceValida_4// "Audience Validation failed."
0x188c7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x188cc  ldarg.1
0x188cd  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x188d2  ldc.i4.0
0x188d3  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x188d8  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException::.ctor()
0x188dd  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException)
0x188e2  throw
0x188e3  ldc.i4   0x80935F
0x188e8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x188ed  ldc.i4.s 0x32
0x188ef  ldstr    aSpjsonwebsecur_5// "SPJsonWebSecurityTokenHandler: Audience"...
0x188f4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x188f9  leave.s  loc_18969
0x188fb  pop
0x188fc  ldc.i4   0x809360
0x18901  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18906  ldc.i4.s 0xA
0x18908  ldstr    aGotSpaudiencev// "Got SPAudienceValidatorInitializationEx"...
0x1890d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18912  rethrow
0x18914  pop
0x18915  ldc.i4   0x128F4DA
0x1891a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1891f  ldc.i4.s 0xA
0x18921  ldstr    aGotNullreferen// "Got NullReferenceException tying to val"...
0x18926  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1892b  rethrow
0x1892d  stloc.0
0x1892e  ldc.i4   0x809361
0x18933  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18938  ldc.i4.s 0xA
0x1893a  ldstr    aExceptionValid_3// "Exception validating audience. Exceptio"...
0x1893f  ldc.i4.1
0x18940  newarr   [mscorlib]System.Object
0x18945  stloc.1
0x18946  ldloc.1
0x18947  ldc.i4.0
0x18948  ldloc.0
0x18949  stelem.ref
0x1894a  ldloc.1
0x1894b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x18950  ldarg.1
0x18951  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x18956  ldc.i4.0
0x18957  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x1895c  ldnull
0x1895d  ldloc.0
0x1895e  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException::.ctor(string, class [mscorlib]System.Exception)
0x18963  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException)
0x18968  throw
0x18969  ret
```
