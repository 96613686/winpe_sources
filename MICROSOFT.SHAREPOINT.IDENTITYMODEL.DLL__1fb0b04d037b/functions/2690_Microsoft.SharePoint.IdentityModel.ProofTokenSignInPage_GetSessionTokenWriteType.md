# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::GetSessionTokenWriteType

- ea: `0x2690`
- end: `0x2779`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::GetSessionTokenWriteType`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2370`

## callees

- `0x2690`
- `0x1bf90`
- `0x2c520`

## string_xrefs

- `0x269f`: `securityToken`
- `0x26c2`: `ProofTokenSignIn: Token is not JWT token`
- `0x271f`: `ProofTokenSignIn: Value of the claim is not a valid SPSessionTokenWriteType. Value: '{0}'.`
- `0x2746`: `ProofTokenSignIn: Value of the claim is not a valid integer. Value: '{0}'.`
- `0x276d`: `ProofTokenSignIn: Token doesn't have psersistent cookie claim.`

## pseudocode

```c

```

## disassembly

```asm
0x2690  ldc.i4   0x175A1C4
0x2695  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x269a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x269f  ldstr    aSecuritytoken// "securityToken"
0x26a4  ldarg.1
0x26a5  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x26aa  ldc.i4.1
0x26ab  stloc.0
0x26ac  ldarg.1
0x26ad  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x26b2  stloc.1
0x26b3  ldloc.1
0x26b4  brtrue.s loc_26D1
0x26b6  ldc.i4   0x35F79C
0x26bb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x26c0  ldc.i4.s 0x32
0x26c2  ldstr    aProoftokensign_26// "ProofTokenSignIn: Token is not JWT toke"...
0x26c7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26cc  br       loc_2777
0x26d1  ldloc.1
0x26d2  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x26d7  ldstr    aUsepersistentc// "usePersistentCookie"
0x26dc  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x26e1  stloc.2
0x26e2  ldloc.2
0x26e3  brfalse.s loc_2761
0x26e5  ldloc.2
0x26e6  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x26eb  stloc.3
0x26ec  ldloc.3
0x26ed  ldloca.s 4
0x26ef  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x26f4  brfalse.s loc_273A
0x26f6  ldtoken  Microsoft.SharePoint.IdentityModel.SPSessionTokenWriteType
0x26fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2700  ldloc.s  4
0x2702  box      [mscorlib]System.Int32
0x2707  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x270c  brfalse.s loc_2713
0x270e  ldloc.s  4
0x2710  stloc.0
0x2711  br.s     loc_2777
0x2713  ldc.i4   0x35F79D
0x2718  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x271d  ldc.i4.s 0x32
0x271f  ldstr    aProoftokensign_27// "ProofTokenSignIn: Value of the claim is"...
0x2724  ldc.i4.1
0x2725  newarr   [mscorlib]System.Object
0x272a  stloc.s  5
0x272c  ldloc.s  5
0x272e  ldc.i4.0
0x272f  ldloc.3
0x2730  stelem.ref
0x2731  ldloc.s  5
0x2733  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2738  br.s     loc_2777
0x273a  ldc.i4   0x35F79E
0x273f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2744  ldc.i4.s 0x32
0x2746  ldstr    aProoftokensign_28// "ProofTokenSignIn: Value of the claim is"...
0x274b  ldc.i4.1
0x274c  newarr   [mscorlib]System.Object
0x2751  stloc.s  6
0x2753  ldloc.s  6
0x2755  ldc.i4.0
0x2756  ldloc.3
0x2757  stelem.ref
0x2758  ldloc.s  6
0x275a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x275f  br.s     loc_2777
0x2761  ldc.i4   0x35F79F
0x2766  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x276b  ldc.i4.s 0x32
0x276d  ldstr    aProoftokensign_29// "ProofTokenSignIn: Token doesn't have ps"...
0x2772  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2777  ldloc.0
0x2778  ret
```
