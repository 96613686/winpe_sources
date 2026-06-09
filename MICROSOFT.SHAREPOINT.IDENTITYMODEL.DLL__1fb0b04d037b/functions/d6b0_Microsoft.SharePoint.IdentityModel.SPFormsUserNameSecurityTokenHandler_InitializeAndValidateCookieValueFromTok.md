# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::InitializeAndValidateCookieValueFromToken

- ea: `0xd6b0`
- end: `0xd75b`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::InitializeAndValidateCookieValueFromToken`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xd400`

## callees

- `0x1ae0`
- `0xd240`
- `0xd6b0`
- `0x21960`

## string_xrefs

- `0xd6c4`: `ValidateOriginalCookie: Received null userToken.`
- `0xd71a`: `ValidateOriginalCookie: Inconsistent cookie, username does not match. Token username: <name>{0}</name>. Cookie username: <name>{1}</name>.`

## pseudocode

```c

```

## disassembly

```asm
0xd6b0  ldc.i4.0
0xd6b1  stloc.0
0xd6b2  ldarg.2
0xd6b3  ldnull
0xd6b4  stind.ref
0xd6b5  ldarg.1
0xd6b6  brtrue.s loc_D6D3
0xd6b8  ldc.i4   0x11D880A
0xd6bd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd6c2  ldc.i4.s 0xA
0xd6c4  ldstr    aValidateorigin// "ValidateOriginalCookie: Received null u"...
0xd6c9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xd6ce  br       loc_D759
0xd6d3  ldarg.1
0xd6d4  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_Password()
0xd6d9  ldarg.2
0xd6da  call     bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::CreateAndValidateCookieValue(string cookieValue, [out] class Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue& resultCookie)
0xd6df  brtrue.s loc_D6F9
0xd6e1  ldc.i4   0x11D880B
0xd6e6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd6eb  ldc.i4.s 0x14
0xd6ed  ldstr    aValidateorigin_0// "ValidateOriginalCookie: Cookie string i"...
0xd6f2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xd6f7  br.s     loc_D759
0xd6f9  ldarg.2
0xd6fa  ldind.ref
0xd6fb  callvirt instance string Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue::get_UserName()
0xd700  ldarg.1
0xd701  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd706  ldc.i4.5
0xd707  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xd70c  brtrue.s loc_D741
0xd70e  ldc.i4   0x11D880C
0xd713  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd718  ldc.i4.s 0xA
0xd71a  ldstr    aValidateorigin_1// "ValidateOriginalCookie: Inconsistent co"...
0xd71f  ldc.i4.2
0xd720  newarr   [mscorlib]System.Object
0xd725  stloc.1
0xd726  ldloc.1
0xd727  ldc.i4.0
0xd728  ldarg.1
0xd729  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd72e  stelem.ref
0xd72f  ldloc.1
0xd730  ldc.i4.1
0xd731  ldarg.2
0xd732  ldind.ref
0xd733  callvirt instance string Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue::get_UserName()
0xd738  stelem.ref
0xd739  ldloc.1
0xd73a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xd73f  br.s     loc_D759
0xd741  ldc.i4   0x11D880D
0xd746  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd74b  ldc.i4.s 0x64
0xd74d  ldstr    aValidateorigin_2// "ValidateOriginalCookie: Success."
0xd752  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xd757  ldc.i4.1
0xd758  stloc.0
0xd759  ldloc.0
0xd75a  ret
```
