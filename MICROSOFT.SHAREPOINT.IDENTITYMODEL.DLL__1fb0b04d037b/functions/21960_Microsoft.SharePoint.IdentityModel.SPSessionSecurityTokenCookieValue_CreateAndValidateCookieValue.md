# Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::CreateAndValidateCookieValue

- ea: `0x21960`
- end: `0x21a71`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::CreateAndValidateCookieValue`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xd6b0`

## callees

- `0x1b00`
- `0x1b30`
- `0x1b40`
- `0x1b60`
- `0x21960`
- `0x21a80`
- `0x28160`

## string_xrefs

- `0x21979`: `CreateAndValidateCookieValue: Empty cookie string received.`
- `0x219a0`: `CreateAndValidateCookieValue: Failed to get cookie handler.`
- `0x219c5`: `CreateAndValidateCookieValue: Failed to initialize cookie using the original cookie string. Length: '{0}'.`
- `0x219ff`: `CreateAndValidateCookieValue: The cookie's value has been tampered with: <name>{0}</name>.`
- `0x21a31`: `CreateAndValidateCookieValue: Cookie value has expired: '{0}'.`
- `0x21a63`: `CreateAndValidateCookieValue: Success.`

## pseudocode

```c

```

## disassembly

```asm
0x21960  ldc.i4.0
0x21961  stloc.0
0x21962  ldarg.1
0x21963  ldnull
0x21964  stind.ref
0x21965  ldarg.0
0x21966  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2196b  brfalse.s loc_21988
0x2196d  ldc.i4   0x11D8814
0x21972  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21977  ldc.i4.s 0xA
0x21979  ldstr    aCreateandvalid// "CreateAndValidateCookieValue: Empty coo"...
0x2197e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21983  br       loc_21A6F
0x21988  ldarg.1
0x21989  call     class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetCookieValueHandler()
0x2198e  dup
0x2198f  stloc.1
0x21990  stind.ref
0x21991  ldloc.1
0x21992  brtrue.s loc_219AF
0x21994  ldc.i4   0x11D8815
0x21999  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2199e  ldc.i4.s 0xA
0x219a0  ldstr    aCreateandvalid_0// "CreateAndValidateCookieValue: Failed to"...
0x219a5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x219aa  br       loc_21A6F
0x219af  ldarg.1
0x219b0  ldind.ref
0x219b1  ldarg.0
0x219b2  callvirt instance bool Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue::Initialize(string cookieValue)
0x219b7  brtrue.s loc_219EA
0x219b9  ldc.i4   0x11D8816
0x219be  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x219c3  ldc.i4.s 0x14
0x219c5  ldstr    aCreateandvalid_1// "CreateAndValidateCookieValue: Failed to"...
0x219ca  ldc.i4.1
0x219cb  newarr   [mscorlib]System.Object
0x219d0  stloc.2
0x219d1  ldloc.2
0x219d2  ldc.i4.0
0x219d3  ldarg.0
0x219d4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x219d9  box      [mscorlib]System.Int32
0x219de  stelem.ref
0x219df  ldloc.2
0x219e0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x219e5  br       loc_21A6F
0x219ea  ldarg.1
0x219eb  ldind.ref
0x219ec  callvirt instance bool Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue::get_IsValid()
0x219f1  brtrue.s loc_21A1C
0x219f3  ldc.i4   0x11D8817
0x219f8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x219fd  ldc.i4.s 0xA
0x219ff  ldstr    aCreateandvalid_2// "CreateAndValidateCookieValue: The cooki"...
0x21a04  ldc.i4.1
0x21a05  newarr   [mscorlib]System.Object
0x21a0a  stloc.3
0x21a0b  ldloc.3
0x21a0c  ldc.i4.0
0x21a0d  ldarg.0
0x21a0e  call     string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::GetCookieStringForLogging(string cookieValue)
0x21a13  stelem.ref
0x21a14  ldloc.3
0x21a15  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x21a1a  br.s     loc_21A6F
0x21a1c  ldarg.1
0x21a1d  ldind.ref
0x21a1e  callvirt instance bool Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue::get_IsExpired()
0x21a23  brfalse.s loc_21A57
0x21a25  ldc.i4   0x11D8818
0x21a2a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21a2f  ldc.i4.s 0x32
0x21a31  ldstr    aCreateandvalid_3// "CreateAndValidateCookieValue: Cookie va"...
0x21a36  ldc.i4.1
0x21a37  newarr   [mscorlib]System.Object
0x21a3c  stloc.s  4
0x21a3e  ldloc.s  4
0x21a40  ldc.i4.0
0x21a41  ldarg.1
0x21a42  ldind.ref
0x21a43  callvirt instance int64 Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue::get_ExpireDateUtcFileTime()
0x21a48  box      [mscorlib]System.Int64
0x21a4d  stelem.ref
0x21a4e  ldloc.s  4
0x21a50  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x21a55  br.s     loc_21A6F
0x21a57  ldc.i4   0x11D8819
0x21a5c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21a61  ldc.i4.s 0x64
0x21a63  ldstr    aCreateandvalid_4// "CreateAndValidateCookieValue: Success."
0x21a68  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21a6d  ldc.i4.1
0x21a6e  stloc.0
0x21a6f  ldloc.0
0x21a70  ret
```
