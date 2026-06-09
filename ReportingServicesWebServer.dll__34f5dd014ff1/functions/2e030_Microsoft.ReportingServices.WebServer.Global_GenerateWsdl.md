# Microsoft.ReportingServices.WebServer.Global::GenerateWsdl

- ea: `0x2e030`
- end: `0x2e0a6`
- name: `Microsoft.ReportingServices.WebServer.Global::GenerateWsdl`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ca30`

## callees

- `0x2cb90`
- `0x2cc60`
- `0x2dfb0`
- `0x2e030`
- `0x34c20`

## string_xrefs

- `0x2e03b`: `%ReportServerServiceObjectURL%`

## pseudocode

```c

```

## disassembly

```asm
0x2e030  ldarg.1
0x2e031  call     string Microsoft.ReportingServices.WebServer.Global::GetWsdlTemplate(string name)
0x2e036  stloc.0
0x2e037  ldloc.0
0x2e038  brfalse.s loc_2E059
0x2e03a  ldloc.0
0x2e03b  ldstr    aReportserverse// "%ReportServerServiceObjectURL%"
0x2e040  call     string Microsoft.ReportingServices.WebServer.Global::GetWsdlServiceLocation()
0x2e045  call     string [System.Web]System.Web.HttpUtility::HtmlAttributeEncode(string)
0x2e04a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2e04f  stloc.1
0x2e050  ldarg.0
0x2e051  ldloc.1
0x2e052  call     instance void Microsoft.ReportingServices.WebServer.Global::WriteUtf8XmlString(string xml)
0x2e057  ldc.i4.0
0x2e058  ret
0x2e059  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2e05e  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2e063  ldarg.1
0x2e064  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2e069  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2e06e  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpResponse::get_Filter()
0x2e073  newobj   instance void Microsoft.ReportingServices.WebServer.WsdlFilter::.ctor(string name, class [mscorlib]System.IO.Stream parentStream)
0x2e078  callvirt instance void [System.Web]System.Web.HttpResponse::set_Filter(class [mscorlib]System.IO.Stream)
0x2e07d  ldarg.2
0x2e07e  brtrue.s loc_2E0A4
0x2e080  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2e085  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2e08a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2e08f  callvirt instance string [System.Web]System.Web.HttpRequest::get_ApplicationPath()
0x2e094  ldarg.1
0x2e095  ldstr    aWsdl_0// "?wsdl"
0x2e09a  call     string [mscorlib]System.String::Concat(string, string, string)
0x2e09f  callvirt instance void [System.Web]System.Web.HttpContext::RewritePath(string)
0x2e0a4  ldc.i4.1
0x2e0a5  ret
```
