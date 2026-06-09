# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::GetSessionAttributesFromToken

- ea: `0x24c0`
- end: `0x2587`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::GetSessionAttributesFromToken`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2370`

## callees

- `0x24c0`
- `0x2590`
- `0x134d0`
- `0x13680`

## string_xrefs

- `0x24de`: `GetSessionAttributesFromToken: Identity token is null.`
- `0x2509`: `GetSessionAttributesFromToken: Failed to parse jwt identity token.`
- `0x2538`: `GetSessionAttributesFromToken: Extracted the following session attributes from the proof token: '{0}'.`
- `0x2565`: `GetSessionAttributesFromToken: Failed to parse identity token. Ex: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x24c0  ldloca.s 0
0x24c2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes>
0x24c8  ldnull
0x24c9  stloc.1
0x24ca  ldarg.1
0x24cb  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_IdentityToken()
0x24d0  brtrue.s loc_24ED
0x24d2  ldc.i4   0x13DE600
0x24d7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x24dc  ldc.i4.s 0xA
0x24de  ldstr    aGetsessionattr// "GetSessionAttributesFromToken: Identity"...
0x24e3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24e8  br       loc_2585
0x24ed  ldarg.0
0x24ee  ldarg.1
0x24ef  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_IdentityToken()
0x24f4  ldloca.s 1
0x24f6  call     instance bool Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::TryParseJwtClaims(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token, [out] class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection& identityCollection)
0x24fb  brtrue.s loc_2515
0x24fd  ldc.i4   0x13DE601
0x2502  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2507  ldc.i4.s 0xA
0x2509  ldstr    aGetsessionattr_0// "GetSessionAttributesFromToken: Failed t"...
0x250e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2513  br.s     loc_2585
0x2515  ldarg.1
0x2516  ldloc.1
0x2517  newobj   instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection identity)
0x251c  stloc.2
0x251d  ldloc.2
0x251e  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_SessionAttributes()
0x2523  ldc.i4.2
0x2524  conv.i8
0x2525  or
0x2526  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes>::.ctor(var<u1>)
0x252b  stloc.0
0x252c  ldc.i4   0x13DE602
0x2531  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2536  ldc.i4.s 0x32
0x2538  ldstr    aGetsessionattr_1// "GetSessionAttributesFromToken: Extracte"...
0x253d  ldc.i4.1
0x253e  newarr   [mscorlib]System.Object
0x2543  stloc.s  4
0x2545  ldloc.s  4
0x2547  ldc.i4.0
0x2548  ldloc.0
0x2549  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes>
0x254e  stelem.ref
0x254f  ldloc.s  4
0x2551  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2556  leave.s  loc_2585
0x2558  stloc.3
0x2559  ldc.i4   0x13DE603
0x255e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2563  ldc.i4.s 0xA
0x2565  ldstr    aGetsessionattr_2// "GetSessionAttributesFromToken: Failed t"...
0x256a  ldc.i4.1
0x256b  newarr   [mscorlib]System.Object
0x2570  stloc.s  5
0x2572  ldloc.s  5
0x2574  ldc.i4.0
0x2575  ldloc.3
0x2576  callvirt instance string [mscorlib]System.Object::ToString()
0x257b  stelem.ref
0x257c  ldloc.s  5
0x257e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2583  leave.s  loc_2585
0x2585  ldloc.0
0x2586  ret
```
