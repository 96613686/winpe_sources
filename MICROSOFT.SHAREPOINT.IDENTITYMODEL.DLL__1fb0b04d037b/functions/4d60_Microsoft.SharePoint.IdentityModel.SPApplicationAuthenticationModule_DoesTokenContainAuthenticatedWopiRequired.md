# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::DoesTokenContainAuthenticatedWopiRequiredScopes

- ea: `0x4d60`
- end: `0x4e81`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::DoesTokenContainAuthenticatedWopiRequiredScopes`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x49d0`

## callees

- `0x4d60`
- `0x28920`

## string_xrefs

- `0x4d83`: `SPApplicationAuthenticationModule: Scope claim missing in auth token`
- `0x4dca`: `SPApplicationAuthenticationModule: Validating scope claim of read-write authenticated WOPI request`
- `0x4dd5`: `Files.ReadWrite.Selected`
- `0x4e03`: `Files.ReadWrite.Selected`
- `0x4e3a`: `Files.ReadWrite.Selected`
- `0x4e70`: `Files.ReadWrite.Selected`
- `0x4df5`: `SPApplicationAuthenticationModule: Scope claim doesn't contain '{0}' in auth token`
- `0x4e1d`: `SPApplicationAuthenticationModule: Validating scope claim of read-only authenticated WOPI request`
- `0x4e28`: `Files.Read.Selected`
- `0x4e67`: `Files.Read.Selected`
- `0x4e57`: `SPApplicationAuthenticationModule: Scope claim doesn't contain '{0}' or '{1}' in auth token`

## pseudocode

```c

```

## disassembly

```asm
0x4d60  ldarg.1
0x4d61  ldstr    aScp// "scp"
0x4d66  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x4d6b  stloc.0
0x4d6c  ldloc.0
0x4d6d  brfalse.s loc_4D77
0x4d6f  ldloc.0
0x4d70  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4d75  brtrue.s loc_4D8F
0x4d77  ldc.i4   0x78F558
0x4d7c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4d81  ldc.i4.s 0x14
0x4d83  ldstr    aSpapplicationa_64// "SPApplicationAuthenticationModule: Scop"...
0x4d88  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4d8d  ldc.i4.0
0x4d8e  ret
0x4d8f  ldloc.0
0x4d90  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4d95  callvirt instance string [mscorlib]System.String::Trim()
0x4d9a  ldc.i4.1
0x4d9b  newarr   [mscorlib]System.String
0x4da0  stloc.2
0x4da1  ldloc.2
0x4da2  ldc.i4.0
0x4da3  ldstr    asc_37508// " "
0x4da8  stelem.ref
0x4da9  ldloc.2
0x4daa  ldc.i4.1
0x4dab  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x4db0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4db5  stloc.1
0x4db6  ldarg.2
0x4db7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenContext::get_HasEditLicense()
0x4dbc  brfalse.s loc_4E11
0x4dbe  ldc.i4   0x78F559
0x4dc3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4dc8  ldc.i4.s 0x32
0x4dca  ldstr    aSpapplicationa_65// "SPApplicationAuthenticationModule: Vali"...
0x4dcf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4dd4  ldloc.1
0x4dd5  ldstr    aFilesReadwrite// "Files.ReadWrite.Selected"
0x4dda  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x4ddf  call     T0x2B00000C
0x4de4  brtrue   loc_4E7F
0x4de9  ldc.i4   0x78F55A
0x4dee  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4df3  ldc.i4.s 0x14
0x4df5  ldstr    aSpapplicationa_66// "SPApplicationAuthenticationModule: Scop"...
0x4dfa  ldc.i4.1
0x4dfb  newarr   [mscorlib]System.Object
0x4e00  stloc.3
0x4e01  ldloc.3
0x4e02  ldc.i4.0
0x4e03  ldstr    aFilesReadwrite// "Files.ReadWrite.Selected"
0x4e08  stelem.ref
0x4e09  ldloc.3
0x4e0a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x4e0f  ldc.i4.0
0x4e10  ret
0x4e11  ldc.i4   0x78F55B
0x4e16  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4e1b  ldc.i4.s 0x32
0x4e1d  ldstr    aSpapplicationa_67// "SPApplicationAuthenticationModule: Vali"...
0x4e22  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4e27  ldloc.1
0x4e28  ldstr    aFilesReadSelec// "Files.Read.Selected"
0x4e2d  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x4e32  call     T0x2B00000C
0x4e37  brtrue.s loc_4E7F
0x4e39  ldloc.1
0x4e3a  ldstr    aFilesReadwrite// "Files.ReadWrite.Selected"
0x4e3f  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x4e44  call     T0x2B00000C
0x4e49  brtrue.s loc_4E7F
0x4e4b  ldc.i4   0x78F55C
0x4e50  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4e55  ldc.i4.s 0x14
0x4e57  ldstr    aSpapplicationa_68// "SPApplicationAuthenticationModule: Scop"...
0x4e5c  ldc.i4.2
0x4e5d  newarr   [mscorlib]System.Object
0x4e62  stloc.s  4
0x4e64  ldloc.s  4
0x4e66  ldc.i4.0
0x4e67  ldstr    aFilesReadSelec// "Files.Read.Selected"
0x4e6c  stelem.ref
0x4e6d  ldloc.s  4
0x4e6f  ldc.i4.1
0x4e70  ldstr    aFilesReadwrite// "Files.ReadWrite.Selected"
0x4e75  stelem.ref
0x4e76  ldloc.s  4
0x4e78  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x4e7d  ldc.i4.0
0x4e7e  ret
0x4e7f  ldc.i4.1
0x4e80  ret
```
