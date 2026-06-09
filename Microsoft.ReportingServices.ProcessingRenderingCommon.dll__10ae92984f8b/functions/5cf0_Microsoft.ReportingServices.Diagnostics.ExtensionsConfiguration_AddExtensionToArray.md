# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::AddExtensionToArray

- ea: `0x5cf0`
- end: `0x5d20`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::AddExtensionToArray`
- size: `48`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x55b0`
- `0x56c0`
- `0x57d0`
- `0x5a00`
- `0x5b60`
- `0x5bd0`

## callees

- `0x4fa0`
- `0x5cf0`
- `0x5d20`
- `0x15740`

## pseudocode

```c

```

## disassembly

```asm
0x5cf0  ldarg.2
0x5cf1  ldarg.1
0x5cf2  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x5cf7  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x5cfc  brfalse.s loc_5D17
0x5cfe  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5d03  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x5d08  brfalse.s loc_5D16
0x5d0a  ldarg.0
0x5d0b  ldarg.1
0x5d0c  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x5d11  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::TraceNonUniqueExtensionError(string extensionName)
0x5d16  ret
0x5d17  ldarg.2
0x5d18  ldarg.1
0x5d19  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5d1e  pop
0x5d1f  ret
```
