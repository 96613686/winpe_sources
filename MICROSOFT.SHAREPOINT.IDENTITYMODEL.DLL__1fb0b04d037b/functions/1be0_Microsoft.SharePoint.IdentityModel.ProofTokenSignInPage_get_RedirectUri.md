# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_RedirectUri

- ea: `0x1be0`
- end: `0x1c83`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_RedirectUri`
- size: `163`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1c90`
- `0x1e70`
- `0x2110`
- `0x2250`
- `0x2300`
- `0x27a0`

## callees

- `0x1be0`
- `0x2830`

## string_xrefs

- `0x1be8`: `redirect_uri`
- `0x1c02`: `RedirectUriFlags`
- `0x1c2e`: `ProofTokenSignIn: RedirectUri after apply flag is {0}`
- `0x1c68`: `ProofTokenSignIn: Redirect Uri is null, empty or not a valid uri. The value is {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1be0  ldnull
0x1be1  stloc.0
0x1be2  ldarg.0
0x1be3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1be8  ldstr    aRedirectUri// "redirect_uri"
0x1bed  ldc.i4.0
0x1bee  call     T0x2B000002
0x1bf3  stloc.1
0x1bf4  ldloc.1
0x1bf5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1bfa  brtrue.s loc_1C49
0x1bfc  ldarg.0
0x1bfd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1c02  ldstr    aRedirecturifla// "RedirectUriFlags"
0x1c07  ldc.i4.0
0x1c08  call     T0x2B000002
0x1c0d  stloc.2
0x1c0e  ldloc.2
0x1c0f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1c14  brtrue.s loc_1C49
0x1c16  ldarg.0
0x1c17  ldloc.1
0x1c18  ldloc.2
0x1c19  ldloca.s 3
0x1c1b  call     instance bool Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::TryResolveRedirectUriUsingFlags(string redirectUri, string redirectUriFlags, [out] string& result)
0x1c20  brfalse.s loc_1C49
0x1c22  ldc.i4   0x49C402
0x1c27  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1c2c  ldc.i4.s 0x32
0x1c2e  ldstr    aProoftokensign// "ProofTokenSignIn: RedirectUri after app"...
0x1c33  ldc.i4.1
0x1c34  newarr   [mscorlib]System.Object
0x1c39  stloc.s  4
0x1c3b  ldloc.s  4
0x1c3d  ldc.i4.0
0x1c3e  ldloc.3
0x1c3f  stelem.ref
0x1c40  ldloc.s  4
0x1c42  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1c47  ldloc.3
0x1c48  stloc.1
0x1c49  ldloc.1
0x1c4a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1c4f  brtrue.s loc_1C5C
0x1c51  ldloc.1
0x1c52  ldc.i4.1
0x1c53  ldloca.s 0
0x1c55  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x1c5a  brtrue.s loc_1C81
0x1c5c  ldc.i4   0x35F786
0x1c61  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1c66  ldc.i4.s 0x14
0x1c68  ldstr    aProoftokensign_0// "ProofTokenSignIn: Redirect Uri is null,"...
0x1c6d  ldc.i4.1
0x1c6e  newarr   [mscorlib]System.Object
0x1c73  stloc.s  5
0x1c75  ldloc.s  5
0x1c77  ldc.i4.0
0x1c78  ldloc.1
0x1c79  stelem.ref
0x1c7a  ldloc.s  5
0x1c7c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1c81  ldloc.0
0x1c82  ret
```
