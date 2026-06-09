# Microsoft.ReportingServices.WebServer.Global::WriteXsdResource

- ea: `0x2cd50`
- end: `0x2cda1`
- name: `Microsoft.ReportingServices.WebServer.Global::WriteXsdResource`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2ccb0`

## string_xrefs

- `0x2cd5b`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x2cd50  ldarg.0
0x2cd51  call     instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x2cd56  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2cd5b  ldstr    aTextXml// "text/xml"
0x2cd60  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2cd65  ldarg.0
0x2cd66  call     instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x2cd6b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2cd70  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2cd75  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding)
0x2cd7a  ldarg.1
0x2cd7b  call     unsigned int8[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::GetResourceBinary(string)
0x2cd80  stloc.0
0x2cd81  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2cd86  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2cd8b  ldloc.0
0x2cd8c  callvirt instance void [System.Web]System.Web.HttpResponse::BinaryWrite(unsigned int8[])
0x2cd91  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2cd96  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2cd9b  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x2cda0  ret
```
