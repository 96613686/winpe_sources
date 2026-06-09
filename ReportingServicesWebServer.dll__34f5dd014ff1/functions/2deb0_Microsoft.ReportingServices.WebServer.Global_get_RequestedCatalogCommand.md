# Microsoft.ReportingServices.WebServer.Global::get_RequestedCatalogCommand

- ea: `0x2deb0`
- end: `0x2deca`
- name: `Microsoft.ReportingServices.WebServer.Global::get_RequestedCatalogCommand`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d810`

## string_xrefs

- `0x2debf`: `rs:Command`

## pseudocode

```c

```

## disassembly

```asm
0x2deb0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2deb5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2deba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2debf  ldstr    aRsCommand// "rs:Command"
0x2dec4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2dec9  ret
```
