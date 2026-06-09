# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::TraceNonUniqueExtensionError

- ea: `0x5d20`
- end: `0x5d3a`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::TraceNonUniqueExtensionError`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5cf0`

## string_xrefs

- `0x5d25`: `More then one extension found with the name '{0}'. Only the first one found will be used.`

## pseudocode

```c

```

## disassembly

```asm
0x5d20  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5d25  ldstr    aMoreThenOneExt// "More then one extension found with the "...
0x5d2a  ldc.i4.1
0x5d2b  newarr   [mscorlib]System.Object
0x5d30  dup
0x5d31  ldc.i4.0
0x5d32  ldarg.1
0x5d33  stelem.ref
0x5d34  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x5d39  ret
```
