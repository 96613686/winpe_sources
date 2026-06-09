# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::set_CommandParamValue

- ea: `0xc680`
- end: `0xc692`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::set_CommandParamValue`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc3e0`

## string_xrefs

- `0xc686`: `Command`

## pseudocode

```c

```

## disassembly

```asm
0xc680  ldarg.0
0xc681  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RSRequestParameters::get_CatalogParameters()
0xc686  ldstr    aCommand// "Command"
0xc68b  ldarg.1
0xc68c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0xc691  ret
```
