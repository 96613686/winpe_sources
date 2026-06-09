# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CommandUserInterface::ProcessRequest

- ea: `0x34f0`
- end: `0x3629`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CommandUserInterface::ProcessRequest`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x34f0`
- `0x3630`

## string_xrefs

- `0x3504`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x34f0  ldarg.1
0x34f1  brtrue.s loc_34FE
0x34f3  ldstr    aContext// "context"
0x34f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x34fd  throw
0x34fe  ldarg.1
0x34ff  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x3504  ldstr    aApplicationJso// "application/json"
0x3509  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x350e  ldsfld   string [mscorlib]System.String::Empty
0x3513  stloc.0
0x3514  call     class [Microsoft.SharePoint.Spx.WebSite.Ribbon]Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WHCUIDataSource Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CommandUserInterface::GetCuiDataSource()
0x3519  stloc.1
0x351a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x351f  stloc.2
0x3520  ldloc.2
0x3521  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3526  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x352b  stloc.3
0x352c  ldloc.1
0x352d  ldloc.3
0x352e  callvirt instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.CUIDataSource::WriteResult(class [mscorlib]System.IO.TextWriter)
0x3533  ldloc.3
0x3534  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3539  ldloc.2
0x353a  callvirt instance string [mscorlib]System.Object::ToString()
0x353f  stloc.0
0x3540  leave.s  loc_354C
0x3542  ldloc.3
0x3543  brfalse.s loc_354B
0x3545  ldloc.3
0x3546  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x354b  endfinally
0x354c  ldarg.1
0x354d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3552  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x3557  ldstr    aAcceptEncoding// "Accept-Encoding"
0x355c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3561  stloc.s  4
0x3563  ldc.i4.0
0x3564  stloc.s  5
0x3566  ldloc.s  4
0x3568  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x356d  brtrue.s loc_3582
0x356f  ldloc.s  4
0x3571  ldstr    aGzip// "gzip"
0x3576  ldc.i4.5
0x3577  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x357c  ldc.i4.m1
0x357d  beq.s    loc_3582
0x357f  ldc.i4.1
0x3580  stloc.s  5
0x3582  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x3587  ldloc.0
0x3588  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x358d  stloc.s  6
0x358f  ldloc.s  5
0x3591  brfalse.s loc_35EC
0x3593  ldarg.1
0x3594  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x3599  ldstr    aContentEncodin// "Content-Encoding"
0x359e  ldstr    aGzip// "gzip"
0x35a3  callvirt instance void [System.Web]System.Web.HttpResponse::AppendHeader(string, string)
0x35a8  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x35ad  stloc.s  7
0x35af  ldloc.s  7
0x35b1  ldc.i4.1
0x35b2  newobj   instance void [System]System.IO.Compression.GZipStream::.ctor(class [mscorlib]System.IO.Stream, valuetype [System]System.IO.Compression.CompressionMode)
0x35b7  stloc.s  8
0x35b9  ldloc.s  8
0x35bb  ldloc.s  6
0x35bd  ldc.i4.0
0x35be  ldloc.s  6
0x35c0  ldlen
0x35c1  conv.i4
0x35c2  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x35c7  leave.s  loc_35D5
0x35c9  ldloc.s  8
0x35cb  brfalse.s loc_35D4
0x35cd  ldloc.s  8
0x35cf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35d4  endfinally
0x35d5  ldloc.s  7
0x35d7  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x35dc  stloc.s  6
0x35de  leave.s  loc_35EC
0x35e0  ldloc.s  7
0x35e2  brfalse.s loc_35EB
0x35e4  ldloc.s  7
0x35e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35eb  endfinally
0x35ec  ldarg.1
0x35ed  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x35f2  ldloc.s  6
0x35f4  callvirt instance void [System.Web]System.Web.HttpResponse::BinaryWrite(unsigned int8[])
0x35f9  ldarg.1
0x35fa  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x35ff  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x3604  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3609  stloc.s  9
0x360b  ldloca.s 9
0x360d  ldsfld   int32 Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CommandUserInterface::cacheLength
0x3612  conv.r8
0x3613  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x3618  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetExpires(valuetype [mscorlib]System.DateTime)
0x361d  ldarg.1
0x361e  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x3623  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x3628  ret
```
