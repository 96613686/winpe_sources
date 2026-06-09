# Microsoft.ReportingServices.WebServer.Global::GetWsdlServiceLocation

- ea: `0x2cb90`
- end: `0x2cbaa`
- name: `Microsoft.ReportingServices.WebServer.Global::GetWsdlServiceLocation`
- size: `26`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e030`
- `0x34ab0`
- `0x34d20`

## string_xrefs

- `0x2cb9a`: `WsdlServiceLocation`

## pseudocode

```c

```

## disassembly

```asm
0x2cb90  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2cb95  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x2cb9a  ldstr    aWsdlserviceloc// "WsdlServiceLocation"
0x2cb9f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x2cba4  isinst   [mscorlib]System.String
0x2cba9  ret
```
