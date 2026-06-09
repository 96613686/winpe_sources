# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SessionRevocationTokenValidFromTime

- ea: `0x199e0`
- end: `0x19b41`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SessionRevocationTokenValidFromTime`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ef60`

## callees

- `0x199e0`

## string_xrefs

- `0x19a0b`: `SessionRevocationTokenValidFromTime: Using token issued at time: '{0}.`
- `0x19a5c`: `SessionRevocationTokenValidFromTime: Using token not valid before time: '{0}.`
- `0x19aad`: `SessionRevocationTokenValidFromTime: Using token valid from time: '{0}.`
- `0x19afb`: `SessionRevocationTokenValidFromTime: Using authentication instant time: '{0}.`
- `0x19b35`: `SessionRevocationTokenValidFromTime: Could not find any valid value.`

## pseudocode

```c

```

## disassembly

```asm
0x199e0  ldarg.0
0x199e1  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenIssuanceTimeUtc
0x199e6  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x199eb  brfalse.s loc_19A31
0x199ed  ldloca.s 0
0x199ef  ldarg.0
0x199f0  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenIssuanceTimeUtc
0x199f5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x199fa  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x199ff  ldc.i4   0x1405322
0x19a04  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19a09  ldc.i4.s 0x32
0x19a0b  ldstr    aSessionrevocat// "SessionRevocationTokenValidFromTime: Us"...
0x19a10  ldc.i4.1
0x19a11  newarr   [mscorlib]System.Object
0x19a16  stloc.1
0x19a17  ldloc.1
0x19a18  ldc.i4.0
0x19a19  ldloca.s 0
0x19a1b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19a20  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.DateTime)
0x19a25  stelem.ref
0x19a26  ldloc.1
0x19a27  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19a2c  br       loc_19B3F
0x19a31  ldarg.0
0x19a32  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenNotBeforeTimeUtc
0x19a37  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x19a3c  brfalse.s loc_19A82
0x19a3e  ldloca.s 0
0x19a40  ldarg.0
0x19a41  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenNotBeforeTimeUtc
0x19a46  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19a4b  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x19a50  ldc.i4   0x1405323
0x19a55  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19a5a  ldc.i4.s 0x14
0x19a5c  ldstr    aSessionrevocat_0// "SessionRevocationTokenValidFromTime: Us"...
0x19a61  ldc.i4.1
0x19a62  newarr   [mscorlib]System.Object
0x19a67  stloc.2
0x19a68  ldloc.2
0x19a69  ldc.i4.0
0x19a6a  ldloca.s 0
0x19a6c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19a71  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.DateTime)
0x19a76  stelem.ref
0x19a77  ldloc.2
0x19a78  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19a7d  br       loc_19B3F
0x19a82  ldarg.0
0x19a83  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenValidFromUtc
0x19a88  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x19a8d  brfalse.s loc_19AD0
0x19a8f  ldloca.s 0
0x19a91  ldarg.0
0x19a92  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenValidFromUtc
0x19a97  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19a9c  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x19aa1  ldc.i4   0x1405340
0x19aa6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19aab  ldc.i4.s 0x14
0x19aad  ldstr    aSessionrevocat_1// "SessionRevocationTokenValidFromTime: Us"...
0x19ab2  ldc.i4.1
0x19ab3  newarr   [mscorlib]System.Object
0x19ab8  stloc.3
0x19ab9  ldloc.3
0x19aba  ldc.i4.0
0x19abb  ldloca.s 0
0x19abd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19ac2  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.DateTime)
0x19ac7  stelem.ref
0x19ac8  ldloc.3
0x19ac9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19ace  br.s     loc_19B3F
0x19ad0  ldarg.0
0x19ad1  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_authenticationInstantUtc
0x19ad6  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x19adb  brfalse.s loc_19B21
0x19add  ldloca.s 0
0x19adf  ldarg.0
0x19ae0  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_authenticationInstantUtc
0x19ae5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19aea  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x19aef  ldc.i4   0x1405341
0x19af4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19af9  ldc.i4.s 0xF
0x19afb  ldstr    aSessionrevocat_2// "SessionRevocationTokenValidFromTime: Us"...
0x19b00  ldc.i4.1
0x19b01  newarr   [mscorlib]System.Object
0x19b06  stloc.s  4
0x19b08  ldloc.s  4
0x19b0a  ldc.i4.0
0x19b0b  ldloca.s 0
0x19b0d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19b12  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.DateTime)
0x19b17  stelem.ref
0x19b18  ldloc.s  4
0x19b1a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19b1f  br.s     loc_19B3F
0x19b21  ldloca.s 0
0x19b23  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x19b29  ldc.i4   0x1405342
0x19b2e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19b33  ldc.i4.s 0xF
0x19b35  ldstr    aSessionrevocat_3// "SessionRevocationTokenValidFromTime: Co"...
0x19b3a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x19b3f  ldloc.0
0x19b40  ret
```
