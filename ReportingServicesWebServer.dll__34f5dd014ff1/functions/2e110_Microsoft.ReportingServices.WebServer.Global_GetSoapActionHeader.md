# Microsoft.ReportingServices.WebServer.Global::GetSoapActionHeader

- ea: `0x2e110`
- end: `0x2e148`
- name: `Microsoft.ReportingServices.WebServer.Global::GetSoapActionHeader`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2c950`
- `0x2d120`

## callees

- `0x2e110`

## string_xrefs

- `0x2e136`: `application/soap+xml`

## pseudocode

```c

```

## disassembly

```asm
0x2e110  ldarg.1
0x2e111  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2e116  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x2e11b  ldstr    aSoapaction// "SOAPAction"
0x2e120  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2e125  stloc.0
0x2e126  ldloc.0
0x2e127  brtrue.s loc_2E146
0x2e129  ldarg.1
0x2e12a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2e12f  callvirt instance string [System.Web]System.Web.HttpRequest::get_ContentType()
0x2e134  stloc.1
0x2e135  ldloc.1
0x2e136  ldstr    aApplicationSoa// "application/soap+xml"
0x2e13b  ldc.i4.5
0x2e13c  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2e141  ldc.i4.m1
0x2e142  beq.s    loc_2E146
0x2e144  ldloc.1
0x2e145  stloc.0
0x2e146  ldloc.0
0x2e147  ret
```
