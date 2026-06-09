# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetJwtIdentityToken

- ea: `0x1a5b0`
- end: `0x1a6d3`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetJwtIdentityToken`
- size: `291`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a2f0`
- `0x1b5b0`
- `0x1b670`

## callees

- `0x1a5b0`
- `0x1a6e0`

## string_xrefs

- `0x1a5da`: `TryGetJwtIdentityToken: Request is null.`
- `0x1a5fd`: `TryGetJwtIdentityToken: Expected OnBehalfOf token, but it was null.`
- `0x1a627`: `TryGetJwtIdentityToken: Failed to get security token from request.`
- `0x1a651`: `TryGetJwtIdentityToken: Could not extract identity jwt token.`
- `0x1a669`: `TryGetJwtIdentityToken: Successfully got the identity jwt token. IsProofToken: '{0}'.`
- `0x1a6b1`: `TryGetJwtIdentityToken: Exception encountered. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1a5b0  ldarg.0
0x1a5b1  ldfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_JsonToken
0x1a5b6  brfalse.s loc_1A5C2
0x1a5b8  ldarg.2
0x1a5b9  ldarg.0
0x1a5ba  ldfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_JsonToken
0x1a5bf  stind.ref
0x1a5c0  ldc.i4.1
0x1a5c1  ret
0x1a5c2  ldc.i4.0
0x1a5c3  stloc.0
0x1a5c4  ldarg.2
0x1a5c5  ldnull
0x1a5c6  stind.ref
0x1a5c7  ldnull
0x1a5c8  stloc.1
0x1a5c9  ldc.i4.0
0x1a5ca  stloc.2
0x1a5cb  ldarg.1
0x1a5cc  brtrue.s loc_1A5E9
0x1a5ce  ldc.i4   0x1405318
0x1a5d3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a5d8  ldc.i4.s 0xA
0x1a5da  ldstr    aTrygetjwtident// "TryGetJwtIdentityToken: Request is null"...
0x1a5df  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a5e4  br       loc_1A69D
0x1a5e9  ldarg.1
0x1a5ea  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x1a5ef  brtrue.s loc_1A60C
0x1a5f1  ldc.i4   0x1405319
0x1a5f6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a5fb  ldc.i4.s 0xA
0x1a5fd  ldstr    aTrygetjwtident_0// "TryGetJwtIdentityToken: Expected OnBeha"...
0x1a602  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a607  br       loc_1A69D
0x1a60c  ldarg.1
0x1a60d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x1a612  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSecurityToken()
0x1a617  dup
0x1a618  stloc.1
0x1a619  brtrue.s loc_1A633
0x1a61b  ldc.i4   0x140531A
0x1a620  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a625  ldc.i4.s 0xA
0x1a627  ldstr    aTrygetjwtident_1// "TryGetJwtIdentityToken: Failed to get s"...
0x1a62c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a631  br.s     loc_1A69D
0x1a633  ldarg.2
0x1a634  ldarg.0
0x1a635  ldloc.1
0x1a636  ldloca.s 2
0x1a638  call     instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetJwtIdentityToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token, [out] bool& isProofToken)
0x1a63d  dup
0x1a63e  stloc.s  4
0x1a640  stind.ref
0x1a641  ldloc.s  4
0x1a643  brtrue.s loc_1A65D
0x1a645  ldc.i4   0x140531B
0x1a64a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a64f  ldc.i4.s 0x32
0x1a651  ldstr    aTrygetjwtident_2// "TryGetJwtIdentityToken: Could not extra"...
0x1a656  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a65b  br.s     loc_1A69D
0x1a65d  ldc.i4   0x140531C
0x1a662  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a667  ldc.i4.s 0x64
0x1a669  ldstr    aTrygetjwtident_3// "TryGetJwtIdentityToken: Successfully go"...
0x1a66e  ldc.i4.1
0x1a66f  newarr   [mscorlib]System.Object
0x1a674  stloc.s  5
0x1a676  ldloc.s  5
0x1a678  ldc.i4.0
0x1a679  ldloc.2
0x1a67a  box      [mscorlib]System.Boolean
0x1a67f  stelem.ref
0x1a680  ldloc.s  5
0x1a682  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1a687  ldarg.0
0x1a688  ldarg.2
0x1a689  ldind.ref
0x1a68a  stfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_JsonToken
0x1a68f  ldarg.0
0x1a690  ldloc.2
0x1a691  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a696  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_IsProofToken
0x1a69b  ldc.i4.1
0x1a69c  stloc.0
0x1a69d  leave.s  loc_1A6D1
0x1a69f  stloc.3
0x1a6a0  ldc.i4.0
0x1a6a1  stloc.0
0x1a6a2  ldarg.2
0x1a6a3  ldnull
0x1a6a4  stind.ref
0x1a6a5  ldc.i4   0x140531D
0x1a6aa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a6af  ldc.i4.s 0xA
0x1a6b1  ldstr    aTrygetjwtident_4// "TryGetJwtIdentityToken: Exception encou"...
0x1a6b6  ldc.i4.1
0x1a6b7  newarr   [mscorlib]System.Object
0x1a6bc  stloc.s  6
0x1a6be  ldloc.s  6
0x1a6c0  ldc.i4.0
0x1a6c1  ldloc.3
0x1a6c2  callvirt instance string [mscorlib]System.Object::ToString()
0x1a6c7  stelem.ref
0x1a6c8  ldloc.s  6
0x1a6ca  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1a6cf  leave.s  loc_1A6D1
0x1a6d1  ldloc.0
0x1a6d2  ret
```
