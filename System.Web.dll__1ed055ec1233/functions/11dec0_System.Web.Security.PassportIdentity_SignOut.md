# System.Web.Security.PassportIdentity::SignOut

- ea: `0x11dec0`
- end: `0x11e139`
- name: `System.Web.Security.PassportIdentity::SignOut`
- size: `633`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x14340`
- `0x15e20`
- `0x16330`
- `0x16350`
- `0x167a0`
- `0x17a20`
- `0x17b50`
- `0x17bd0`
- `0x17c00`
- `0x183a0`
- `0x1c5e0`
- `0x1eb80`
- `0x1f980`
- `0x1fbf0`
- `0x1fe20`
- `0x1ffb0`
- `0x20240`
- `0x20980`
- `0x20f10`
- `0x11d160`
- `0x11de20`
- `0x11dec0`

## string_xrefs

- `0x11e0df`: `no-cache`
- `0x11df2c`: `TicketPath`
- `0x11df34`: `TicketPath`
- `0x11df4c`: `TicketPath`
- `0x11df3c`: `ProfilePath`
- `0x11df44`: `SecurePath`

## pseudocode

```c

```

## disassembly

```asm
0x11dec0  call     class System.Web.HttpContext System.Web.HttpContext::get_Current()
0x11dec5  stloc.0
0x11dec6  ldc.i4.5
0x11dec7  newarr   [mscorlib]System.String
0x11decc  dup
0x11decd  ldc.i4.0
0x11dece  ldstr    aMspauth// "MSPAuth"
0x11ded3  stelem.ref
0x11ded4  dup
0x11ded5  ldc.i4.1
0x11ded6  ldstr    aMspprof// "MSPProf"
0x11dedb  stelem.ref
0x11dedc  dup
0x11dedd  ldc.i4.2
0x11dede  ldstr    aMspconsent// "MSPConsent"
0x11dee3  stelem.ref
0x11dee4  dup
0x11dee5  ldc.i4.3
0x11dee6  ldstr    aMspsecauth// "MSPSecAuth"
0x11deeb  stelem.ref
0x11deec  dup
0x11deed  ldc.i4.4
0x11deee  ldstr    aMspprofc// "MSPProfC"
0x11def3  stelem.ref
0x11def4  stloc.1
0x11def5  ldc.i4.5
0x11def6  newarr   [mscorlib]System.String
0x11defb  dup
0x11defc  ldc.i4.0
0x11defd  ldstr    aTicketdomain// "TicketDomain"
0x11df02  stelem.ref
0x11df03  dup
0x11df04  ldc.i4.1
0x11df05  ldstr    aTicketdomain// "TicketDomain"
0x11df0a  stelem.ref
0x11df0b  dup
0x11df0c  ldc.i4.2
0x11df0d  ldstr    aProfiledomain// "ProfileDomain"
0x11df12  stelem.ref
0x11df13  dup
0x11df14  ldc.i4.3
0x11df15  ldstr    aSecuredomain// "SecureDomain"
0x11df1a  stelem.ref
0x11df1b  dup
0x11df1c  ldc.i4.4
0x11df1d  ldstr    aTicketdomain// "TicketDomain"
0x11df22  stelem.ref
0x11df23  stloc.2
0x11df24  ldc.i4.5
0x11df25  newarr   [mscorlib]System.String
0x11df2a  dup
0x11df2b  ldc.i4.0
0x11df2c  ldstr    aTicketpath// "TicketPath"
0x11df31  stelem.ref
0x11df32  dup
0x11df33  ldc.i4.1
0x11df34  ldstr    aTicketpath// "TicketPath"
0x11df39  stelem.ref
0x11df3a  dup
0x11df3b  ldc.i4.2
0x11df3c  ldstr    aProfilepath// "ProfilePath"
0x11df41  stelem.ref
0x11df42  dup
0x11df43  ldc.i4.3
0x11df44  ldstr    aSecurepath// "SecurePath"
0x11df49  stelem.ref
0x11df4a  dup
0x11df4b  ldc.i4.4
0x11df4c  ldstr    aTicketpath// "TicketPath"
0x11df51  stelem.ref
0x11df52  stloc.3
0x11df53  ldc.i4.5
0x11df54  newarr   [mscorlib]System.String
0x11df59  stloc.s  4
0x11df5b  ldc.i4.5
0x11df5c  newarr   [mscorlib]System.String
0x11df61  stloc.s  5
0x11df63  ldnull
0x11df64  stloc.s  6
0x11df66  ldc.i4.0
0x11df67  stloc.s  7
0x11df69  ldloc.0
0x11df6a  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11df6f  callvirt instance void System.Web.HttpResponse::ClearHeaders()
0x11df74  ldloc.0
0x11df75  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal System.Web.HttpContext::get_User()
0x11df7a  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x11df7f  isinst   System.Web.Security.PassportIdentity
0x11df84  brfalse.s loc_11DF9A
0x11df86  ldloc.0
0x11df87  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal System.Web.HttpContext::get_User()
0x11df8c  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x11df91  castclass System.Web.Security.PassportIdentity
0x11df96  stloc.s  6
0x11df98  br.s     loc_11DFA1
0x11df9a  newobj   instance void System.Web.Security.PassportIdentity::.ctor()
0x11df9f  stloc.s  6
0x11dfa1  ldloc.s  6
0x11dfa3  brfalse.s loc_11E019
0x11dfa5  ldsfld   int32 System.Web.Security.PassportIdentity::_iPassportVer
0x11dfaa  ldc.i4.3
0x11dfab  blt.s    loc_11E019
0x11dfad  ldc.i4.0
0x11dfae  stloc.s  7
0x11dfb0  br.s     loc_11DFDE
0x11dfb2  ldloc.s  6
0x11dfb4  ldloc.2
0x11dfb5  ldloc.s  7
0x11dfb7  ldelem.ref
0x11dfb8  callvirt instance object System.Web.Security.PassportIdentity::GetCurrentConfig(string strAttribute)
0x11dfbd  stloc.s  9
0x11dfbf  ldloc.s  9
0x11dfc1  brfalse.s loc_11DFD8
0x11dfc3  ldloc.s  9
0x11dfc5  isinst   [mscorlib]System.String
0x11dfca  brfalse.s loc_11DFD8
0x11dfcc  ldloc.s  4
0x11dfce  ldloc.s  7
0x11dfd0  ldloc.s  9
0x11dfd2  castclass [mscorlib]System.String
0x11dfd7  stelem.ref
0x11dfd8  ldloc.s  7
0x11dfda  ldc.i4.1
0x11dfdb  add
0x11dfdc  stloc.s  7
0x11dfde  ldloc.s  7
0x11dfe0  ldc.i4.5
0x11dfe1  blt.s    loc_11DFB2
0x11dfe3  ldc.i4.0
0x11dfe4  stloc.s  7
0x11dfe6  br.s     loc_11E014
0x11dfe8  ldloc.s  6
0x11dfea  ldloc.3
0x11dfeb  ldloc.s  7
0x11dfed  ldelem.ref
0x11dfee  callvirt instance object System.Web.Security.PassportIdentity::GetCurrentConfig(string strAttribute)
0x11dff3  stloc.s  0xA
0x11dff5  ldloc.s  0xA
0x11dff7  brfalse.s loc_11E00E
0x11dff9  ldloc.s  0xA
0x11dffb  isinst   [mscorlib]System.String
0x11e000  brfalse.s loc_11E00E
0x11e002  ldloc.s  5
0x11e004  ldloc.s  7
0x11e006  ldloc.s  0xA
0x11e008  castclass [mscorlib]System.String
0x11e00d  stelem.ref
0x11e00e  ldloc.s  7
0x11e010  ldc.i4.1
0x11e011  add
0x11e012  stloc.s  7
0x11e014  ldloc.s  7
0x11e016  ldc.i4.5
0x11e017  blt.s    loc_11DFE8
0x11e019  leave.s  loc_11E01E
0x11e01b  pop
0x11e01c  leave.s  loc_11E01E
0x11e01e  ldc.i4.0
0x11e01f  stloc.s  7
0x11e021  br       loc_11E0AF
0x11e026  ldloc.1
0x11e027  ldloc.s  7
0x11e029  ldelem.ref
0x11e02a  ldsfld   string [mscorlib]System.String::Empty
0x11e02f  newobj   instance void System.Web.HttpCookie::.ctor(string name, string value)
0x11e034  stloc.s  0xB
0x11e036  ldloc.s  0xB
0x11e038  ldc.i4   0x7CE
0x11e03d  ldc.i4.1
0x11e03e  ldc.i4.1
0x11e03f  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x11e044  callvirt instance void System.Web.HttpCookie::set_Expires(valuetype [mscorlib]System.DateTime value)
0x11e049  ldloc.s  4
0x11e04b  ldloc.s  7
0x11e04d  ldelem.ref
0x11e04e  brfalse.s loc_11E069
0x11e050  ldloc.s  4
0x11e052  ldloc.s  7
0x11e054  ldelem.ref
0x11e055  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11e05a  ldc.i4.0
0x11e05b  ble.s    loc_11E069
0x11e05d  ldloc.s  0xB
0x11e05f  ldloc.s  4
0x11e061  ldloc.s  7
0x11e063  ldelem.ref
0x11e064  callvirt instance void System.Web.HttpCookie::set_Domain(string value)
0x11e069  ldloc.s  5
0x11e06b  ldloc.s  7
0x11e06d  ldelem.ref
0x11e06e  brfalse.s loc_11E08B
0x11e070  ldloc.s  5
0x11e072  ldloc.s  7
0x11e074  ldelem.ref
0x11e075  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11e07a  ldc.i4.0
0x11e07b  ble.s    loc_11E08B
0x11e07d  ldloc.s  0xB
0x11e07f  ldloc.s  5
0x11e081  ldloc.s  7
0x11e083  ldelem.ref
0x11e084  callvirt instance void System.Web.HttpCookie::set_Path(string value)
0x11e089  br.s     loc_11E097
0x11e08b  ldloc.s  0xB
0x11e08d  ldstr    asc_1B2C3C// "/"
0x11e092  callvirt instance void System.Web.HttpCookie::set_Path(string value)
0x11e097  ldloc.0
0x11e098  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11e09d  callvirt instance class System.Web.HttpCookieCollection System.Web.HttpResponse::get_Cookies()
0x11e0a2  ldloc.s  0xB
0x11e0a4  callvirt instance void System.Web.HttpCookieCollection::Add(class System.Web.HttpCookie cookie)
0x11e0a9  ldloc.s  7
0x11e0ab  ldc.i4.1
0x11e0ac  add
0x11e0ad  stloc.s  7
0x11e0af  ldloc.s  7
0x11e0b1  ldc.i4.5
0x11e0b2  blt      loc_11E026
0x11e0b7  ldloc.0
0x11e0b8  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11e0bd  ldc.i4.m1
0x11e0be  callvirt instance void System.Web.HttpResponse::set_Expires(int32 value)
0x11e0c3  ldloc.0
0x11e0c4  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11e0c9  callvirt instance class System.Web.HttpCachePolicy System.Web.HttpResponse::get_Cache()
0x11e0ce  ldc.i4.1
0x11e0cf  callvirt instance void System.Web.HttpCachePolicy::SetCacheability(valuetype System.Web.HttpCacheability cacheability)
0x11e0d4  ldloc.0
0x11e0d5  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11e0da  ldstr    aPragma// "Pragma"
0x11e0df  ldstr    aNoCache_0// "no-cache"
0x11e0e4  callvirt instance void System.Web.HttpResponse::AppendHeader(string name, string value)
0x11e0e9  ldloc.0
0x11e0ea  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11e0ef  ldstr    aImageGif// "image/gif"
0x11e0f4  callvirt instance void System.Web.HttpResponse::set_ContentType(string value)
0x11e0f9  ldloc.0
0x11e0fa  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11e0ff  ldarg.0
0x11e100  callvirt instance void System.Web.HttpResponse::WriteFile(string filename)
0x11e105  ldloc.0
0x11e106  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x11e10b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x11e110  ldstr    aRu// "ru"
0x11e115  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11e11a  stloc.s  8
0x11e11c  ldloc.s  8
0x11e11e  brfalse.s loc_11E138
0x11e120  ldloc.s  8
0x11e122  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11e127  ldc.i4.1
0x11e128  ble.s    loc_11E138
0x11e12a  ldloc.0
0x11e12b  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x11e130  ldloc.s  8
0x11e132  ldc.i4.0
0x11e133  callvirt instance void System.Web.HttpResponse::Redirect(string url, bool endResponse)
0x11e138  ret
```
