# Microsoft.ReportingServices.WebServer.WsdlFilter::Close

- ea: `0x34d20`
- end: `0x34db0`
- name: `Microsoft.ReportingServices.WebServer.WsdlFilter::Close`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2cb90`
- `0x2dff0`

## string_xrefs

- `0x34d6a`: `text/xml`
- `0x34d4b`: `%ReportServerServiceObjectURL%`

## pseudocode

```c

```

## disassembly

```asm
0x34d20  ldarg.0
0x34d21  ldfld    class [mscorlib]System.IO.MemoryStream Microsoft.ReportingServices.WebServer.WsdlFilter::m_stream
0x34d26  ldc.i4.0
0x34d27  conv.i8
0x34d28  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x34d2d  ldarg.0
0x34d2e  ldfld    class [mscorlib]System.IO.MemoryStream Microsoft.ReportingServices.WebServer.WsdlFilter::m_stream
0x34d33  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x34d38  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x34d3d  stloc.0
0x34d3e  ldarg.0
0x34d3f  ldfld    string Microsoft.ReportingServices.WebServer.WsdlFilter::m_name
0x34d44  ldloc.0
0x34d45  call     void Microsoft.ReportingServices.WebServer.Global::SetWsdlTemplate(string name, string wsdlTemplate)
0x34d4a  ldloc.0
0x34d4b  ldstr    aReportserverse// "%ReportServerServiceObjectURL%"
0x34d50  call     string Microsoft.ReportingServices.WebServer.Global::GetWsdlServiceLocation()
0x34d55  call     string [System.Web]System.Web.HttpUtility::HtmlAttributeEncode(string)
0x34d5a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x34d5f  stloc.1
0x34d60  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34d65  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x34d6a  ldstr    aTextXml// "text/xml"
0x34d6f  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x34d74  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34d79  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x34d7e  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x34d83  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding)
0x34d88  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x34d8d  ldloc.1
0x34d8e  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x34d93  stloc.2
0x34d94  ldarg.0
0x34d95  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.WebServer.WsdlFilter::m_parentStream
0x34d9a  ldloc.2
0x34d9b  ldc.i4.0
0x34d9c  ldloc.2
0x34d9d  ldlen
0x34d9e  conv.i4
0x34d9f  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x34da4  ldarg.0
0x34da5  ldfld    class [mscorlib]System.IO.MemoryStream Microsoft.ReportingServices.WebServer.WsdlFilter::m_stream
0x34daa  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x34daf  ret
```
