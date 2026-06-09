# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryInitializeSessionAttributesToUpdateFromRequestProperties

- ea: `0x1b0e0`
- end: `0x1b1f2`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryInitializeSessionAttributesToUpdateFromRequestProperties`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19df0`
- `0x1aa80`

## callees

- `0x1b0e0`

## string_xrefs

- `0x1b0f6`: `Initialize session attributes to update: Request object is null.`
- `0x1b11e`: `Initialize session attributes to update: Request object properties are null.`
- `0x1b153`: `Initialize session attributes to update: Request property has no value.`
- `0x1b16b`: `Initialize session attributes to update: Attempting to parse value: '{0}'.`
- `0x1b1d0`: `Failed to parse session attributes to update from request properties. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1b0e0  ldc.i4.0
0x1b0e1  stloc.0
0x1b0e2  ldarg.0
0x1b0e3  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b0e8  brtrue.s loc_1B105
0x1b0ea  ldc.i4   0x139B2C9
0x1b0ef  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b0f4  ldc.i4.s 0xA
0x1b0f6  ldstr    aInitializeSess_5// "Initialize session attributes to update"...
0x1b0fb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1b100  br       loc_1B1BF
0x1b105  ldarg.0
0x1b106  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b10b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1b110  brtrue.s loc_1B12D
0x1b112  ldc.i4   0x139B2CA
0x1b117  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b11c  ldc.i4.s 0xA
0x1b11e  ldstr    aInitializeSess_6// "Initialize session attributes to update"...
0x1b123  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1b128  br       loc_1B1BF
0x1b12d  ldarg.0
0x1b12e  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b133  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1b138  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_SessionAttributesToUpdate()
0x1b13d  stloc.2
0x1b13e  ldloca.s 2
0x1b140  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x1b145  brtrue.s loc_1B15F
0x1b147  ldc.i4   0x139B2CB
0x1b14c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b151  ldc.i4.s 0x64
0x1b153  ldstr    aInitializeSess_7// "Initialize session attributes to update"...
0x1b158  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1b15d  br.s     loc_1B1BF
0x1b15f  ldc.i4   0x139B2CC
0x1b164  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b169  ldc.i4.s 0x32
0x1b16b  ldstr    aInitializeSess_8// "Initialize session attributes to update"...
0x1b170  ldc.i4.1
0x1b171  newarr   [mscorlib]System.Object
0x1b176  stloc.3
0x1b177  ldloc.3
0x1b178  ldc.i4.0
0x1b179  ldarg.0
0x1b17a  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b17f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1b184  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_SessionAttributesToUpdate()
0x1b189  stloc.s  4
0x1b18b  ldloca.s 4
0x1b18d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x1b192  box      [mscorlib]System.Int64
0x1b197  stelem.ref
0x1b198  ldloc.3
0x1b199  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1b19e  ldarg.0
0x1b19f  ldarg.0
0x1b1a0  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b1a5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1b1aa  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_SessionAttributesToUpdate()
0x1b1af  stloc.s  5
0x1b1b1  ldloca.s 5
0x1b1b3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x1b1b8  stfld    valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_SessionAttributesToUpdate
0x1b1bd  ldc.i4.1
0x1b1be  stloc.0
0x1b1bf  leave.s  loc_1B1F0
0x1b1c1  stloc.1
0x1b1c2  ldc.i4.0
0x1b1c3  stloc.0
0x1b1c4  ldc.i4   0x139B2CD
0x1b1c9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b1ce  ldc.i4.s 0xA
0x1b1d0  ldstr    aFailedToParseS_0// "Failed to parse session attributes to u"...
0x1b1d5  ldc.i4.1
0x1b1d6  newarr   [mscorlib]System.Object
0x1b1db  stloc.s  6
0x1b1dd  ldloc.s  6
0x1b1df  ldc.i4.0
0x1b1e0  ldloc.1
0x1b1e1  callvirt instance string [mscorlib]System.Object::ToString()
0x1b1e6  stelem.ref
0x1b1e7  ldloc.s  6
0x1b1e9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1b1ee  leave.s  loc_1B1F0
0x1b1f0  ldloc.0
0x1b1f1  ret
```
