# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::validationHandler

- ea: `0xb30`
- end: `0xb46`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::validationHandler`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xb30`: `Invalid value used in Input XML : `

## pseudocode

```c

```

## disassembly

```asm
0xb30  ldstr    aInvalidValueUs// "Invalid value used in Input XML : "
0xb35  ldarg.1
0xb36  callvirt instance string [System.Xml]System.Xml.Schema.ValidationEventArgs::get_Message()
0xb3b  call     string [mscorlib]System.String::Concat(string, string)
0xb40  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xb45  throw
```
