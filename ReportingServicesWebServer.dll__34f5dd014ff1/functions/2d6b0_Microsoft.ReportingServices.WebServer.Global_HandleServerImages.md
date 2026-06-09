# Microsoft.ReportingServices.WebServer.Global::HandleServerImages

- ea: `0x2d6b0`
- end: `0x2d7d6`
- name: `Microsoft.ReportingServices.WebServer.Global::HandleServerImages`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d120`

## callees

- `0x2d5c0`
- `0x2d6b0`

## string_xrefs

- `0x2d757`: `Microsoft.ReportingServices.WebServer.`

## pseudocode

```c

```

## disassembly

```asm
0x2d6b0  ldarg.0
0x2d6b1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d6b6  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x2d6bb  call     bool Microsoft.ReportingServices.WebServer.Global::IsRequestToImage(string path)
0x2d6c0  brfalse  loc_2D7D2
0x2d6c5  ldsfld   string [mscorlib]System.String::Empty
0x2d6ca  stloc.0
0x2d6cb  ldarg.0
0x2d6cc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d6d1  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x2d6d6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d6db  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2d6e0  callvirt instance string [System.Web]System.Web.HttpRequest::get_ApplicationPath()
0x2d6e5  ldstr    aImagesBlankGif// "/images/blank.gif"
0x2d6ea  call     string [mscorlib]System.String::Concat(string, string)
0x2d6ef  ldc.i4.1
0x2d6f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d6f5  callvirt instance bool [mscorlib]System.String::StartsWith(string, bool, class [mscorlib]System.Globalization.CultureInfo)
0x2d6fa  brfalse.s loc_2D70A
0x2d6fc  ldstr    aBlankGif// "/blank.gif"
0x2d701  ldc.i4.1
0x2d702  call     instance string [mscorlib]System.String::Substring(int32)
0x2d707  stloc.0
0x2d708  br.s     loc_2D747
0x2d70a  ldarg.0
0x2d70b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d710  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x2d715  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d71a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2d71f  callvirt instance string [System.Web]System.Web.HttpRequest::get_ApplicationPath()
0x2d724  ldstr    aImagesLineErr1// "/images/line_err1.gif"
0x2d729  call     string [mscorlib]System.String::Concat(string, string)
0x2d72e  ldc.i4.1
0x2d72f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d734  callvirt instance bool [mscorlib]System.String::StartsWith(string, bool, class [mscorlib]System.Globalization.CultureInfo)
0x2d739  brfalse.s loc_2D747
0x2d73b  ldstr    aLineErr1Gif// "/line_err1.gif"
0x2d740  ldc.i4.1
0x2d741  call     instance string [mscorlib]System.String::Substring(int32)
0x2d746  stloc.0
0x2d747  ldloc.0
0x2d748  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d74d  brtrue   loc_2D7D2
0x2d752  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x2d757  ldstr    aMicrosoftRepor_129// "Microsoft.ReportingServices.WebServer."
0x2d75c  ldloc.0
0x2d75d  call     string [mscorlib]System.String::Concat(string, string)
0x2d762  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x2d767  stloc.1
0x2d768  ldloc.1
0x2d769  brfalse.s loc_2D7BE
0x2d76b  ldloc.1
0x2d76c  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x2d771  conv.ovf.i
0x2d772  newarr   [mscorlib]System.Byte
0x2d777  stloc.2
0x2d778  ldloc.1
0x2d779  ldloc.2
0x2d77a  ldc.i4.0
0x2d77b  ldloc.2
0x2d77c  ldlen
0x2d77d  conv.i4
0x2d77e  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x2d783  pop
0x2d784  ldarg.0
0x2d785  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x2d78a  ldstr    aImage_1// "image/"
0x2d78f  ldloc.0
0x2d790  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x2d795  ldstr    asc_42AB6// "."
0x2d79a  ldsfld   string [mscorlib]System.String::Empty
0x2d79f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2d7a4  call     string [mscorlib]System.String::Concat(string, string)
0x2d7a9  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2d7ae  ldarg.0
0x2d7af  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x2d7b4  ldloc.2
0x2d7b5  callvirt instance void [System.Web]System.Web.HttpResponse::BinaryWrite(unsigned int8[])
0x2d7ba  ldc.i4.1
0x2d7bb  stloc.3
0x2d7bc  leave.s  loc_2D7D4
0x2d7be  leave.s  loc_2D7CA
0x2d7c0  ldloc.1
0x2d7c1  brfalse.s loc_2D7C9
0x2d7c3  ldloc.1
0x2d7c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d7c9  endfinally
0x2d7ca  leave.s  loc_2D7D2
0x2d7cc  pop
0x2d7cd  leave.s  loc_2D7D2
0x2d7cf  pop
0x2d7d0  leave.s  loc_2D7D2
0x2d7d2  ldc.i4.0
0x2d7d3  ret
0x2d7d4  ldloc.3
0x2d7d5  ret
```
