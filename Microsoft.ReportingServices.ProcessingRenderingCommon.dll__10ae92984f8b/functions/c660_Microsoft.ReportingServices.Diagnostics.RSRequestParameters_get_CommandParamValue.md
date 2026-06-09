# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_CommandParamValue

- ea: `0xc660`
- end: `0xc671`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_CommandParamValue`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc3e0`

## string_xrefs

- `0xc666`: `Command`

## pseudocode

```c

```

## disassembly

```asm
0xc660  ldarg.0
0xc661  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_CatalogParameters()
0xc666  ldstr    aCommand// "Command"
0xc66b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc670  ret
```
