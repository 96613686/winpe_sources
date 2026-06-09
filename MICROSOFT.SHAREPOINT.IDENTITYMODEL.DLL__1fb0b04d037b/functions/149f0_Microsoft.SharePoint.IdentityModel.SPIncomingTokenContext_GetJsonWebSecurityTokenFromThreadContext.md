# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetJsonWebSecurityTokenFromThreadContext

- ea: `0x149f0`
- end: `0x14a5e`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetJsonWebSecurityTokenFromThreadContext`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x149b0`
- `0x14a60`

## callees

- `0x13550`
- `0x149f0`

## string_xrefs

- `0x14a0c`: `There is no SPIncomingTokenContext in the thread context.`
- `0x14a16`: `SPIncomingApplicationContext not set.`
- `0x14a2d`: `Found SPIncomingTokenContext in the thread context.`
- `0x14a52`: `token is null.`

## pseudocode

```c

```

## disassembly

```asm
0x149f0  call     T0x2B000019
0x149f5  stloc.0
0x149f6  ldloc.0
0x149f7  isinst   Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext
0x149fc  stloc.1
0x149fd  ldloc.1
0x149fe  brtrue.s loc_14A21
0x14a00  ldc.i4   0x1001848
0x14a05  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14a0a  ldc.i4.s 0x14
0x14a0c  ldstr    aThereIsNoSpinc// "There is no SPIncomingTokenContext in t"...
0x14a11  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14a16  ldstr    aSpincomingappl// "SPIncomingApplicationContext not set."
0x14a1b  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x14a20  throw
0x14a21  ldc.i4   0x1001849
0x14a26  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14a2b  ldc.i4.s 0x32
0x14a2d  ldstr    aFoundSpincomin// "Found SPIncomingTokenContext in the thr"...
0x14a32  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14a37  ldloc.1
0x14a38  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_SecurityToken()
0x14a3d  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x14a42  stloc.2
0x14a43  ldloc.2
0x14a44  brtrue.s loc_14A5C
0x14a46  ldc.i4   0x100184A
0x14a4b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14a50  ldc.i4.s 0x32
0x14a52  ldstr    aTokenIsNull// "token is null."
0x14a57  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14a5c  ldloc.2
0x14a5d  ret
```
