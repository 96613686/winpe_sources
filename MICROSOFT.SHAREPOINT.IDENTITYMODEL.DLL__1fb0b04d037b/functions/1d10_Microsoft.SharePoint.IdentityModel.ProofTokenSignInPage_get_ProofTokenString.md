# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_ProofTokenString

- ea: `0x1d10`
- end: `0x1d89`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_ProofTokenString`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1e10`
- `0x2780`
- `0x27a0`

## callees

- `0x1d10`

## string_xrefs

- `0x1d31`: `ProofTokenSignIn: Proof token string read from local variable. Token: '{0}'.`
- `0x1d54`: `ProofToken`
- `0x1d6c`: `ProofTokenSignIn: Proof token string read from form parameters. Token: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1d10  ldsfld   string [mscorlib]System.String::Empty
0x1d15  stloc.0
0x1d16  ldarg.0
0x1d17  ldfld    string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::m_ProofTokenString
0x1d1c  brfalse.s loc_1D4E
0x1d1e  ldarg.0
0x1d1f  ldfld    string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::m_ProofTokenString
0x1d24  stloc.0
0x1d25  ldc.i4   0x35F787
0x1d2a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1d2f  ldc.i4.s 0x64
0x1d31  ldstr    aProoftokensign_1// "ProofTokenSignIn: Proof token string re"...
0x1d36  ldc.i4.1
0x1d37  newarr   [mscorlib]System.Object
0x1d3c  stloc.1
0x1d3d  ldloc.1
0x1d3e  ldc.i4.0
0x1d3f  ldloc.0
0x1d40  call     string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHelper::GetSafeForLoggingTokenString(string)
0x1d45  stelem.ref
0x1d46  ldloc.1
0x1d47  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1d4c  br.s     loc_1D87
0x1d4e  ldarg.0
0x1d4f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1d54  ldstr    aProoftoken// "ProofToken"
0x1d59  ldc.i4.1
0x1d5a  call     T0x2B000002
0x1d5f  stloc.0
0x1d60  ldc.i4   0x35F788
0x1d65  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1d6a  ldc.i4.s 0x64
0x1d6c  ldstr    aProoftokensign_2// "ProofTokenSignIn: Proof token string re"...
0x1d71  ldc.i4.1
0x1d72  newarr   [mscorlib]System.Object
0x1d77  stloc.2
0x1d78  ldloc.2
0x1d79  ldc.i4.0
0x1d7a  ldloc.0
0x1d7b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHelper::GetSafeForLoggingTokenString(string)
0x1d80  stelem.ref
0x1d81  ldloc.2
0x1d82  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1d87  ldloc.0
0x1d88  ret
```
