# Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::DefaultAssertMessage

- ea: `0x11780`
- end: `0x11791`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::DefaultAssertMessage`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x117a0`

## string_xrefs

- `0x11785`: `Un-named assertion fired for component {0}`

## pseudocode

```c

```

## disassembly

```asm
0x11780  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11785  ldstr    aUnNamedAsserti// "Un-named assertion fired for component "...
0x1178a  ldarg.0
0x1178b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x11790  ret
```
