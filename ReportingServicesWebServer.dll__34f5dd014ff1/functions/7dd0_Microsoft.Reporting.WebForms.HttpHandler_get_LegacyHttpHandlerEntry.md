# Microsoft.Reporting.WebForms.HttpHandler::get_LegacyHttpHandlerEntry

- ea: `0x7dd0`
- end: `0x7dec`
- name: `Microsoft.Reporting.WebForms.HttpHandler::get_LegacyHttpHandlerEntry`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x9810`

## callees

- `0x7da0`
- `0x7db0`

## string_xrefs

- `0x7dd5`: `<add verb="*" path="{0}" type = "{1}" />`

## pseudocode

```c

```

## disassembly

```asm
0x7dd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7dd5  ldstr    aAddVerbPath0Ty// "<add verb=\"*\" path=\"{0}\" type = \"{"...
0x7dda  ldarg.0
0x7ddb  callvirt instance string Microsoft.Reporting.WebForms.HttpHandler::get_HttpHandlerPath()
0x7de0  ldarg.0
0x7de1  call     instance string Microsoft.Reporting.WebForms.HttpHandler::GetHttpHandlerTypeName()
0x7de6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x7deb  ret
```
