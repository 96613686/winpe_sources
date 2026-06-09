# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetJwtIdentityToken_0

- ea: `0x1a6e0`
- end: `0x1a785`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetJwtIdentityToken_0`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1a5b0`

## callees

- `0x1a6e0`

## string_xrefs

- `0x1a6fd`: `Successfully extracted identity JWT token for OAuth request.`
- `0x1a731`: `Successfully extracted identity JWT token from proof token.`
- `0x1a749`: `Could not find a JWT identity token for OAuth request.`
- `0x1a766`: `Exception encoutered while extracting JWT identity token. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1a6e0  ldnull
0x1a6e1  stloc.0
0x1a6e2  ldnull
0x1a6e3  stloc.1
0x1a6e4  ldarg.2
0x1a6e5  ldc.i4.0
0x1a6e6  stind.i1
0x1a6e7  ldarg.1
0x1a6e8  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x1a6ed  dup
0x1a6ee  stloc.0
0x1a6ef  brfalse.s loc_1A709
0x1a6f1  ldc.i4   0x13DB11A
0x1a6f6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a6fb  ldc.i4.s 0x32
0x1a6fd  ldstr    aSuccessfullyEx// "Successfully extracted identity JWT tok"...
0x1a702  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a707  br.s     loc_1A755
0x1a709  ldarg.1
0x1a70a  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken
0x1a70f  dup
0x1a710  stloc.1
0x1a711  brfalse.s loc_1A73D
0x1a713  ldloc.1
0x1a714  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_IdentityToken()
0x1a719  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x1a71e  dup
0x1a71f  stloc.0
0x1a720  brfalse.s loc_1A73D
0x1a722  ldarg.2
0x1a723  ldc.i4.1
0x1a724  stind.i1
0x1a725  ldc.i4   0x13DB11B
0x1a72a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a72f  ldc.i4.s 0x32
0x1a731  ldstr    aSuccessfullyEx_0// "Successfully extracted identity JWT tok"...
0x1a736  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a73b  br.s     loc_1A755
0x1a73d  ldc.i4   0x13DB11C
0x1a742  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a747  ldc.i4.s 0x64
0x1a749  ldstr    aCouldNotFindAJ// "Could not find a JWT identity token for"...
0x1a74e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a753  ldnull
0x1a754  stloc.0
0x1a755  leave.s  loc_1A783
0x1a757  stloc.2
0x1a758  ldnull
0x1a759  stloc.0
0x1a75a  ldc.i4   0x13DB11D
0x1a75f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a764  ldc.i4.s 0x32
0x1a766  ldstr    aExceptionEncou_0// "Exception encoutered while extracting J"...
0x1a76b  ldc.i4.1
0x1a76c  newarr   [mscorlib]System.Object
0x1a771  stloc.3
0x1a772  ldloc.3
0x1a773  ldc.i4.0
0x1a774  ldloc.2
0x1a775  callvirt instance string [mscorlib]System.Object::ToString()
0x1a77a  stelem.ref
0x1a77b  ldloc.3
0x1a77c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1a781  leave.s  loc_1A783
0x1a783  ldloc.0
0x1a784  ret
```
