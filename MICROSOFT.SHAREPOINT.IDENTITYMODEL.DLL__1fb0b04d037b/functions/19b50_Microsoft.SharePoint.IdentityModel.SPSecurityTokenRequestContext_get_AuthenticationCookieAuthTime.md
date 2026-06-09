# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_AuthenticationCookieAuthTime

- ea: `0x19b50`
- end: `0x19cb1`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_AuthenticationCookieAuthTime`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1b340`

## callees

- `0x19b50`

## string_xrefs

- `0x19bcc`: `AuthenticationCookieAuthTime: Using token issued at time: '{0}.`
- `0x19c1d`: `AuthenticationCookieAuthTime: Using token not valid before time: '{0}.`
- `0x19c6b`: `AuthenticationCookieAuthTime: Using token valid from time: '{0}.`

## pseudocode

```c

```

## disassembly

```asm
0x19b50  ldarg.0
0x19b51  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_authenticationInstantUtc
0x19b56  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x19b5b  brfalse.s loc_19BA1
0x19b5d  ldloca.s 0
0x19b5f  ldarg.0
0x19b60  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_authenticationInstantUtc
0x19b65  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19b6a  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x19b6f  ldc.i4   0x1405343
0x19b74  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19b79  ldc.i4.s 0x32
0x19b7b  ldstr    aAuthentication_1// "AuthenticationCookieAuthTime: Using aut"...
0x19b80  ldc.i4.1
0x19b81  newarr   [mscorlib]System.Object
0x19b86  stloc.1
0x19b87  ldloc.1
0x19b88  ldc.i4.0
0x19b89  ldloca.s 0
0x19b8b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19b90  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.DateTime)
0x19b95  stelem.ref
0x19b96  ldloc.1
0x19b97  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19b9c  br       loc_19CAF
0x19ba1  ldarg.0
0x19ba2  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenIssuanceTimeUtc
0x19ba7  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x19bac  brfalse.s loc_19BF2
0x19bae  ldloca.s 0
0x19bb0  ldarg.0
0x19bb1  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenIssuanceTimeUtc
0x19bb6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19bbb  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x19bc0  ldc.i4   0x1405344
0x19bc5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19bca  ldc.i4.s 0x14
0x19bcc  ldstr    aAuthentication_2// "AuthenticationCookieAuthTime: Using tok"...
0x19bd1  ldc.i4.1
0x19bd2  newarr   [mscorlib]System.Object
0x19bd7  stloc.2
0x19bd8  ldloc.2
0x19bd9  ldc.i4.0
0x19bda  ldloca.s 0
0x19bdc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19be1  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.DateTime)
0x19be6  stelem.ref
0x19be7  ldloc.2
0x19be8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19bed  br       loc_19CAF
0x19bf2  ldarg.0
0x19bf3  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenNotBeforeTimeUtc
0x19bf8  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x19bfd  brfalse.s loc_19C40
0x19bff  ldloca.s 0
0x19c01  ldarg.0
0x19c02  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenNotBeforeTimeUtc
0x19c07  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19c0c  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x19c11  ldc.i4   0x1405345
0x19c16  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19c1b  ldc.i4.s 0x14
0x19c1d  ldstr    aAuthentication_3// "AuthenticationCookieAuthTime: Using tok"...
0x19c22  ldc.i4.1
0x19c23  newarr   [mscorlib]System.Object
0x19c28  stloc.3
0x19c29  ldloc.3
0x19c2a  ldc.i4.0
0x19c2b  ldloca.s 0
0x19c2d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19c32  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.DateTime)
0x19c37  stelem.ref
0x19c38  ldloc.3
0x19c39  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19c3e  br.s     loc_19CAF
0x19c40  ldarg.0
0x19c41  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenValidFromUtc
0x19c46  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x19c4b  brfalse.s loc_19C91
0x19c4d  ldloca.s 0
0x19c4f  ldarg.0
0x19c50  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenValidFromUtc
0x19c55  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19c5a  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x19c5f  ldc.i4   0x1405346
0x19c64  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19c69  ldc.i4.s 0x14
0x19c6b  ldstr    aAuthentication_4// "AuthenticationCookieAuthTime: Using tok"...
0x19c70  ldc.i4.1
0x19c71  newarr   [mscorlib]System.Object
0x19c76  stloc.s  4
0x19c78  ldloc.s  4
0x19c7a  ldc.i4.0
0x19c7b  ldloca.s 0
0x19c7d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x19c82  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.DateTime)
0x19c87  stelem.ref
0x19c88  ldloc.s  4
0x19c8a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x19c8f  br.s     loc_19CAF
0x19c91  ldloca.s 0
0x19c93  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x19c99  ldc.i4   0x1405347
0x19c9e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19ca3  ldc.i4.s 0x14
0x19ca5  ldstr    aAuthentication_5// "AuthenticationCookieAuthTime: Could not"...
0x19caa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x19caf  ldloc.0
0x19cb0  ret
```
