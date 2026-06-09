# Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::Fail

- ea: `0x11a70`
- end: `0x11a83`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::Fail`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x11d40`

## string_xrefs

- `0x11a72`: `Un-named assertion fired for component `

## pseudocode

```c

```

## disassembly

```asm
0x11a70  ldarg.0
0x11a71  ldarg.1
0x11a72  ldstr    aUnNamedAsserti_0// "Un-named assertion fired for component "
0x11a77  ldarg.1
0x11a78  call     string [mscorlib]System.String::Concat(string, string)
0x11a7d  call     instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::FailInternal(string componentName, string message)
0x11a82  ret
```
