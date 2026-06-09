# Microsoft.ReportingServices.WebServer.Global::WriteUtf8XmlString

- ea: `0x2cc60`
- end: `0x2ccaf`
- name: `Microsoft.ReportingServices.WebServer.Global::WriteUtf8XmlString`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2e030`

## callees

- `0x2cc60`

## string_xrefs

- `0x2cc6b`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x2cc60  ldarg.0
0x2cc61  call     instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x2cc66  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2cc6b  ldstr    aTextXml// "text/xml"
0x2cc70  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2cc75  ldarg.0
0x2cc76  call     instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x2cc7b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2cc80  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2cc85  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding)
0x2cc8a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2cc8f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2cc94  ldarg.1
0x2cc95  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2cc9a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2cc9f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2cca4  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0x2cca9  leave.s  loc_2CCAE
0x2ccab  pop
0x2ccac  leave.s  loc_2CCAE
0x2ccae  ret
```
