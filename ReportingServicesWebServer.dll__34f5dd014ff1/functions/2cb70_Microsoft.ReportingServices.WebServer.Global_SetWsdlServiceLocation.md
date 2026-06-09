# Microsoft.ReportingServices.WebServer.Global::SetWsdlServiceLocation

- ea: `0x2cb70`
- end: `0x2cb90`
- name: `Microsoft.ReportingServices.WebServer.Global::SetWsdlServiceLocation`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ca30`

## callees

- `0x2cc00`

## string_xrefs

- `0x2cb7a`: `WsdlServiceLocation`

## pseudocode

```c

```

## disassembly

```asm
0x2cb70  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2cb75  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x2cb7a  ldstr    aWsdlserviceloc// "WsdlServiceLocation"
0x2cb7f  call     string Microsoft.ReportingServices.WebServer.Global::get_ReportServerExternalUrlRemapped()
0x2cb84  ldarg.0
0x2cb85  call     string [mscorlib]System.String::Concat(string, string)
0x2cb8a  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x2cb8f  ret
```
