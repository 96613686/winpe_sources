# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::SetIdentityUsingProofToken

- ea: `0x2370`
- end: `0x241a`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::SetIdentityUsingProofToken`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x27a0`

## callees

- `0x150`
- `0x2420`
- `0x24c0`
- `0x2690`
- `0x2c520`

## string_xrefs

- `0x237f`: `token`
- `0x239d`: `ProofTokenSignIn: Exchanging proof token with a locally issued token.`
- `0x23ce`: `ProofTokenSignIn: Exchanged proof token with a locally issued token.`
- `0x23f9`: `ProofTokenSignIn: Successfully logged the user in. SessionTokenWriteType: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x2370  ldc.i4   0x175A1C3
0x2375  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x237a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x237f  ldstr    aToken// "token"
0x2384  ldarg.1
0x2385  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x238a  ldarg.0
0x238b  ldarg.1
0x238c  call     instance void Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::BlockPreAuthProofToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken token)
0x2391  ldc.i4   0x35F799
0x2396  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x239b  ldc.i4.s 0x32
0x239d  ldstr    aProoftokensign_20// "ProofTokenSignIn: Exchanging proof toke"...
0x23a2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23a7  ldarg.0
0x23a8  ldarg.1
0x23a9  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes> Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::GetSessionAttributesFromToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken token)
0x23ae  stloc.0
0x23af  ldarg.1
0x23b0  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_IdentityToken()
0x23b5  ldarg.1
0x23b6  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_ProofToken()
0x23bb  ldloc.0
0x23bc  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::SecurityTokenForProofTokenAuthentication(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes>)
0x23c1  stloc.1
0x23c2  ldc.i4   0x35F79A
0x23c7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x23cc  ldc.i4.s 0x64
0x23ce  ldstr    aProoftokensign_21// "ProofTokenSignIn: Exchanged proof token"...
0x23d3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23d8  ldarg.0
0x23d9  ldarg.1
0x23da  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_IdentityToken()
0x23df  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPSessionTokenWriteType Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::GetSessionTokenWriteType(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken)
0x23e4  stloc.2
0x23e5  ldarg.0
0x23e6  ldloc.1
0x23e7  ldloc.2
0x23e8  call     instance void Microsoft.SharePoint.IdentityModel.Pages.IdentityModelSignInPageBase::EstablishSessionWithToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken, valuetype Microsoft.SharePoint.IdentityModel.SPSessionTokenWriteType sessionCookie)
0x23ed  ldc.i4   0x35F79B
0x23f2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x23f7  ldc.i4.s 0x32
0x23f9  ldstr    aProoftokensign_22// "ProofTokenSignIn: Successfully logged t"...
0x23fe  ldc.i4.1
0x23ff  newarr   [mscorlib]System.Object
0x2404  stloc.3
0x2405  ldloc.3
0x2406  ldc.i4.0
0x2407  ldloc.2
0x2408  box      Microsoft.SharePoint.IdentityModel.SPSessionTokenWriteType
0x240d  callvirt instance string [mscorlib]System.Object::ToString()
0x2412  stelem.ref
0x2413  ldloc.3
0x2414  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2419  ret
```
