# System.Web.Security.PassportIdentity::.ctor

- ea: `0x11d160`
- end: `0x11d417`
- name: `System.Web.Security.PassportIdentity::.ctor`
- size: `695`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x11ce00`
- `0x11dec0`

## callees

- `0x15e20`
- `0x16330`
- `0x16350`
- `0x17c20`
- `0x184e0`
- `0x1b710`
- `0x1ba30`
- `0x1c020`
- `0x1c5e0`
- `0x1c860`
- `0x1ca30`
- `0x1fe20`
- `0x26450`
- `0x30770`
- `0x30780`
- `0x30800`
- `0x34fa0`
- `0x11d160`
- `0x11d420`
- `0x11d4b0`
- `0x11d640`

## string_xrefs

- `0x11d35c`: `SERVER_PROTOCOL`
- `0x11d2af`: `Could_not_create_passport_identity`
- `0x11d3d0`: `Could_not_create_passport_identity`

## pseudocode

```c

```

## disassembly

```asm
0x11d160  ldarg.0
0x11d161  call     instance void [mscorlib]System.Object::.ctor()
0x11d166  call     class System.Web.HttpContext System.Web.HttpContext::get_Current()
0x11d16b  stloc.0
0x11d16c  ldsfld   int32 System.Web.Security.PassportIdentity::_iPassportVer
0x11d171  brtrue.s loc_11D17D
0x11d173  call     int32 System.Web.UnsafeNativeMethods::PassportVersion()
0x11d178  stsfld   int32 System.Web.Security.PassportIdentity::_iPassportVer
0x11d17d  ldsfld   int32 System.Web.Security.PassportIdentity::_iPassportVer
0x11d182  ldc.i4.3
0x11d183  bge      loc_11D31D
0x11d188  ldloc.0
0x11d189  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d18e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x11d193  ldstr    aT_3// "t"
0x11d198  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11d19d  stloc.1
0x11d19e  ldloc.0
0x11d19f  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d1a4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x11d1a9  ldstr    aP// "p"
0x11d1ae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11d1b3  stloc.2
0x11d1b4  ldloc.0
0x11d1b5  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d1ba  callvirt instance class System.Web.HttpCookieCollection System.Web.HttpRequest::get_Cookies()
0x11d1bf  ldstr    aMspauth// "MSPAuth"
0x11d1c4  callvirt instance class System.Web.HttpCookie System.Web.HttpCookieCollection::get_Item(string name)
0x11d1c9  stloc.3
0x11d1ca  ldloc.0
0x11d1cb  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d1d0  callvirt instance class System.Web.HttpCookieCollection System.Web.HttpRequest::get_Cookies()
0x11d1d5  ldstr    aMspprof// "MSPProf"
0x11d1da  callvirt instance class System.Web.HttpCookie System.Web.HttpCookieCollection::get_Item(string name)
0x11d1df  stloc.s  4
0x11d1e1  ldloc.0
0x11d1e2  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d1e7  callvirt instance class System.Web.HttpCookieCollection System.Web.HttpRequest::get_Cookies()
0x11d1ec  ldstr    aMspprofc// "MSPProfC"
0x11d1f1  callvirt instance class System.Web.HttpCookie System.Web.HttpCookieCollection::get_Item(string name)
0x11d1f6  stloc.s  5
0x11d1f8  ldloc.3
0x11d1f9  brfalse.s loc_11D203
0x11d1fb  ldloc.3
0x11d1fc  callvirt instance string System.Web.HttpCookie::get_Value()
0x11d201  brtrue.s loc_11D20A
0x11d203  ldsfld   string [mscorlib]System.String::Empty
0x11d208  br.s     loc_11D210
0x11d20a  ldloc.3
0x11d20b  callvirt instance string System.Web.HttpCookie::get_Value()
0x11d210  stloc.s  6
0x11d212  ldloc.s  4
0x11d214  brfalse.s loc_11D21F
0x11d216  ldloc.s  4
0x11d218  callvirt instance string System.Web.HttpCookie::get_Value()
0x11d21d  brtrue.s loc_11D226
0x11d21f  ldsfld   string [mscorlib]System.String::Empty
0x11d224  br.s     loc_11D22D
0x11d226  ldloc.s  4
0x11d228  callvirt instance string System.Web.HttpCookie::get_Value()
0x11d22d  stloc.s  7
0x11d22f  ldloc.s  5
0x11d231  brfalse.s loc_11D23C
0x11d233  ldloc.s  5
0x11d235  callvirt instance string System.Web.HttpCookie::get_Value()
0x11d23a  brtrue.s loc_11D243
0x11d23c  ldsfld   string [mscorlib]System.String::Empty
0x11d241  br.s     loc_11D24A
0x11d243  ldloc.s  5
0x11d245  callvirt instance string System.Web.HttpCookie::get_Value()
0x11d24a  stloc.s  8
0x11d24c  ldc.i4   0x404
0x11d251  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x11d256  stloc.s  9
0x11d258  ldc.i4   0x404
0x11d25d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x11d262  stloc.s  0xA
0x11d264  ldloc.s  6
0x11d266  call     string System.Web.HttpUtility::UrlDecode(string str)
0x11d26b  stloc.s  6
0x11d26d  ldloc.s  7
0x11d26f  call     string System.Web.HttpUtility::UrlDecode(string str)
0x11d274  stloc.s  7
0x11d276  ldloc.s  8
0x11d278  call     string System.Web.HttpUtility::UrlDecode(string str)
0x11d27d  stloc.s  8
0x11d27f  ldloc.1
0x11d280  ldloc.2
0x11d281  ldloc.s  6
0x11d283  ldloc.s  7
0x11d285  ldloc.s  8
0x11d287  ldloc.s  9
0x11d289  ldloc.s  0xA
0x11d28b  ldc.i4   0x400
0x11d290  ldarg.0
0x11d291  ldflda   native int System.Web.Security.PassportIdentity::_iPassport
0x11d296  call     int32 System.Web.UnsafeNativeMethods::PassportCreate(string szQueryStrT, string szQueryStrP, string szAuthCookie, string szProfCookie, string szProfCCookie, class [mscorlib]System.Text.StringBuilder szAuthCookieRet, class [mscorlib]System.Text.StringBuilder szProfCookieRet, int32 iRetBufSize, native int& passportManager)
0x11d29b  stloc.s  0xB
0x11d29d  ldarg.0
0x11d29e  ldfld    native int System.Web.Security.PassportIdentity::_iPassport
0x11d2a3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x11d2a8  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x11d2ad  brfalse.s loc_11D2C1
0x11d2af  ldstr    aCouldNotCreate_2// "Could_not_create_passport_identity"
0x11d2b4  call     string System.Web.SR::GetString(string name)
0x11d2b9  ldloc.s  0xB
0x11d2bb  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x11d2c0  throw
0x11d2c1  ldloc.s  9
0x11d2c3  callvirt instance string [mscorlib]System.Object::ToString()
0x11d2c8  call     string System.Web.Security.PassportIdentity::UrlEncodeCookie(string strIn)
0x11d2cd  stloc.s  0xC
0x11d2cf  ldloc.s  0xA
0x11d2d1  callvirt instance string [mscorlib]System.Object::ToString()
0x11d2d6  call     string System.Web.Security.PassportIdentity::UrlEncodeCookie(string strIn)
0x11d2db  stloc.s  0xD
0x11d2dd  ldloc.s  0xC
0x11d2df  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11d2e4  ldc.i4.1
0x11d2e5  ble.s    loc_11D2F9
0x11d2e7  ldloc.0
0x11d2e8  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11d2ed  ldstr    aSetCookie// "Set-Cookie"
0x11d2f2  ldloc.s  0xC
0x11d2f4  callvirt instance void System.Web.HttpResponse::AppendHeader(string name, string value)
0x11d2f9  ldloc.s  0xD
0x11d2fb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11d300  ldc.i4.1
0x11d301  ble      loc_11D3F4
0x11d306  ldloc.0
0x11d307  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11d30c  ldstr    aSetCookie// "Set-Cookie"
0x11d311  ldloc.s  0xD
0x11d313  callvirt instance void System.Web.HttpResponse::AppendHeader(string name, string value)
0x11d318  br       loc_11D3F4
0x11d31d  ldc.i4.6
0x11d31e  newarr   [mscorlib]System.String
0x11d323  dup
0x11d324  ldc.i4.0
0x11d325  ldloc.0
0x11d326  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d32b  callvirt instance string System.Web.HttpRequest::get_HttpMethod()
0x11d330  stelem.ref
0x11d331  dup
0x11d332  ldc.i4.1
0x11d333  ldstr    asc_1B0CBE// " "
0x11d338  stelem.ref
0x11d339  dup
0x11d33a  ldc.i4.2
0x11d33b  ldloc.0
0x11d33c  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d341  callvirt instance string System.Web.HttpRequest::get_RawUrl()
0x11d346  stelem.ref
0x11d347  dup
0x11d348  ldc.i4.3
0x11d349  ldstr    asc_1B0CBE// " "
0x11d34e  stelem.ref
0x11d34f  dup
0x11d350  ldc.i4.4
0x11d351  ldloc.0
0x11d352  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d357  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_ServerVariables()
0x11d35c  ldstr    aServerProtocol// "SERVER_PROTOCOL"
0x11d361  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11d366  stelem.ref
0x11d367  dup
0x11d368  ldc.i4.5
0x11d369  ldstr    asc_1B2016// "\r\n"
0x11d36e  stelem.ref
0x11d36f  call     string [mscorlib]System.String::Concat(string[])
0x11d374  stloc.s  0xE
0x11d376  ldc.i4   0xFFC
0x11d37b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x11d380  stloc.s  0xF
0x11d382  ldloc.s  0xE
0x11d384  ldloc.0
0x11d385  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d38a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_ServerVariables()
0x11d38f  ldstr    aAllRaw// "ALL_RAW"
0x11d394  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11d399  ldloc.0
0x11d39a  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11d39f  callvirt instance bool System.Web.HttpRequest::get_IsSecureConnection()
0x11d3a4  brtrue.s loc_11D3A9
0x11d3a6  ldc.i4.0
0x11d3a7  br.s     loc_11D3AA
0x11d3a9  ldc.i4.1
0x11d3aa  ldloc.s  0xF
0x11d3ac  ldc.i4   0xFFA
0x11d3b1  ldarg.0
0x11d3b2  ldflda   native int System.Web.Security.PassportIdentity::_iPassport
0x11d3b7  call     int32 System.Web.UnsafeNativeMethods::PassportCreateHttpRaw(string szRequestLine, string szHeaders, int32 fSecure, class [mscorlib]System.Text.StringBuilder szBufOut, int32 dwRetBufSize, native int& passportManager)
0x11d3bc  stloc.s  0x10
0x11d3be  ldarg.0
0x11d3bf  ldfld    native int System.Web.Security.PassportIdentity::_iPassport
0x11d3c4  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x11d3c9  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x11d3ce  brfalse.s loc_11D3E2
0x11d3d0  ldstr    aCouldNotCreate_2// "Could_not_create_passport_identity"
0x11d3d5  call     string System.Web.SR::GetString(string name)
0x11d3da  ldloc.s  0x10
0x11d3dc  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x11d3e1  throw
0x11d3e2  ldloc.s  0xF
0x11d3e4  callvirt instance string [mscorlib]System.Object::ToString()
0x11d3e9  stloc.s  0x11
0x11d3eb  ldarg.0
0x11d3ec  ldloc.0
0x11d3ed  ldloc.s  0x11
0x11d3ef  call     instance void System.Web.Security.PassportIdentity::SetHeaders(class System.Web.HttpContext context, string strResponseHeaders)
0x11d3f4  ldarg.0
0x11d3f5  ldarg.0
0x11d3f6  ldc.i4.m1
0x11d3f7  ldc.i4.m1
0x11d3f8  ldc.i4.m1
0x11d3f9  call     instance bool System.Web.Security.PassportIdentity::GetIsAuthenticated(int32 iTimeWindow, int32 iForceLogin, int32 iCheckSecure)
0x11d3fe  stfld    bool System.Web.Security.PassportIdentity::_Authenticated
0x11d403  ldarg.0
0x11d404  ldfld    bool System.Web.Security.PassportIdentity::_Authenticated
0x11d409  brtrue.s loc_11D416
0x11d40b  ldarg.0
0x11d40c  ldsfld   string [mscorlib]System.String::Empty
0x11d411  stfld    string System.Web.Security.PassportIdentity::_Name
0x11d416  ret
```
