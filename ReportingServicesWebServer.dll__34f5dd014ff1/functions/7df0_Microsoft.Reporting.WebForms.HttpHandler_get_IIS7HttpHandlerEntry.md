# Microsoft.Reporting.WebForms.HttpHandler::get_IIS7HttpHandlerEntry

- ea: `0x7df0`
- end: `0x7e11`
- name: `Microsoft.Reporting.WebForms.HttpHandler::get_IIS7HttpHandlerEntry`
- size: `33`
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

- `0x7df5`: `<add name="{0}" preCondition="integratedMode" verb="*" path="{1}" type="{2}" />`

## pseudocode

```c

```

## disassembly

```asm
0x7df0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7df5  ldstr    aAddName0Precon// "<add name=\"{0}\" preCondition=\"integr"...
0x7dfa  ldstr    aReportviewerwe// "ReportViewerWebControlHandler"
0x7dff  ldarg.0
0x7e00  callvirt instance string Microsoft.Reporting.WebForms.HttpHandler::get_HttpHandlerPath()
0x7e05  ldarg.0
0x7e06  call     instance string Microsoft.Reporting.WebForms.HttpHandler::GetHttpHandlerTypeName()
0x7e0b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x7e10  ret
```
