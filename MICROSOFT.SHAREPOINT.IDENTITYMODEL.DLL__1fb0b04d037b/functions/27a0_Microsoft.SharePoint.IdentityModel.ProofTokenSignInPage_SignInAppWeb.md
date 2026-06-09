# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::SignInAppWeb

- ea: `0x27a0`
- end: `0x282c`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::SignInAppWeb`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1ec0`

## callees

- `0x1be0`
- `0x1d10`
- `0x1d90`
- `0x21a0`
- `0x2370`
- `0x27a0`
- `0x10ad0`
- `0x2c520`

## string_xrefs

- `0x27af`: `RedirectUri`
- `0x27bf`: `Login with Proof Token`
- `0x27f8`: `ProofTokenSignIn: Parsing incoming tokens.`

## pseudocode

```c

```

## disassembly

```asm
0x27a0  ldc.i4   0x175A1C5
0x27a5  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x27aa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x27af  ldstr    aRedirecturi// "RedirectUri"
0x27b4  ldarg.0
0x27b5  call     instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_RedirectUri()
0x27ba  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x27bf  ldstr    aLoginWithProof// "Login with Proof Token"
0x27c4  ldc.i4.s 0x32
0x27c6  ldc.i4.0
0x27c7  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x27cc  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x27d1  stloc.0
0x27d2  ldarg.0
0x27d3  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_ProofTokenString()
0x27d8  stloc.1
0x27d9  ldarg.0
0x27da  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_IdentityTokenString()
0x27df  stloc.2
0x27e0  ldarg.0
0x27e1  call     instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_RedirectUri()
0x27e6  callvirt instance string [System]System.Uri::get_OriginalString()
0x27eb  stloc.3
0x27ec  ldc.i4   0x35F7A0
0x27f1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x27f6  ldc.i4.s 0x32
0x27f8  ldstr    aProoftokensign_30// "ProofTokenSignIn: Parsing incoming toke"...
0x27fd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2802  ldloc.1
0x2803  ldloc.2
0x2804  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::CreateFromJsonWebToken(string proofTokenString, string identityTokenString)
0x2809  stloc.s  4
0x280b  ldloc.s  4
0x280d  brfalse.s loc_2817
0x280f  ldarg.0
0x2810  ldloc.s  4
0x2812  call     instance void Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::SetIdentityUsingProofToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken token)
0x2817  ldarg.0
0x2818  ldloc.3
0x2819  ldc.i4.2
0x281a  call     instance void Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::Redirect(string url, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPRedirectFlags redirectFlags)
0x281f  leave.s  loc_282B
0x2821  ldloc.0
0x2822  brfalse.s loc_282A
0x2824  ldloc.0
0x2825  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x282a  endfinally
0x282b  ret
```
