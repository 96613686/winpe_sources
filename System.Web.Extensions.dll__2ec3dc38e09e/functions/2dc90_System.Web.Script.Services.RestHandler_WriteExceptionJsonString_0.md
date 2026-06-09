# System.Web.Script.Services.RestHandler::WriteExceptionJsonString_0

- ea: `0x2dc90`
- end: `0x2dda1`
- name: `System.Web.Script.Services.RestHandler::WriteExceptionJsonString_0`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x2be30`
- `0x2dc80`

## callees

- `0x2b710`
- `0x2dc50`
- `0x2dc90`
- `0x31cb0`

## string_xrefs

- `0x2dce0`: `application/json`
- `0x2dcf0`: `jsonerror`

## pseudocode

```c

```

## disassembly

```asm
0x2dc90  ldarg.0
0x2dc91  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dc96  callvirt instance string [System.Web]System.Web.HttpResponse::get_Charset()
0x2dc9b  stloc.0
0x2dc9c  ldarg.0
0x2dc9d  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dca2  callvirt instance void [System.Web]System.Web.HttpResponse::ClearHeaders()
0x2dca7  ldarg.0
0x2dca8  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dcad  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0x2dcb2  ldarg.0
0x2dcb3  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dcb8  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x2dcbd  ldarg.0
0x2dcbe  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dcc3  ldarg.2
0x2dcc4  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x2dcc9  ldarg.0
0x2dcca  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dccf  ldarg.2
0x2dcd0  call     string [System.Web]System.Web.HttpWorkerRequest::GetStatusDescription(int32)
0x2dcd5  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusDescription(string)
0x2dcda  ldarg.0
0x2dcdb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dce0  ldstr    aApplicationJso// "application/json"
0x2dce5  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2dcea  ldarg.0
0x2dceb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dcf0  ldstr    aJsonerror// "jsonerror"
0x2dcf5  ldstr    aTrue// "true"
0x2dcfa  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x2dcff  ldarg.0
0x2dd00  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dd05  ldloc.0
0x2dd06  callvirt instance void [System.Web]System.Web.HttpResponse::set_Charset(string)
0x2dd0b  ldarg.0
0x2dd0c  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dd11  ldc.i4.1
0x2dd12  callvirt instance void [System.Web]System.Web.HttpResponse::set_TrySkipIisCustomErrors(bool)
0x2dd17  ldarg.0
0x2dd18  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dd1d  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpResponse::get_OutputStream()
0x2dd22  ldc.i4.0
0x2dd23  newobj   instance void [mscorlib]System.Text.UTF8Encoding::.ctor(bool)
0x2dd28  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x2dd2d  stloc.1
0x2dd2e  ldarg.1
0x2dd2f  isinst   [mscorlib]System.Reflection.TargetInvocationException
0x2dd34  brfalse.s loc_2DD3E
0x2dd36  ldarg.1
0x2dd37  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x2dd3c  starg.s  1
0x2dd3e  ldarg.0
0x2dd3f  callvirt instance bool [System.Web]System.Web.HttpContext::get_IsCustomErrorEnabled()
0x2dd44  brfalse.s loc_2DD67
0x2dd46  ldloc.1
0x2dd47  call     string System.Web.Resources.AtlasWeb::get_WebService_Error()
0x2dd4c  ldsfld   string [mscorlib]System.String::Empty
0x2dd51  ldsfld   string [mscorlib]System.String::Empty
0x2dd56  call     object System.Web.Script.Services.RestHandler::BuildWebServiceError(string msg, string stack, string type)
0x2dd5b  call     string System.Web.Script.Serialization.JavaScriptSerializer::SerializeInternal(object o)
0x2dd60  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2dd65  br.s     loc_2DD8E
0x2dd67  ldloc.1
0x2dd68  ldarg.1
0x2dd69  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2dd6e  ldarg.1
0x2dd6f  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x2dd74  ldarg.1
0x2dd75  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x2dd7a  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2dd7f  call     object System.Web.Script.Services.RestHandler::BuildWebServiceError(string msg, string stack, string type)
0x2dd84  call     string System.Web.Script.Serialization.JavaScriptSerializer::SerializeInternal(object o)
0x2dd89  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2dd8e  ldloc.1
0x2dd8f  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x2dd94  leave.s  loc_2DDA0
0x2dd96  ldloc.1
0x2dd97  brfalse.s loc_2DD9F
0x2dd99  ldloc.1
0x2dd9a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dd9f  endfinally
0x2dda0  ret
```
