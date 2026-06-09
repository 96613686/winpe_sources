# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::IsS2SRequest

- ea: `0x1a1f0`
- end: `0x1a2e2`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::IsS2SRequest`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a0d0`

## callees

- `0x17890`
- `0x1a1f0`

## string_xrefs

- `0x1a224`: `Expected OnBehalfOf token, but it was null.`
- `0x1a250`: `Token is not a JWT.`
- `0x1a270`: `JWT inner actor token not present.`

## pseudocode

```c

```

## disassembly

```asm
0x1a1f0  ldc.i4.0
0x1a1f1  stloc.0
0x1a1f2  ldarg.1
0x1a1f3  brtrue.s loc_1A210
0x1a1f5  ldc.i4   0x11D08D8
0x1a1fa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a1ff  ldc.i4.s 0xA
0x1a201  ldstr    aRequestWasNull// "request was null."
0x1a206  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a20b  br       loc_1A2AF
0x1a210  ldarg.1
0x1a211  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x1a216  brtrue.s loc_1A230
0x1a218  ldc.i4   0x11D08D9
0x1a21d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a222  ldc.i4.s 0xA
0x1a224  ldstr    aExpectedOnbeha// "Expected OnBehalfOf token, but it was n"...
0x1a229  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a22e  br.s     loc_1A2AF
0x1a230  ldarg.1
0x1a231  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x1a236  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSecurityToken()
0x1a23b  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x1a240  stloc.1
0x1a241  ldloc.1
0x1a242  brtrue.s loc_1A25C
0x1a244  ldc.i4   0x11D08DA
0x1a249  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a24e  ldc.i4.s 0xF
0x1a250  ldstr    aTokenIsNotAJwt// "Token is not a JWT."
0x1a255  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a25a  br.s     loc_1A2AF
0x1a25c  ldloc.1
0x1a25d  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x1a262  brtrue.s loc_1A27C
0x1a264  ldc.i4   0x11D08DB
0x1a269  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a26e  ldc.i4.s 0x64
0x1a270  ldstr    aJwtInnerActorT// "JWT inner actor token not present."
0x1a275  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a27a  br.s     loc_1A2AF
0x1a27c  ldloc.1
0x1a27d  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x1a282  call     bool Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsTrustedForDelegation(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken identity)
0x1a287  stloc.0
0x1a288  ldc.i4   0x11D08DD
0x1a28d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a292  ldc.i4.s 0x32
0x1a294  ldstr    aCheckedIfReque// "Checked if request was S2S. Result: '{0"...
0x1a299  ldc.i4.1
0x1a29a  newarr   [mscorlib]System.Object
0x1a29f  stloc.3
0x1a2a0  ldloc.3
0x1a2a1  ldc.i4.0
0x1a2a2  ldloc.0
0x1a2a3  box      [mscorlib]System.Boolean
0x1a2a8  stelem.ref
0x1a2a9  ldloc.3
0x1a2aa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1a2af  leave.s  loc_1A2E0
0x1a2b1  stloc.2
0x1a2b2  ldc.i4   0x11D08DE
0x1a2b7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a2bc  ldc.i4.s 0xA
0x1a2be  ldstr    aExceptionDeter// "Exception determining if OAuth request "...
0x1a2c3  ldc.i4.1
0x1a2c4  newarr   [mscorlib]System.Object
0x1a2c9  stloc.s  4
0x1a2cb  ldloc.s  4
0x1a2cd  ldc.i4.0
0x1a2ce  ldloc.2
0x1a2cf  callvirt instance string [mscorlib]System.Object::ToString()
0x1a2d4  stelem.ref
0x1a2d5  ldloc.s  4
0x1a2d7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1a2dc  ldc.i4.0
0x1a2dd  stloc.0
0x1a2de  leave.s  loc_1A2E0
0x1a2e0  ldloc.0
0x1a2e1  ret
```
