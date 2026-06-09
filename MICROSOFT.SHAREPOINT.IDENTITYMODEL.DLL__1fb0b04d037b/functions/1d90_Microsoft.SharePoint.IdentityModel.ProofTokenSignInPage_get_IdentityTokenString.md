# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_IdentityTokenString

- ea: `0x1d90`
- end: `0x1e09`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_IdentityTokenString`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1e40`
- `0x2780`
- `0x27a0`

## callees

- `0x1d90`

## string_xrefs

- `0x1db1`: `ProofTokenSignIn: Identity token string read from local variable. Token: '{0}'.`
- `0x1dd4`: `IdentityToken`
- `0x1dec`: `ProofTokenSignIn: Identity token string read from form parameters. Token: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1d90  ldsfld   string [mscorlib]System.String::Empty
0x1d95  stloc.0
0x1d96  ldarg.0
0x1d97  ldfld    string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::m_IdentityTokenString
0x1d9c  brfalse.s loc_1DCE
0x1d9e  ldarg.0
0x1d9f  ldfld    string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::m_IdentityTokenString
0x1da4  stloc.0
0x1da5  ldc.i4   0x35F789
0x1daa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1daf  ldc.i4.s 0x64
0x1db1  ldstr    aProoftokensign_3// "ProofTokenSignIn: Identity token string"...
0x1db6  ldc.i4.1
0x1db7  newarr   [mscorlib]System.Object
0x1dbc  stloc.1
0x1dbd  ldloc.1
0x1dbe  ldc.i4.0
0x1dbf  ldloc.0
0x1dc0  call     string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHelper::GetSafeForLoggingTokenString(string)
0x1dc5  stelem.ref
0x1dc6  ldloc.1
0x1dc7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1dcc  br.s     loc_1E07
0x1dce  ldarg.0
0x1dcf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1dd4  ldstr    aIdentitytoken// "IdentityToken"
0x1dd9  ldc.i4.1
0x1dda  call     T0x2B000002
0x1ddf  stloc.0
0x1de0  ldc.i4   0x35F78A
0x1de5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1dea  ldc.i4.s 0x64
0x1dec  ldstr    aProoftokensign_4// "ProofTokenSignIn: Identity token string"...
0x1df1  ldc.i4.1
0x1df2  newarr   [mscorlib]System.Object
0x1df7  stloc.2
0x1df8  ldloc.2
0x1df9  ldc.i4.0
0x1dfa  ldloc.0
0x1dfb  call     string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHelper::GetSafeForLoggingTokenString(string)
0x1e00  stelem.ref
0x1e01  ldloc.2
0x1e02  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1e07  ldloc.0
0x1e08  ret
```
