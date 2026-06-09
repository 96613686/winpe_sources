# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement

- ea: `0x5d40`
- end: `0x5d4e`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement`
- size: `14`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x55b0`
- `0x56c0`
- `0x57d0`
- `0x5b60`
- `0x5e80`

## callees

- `0x5d50`

## string_xrefs

- `0x5d43`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x5d40  ldarg.0
0x5d41  ldarg.1
0x5d42  ldarg.2
0x5d43  ldstr    aExtension// "Extension"
0x5d48  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension, string childName)
0x5d4d  ret
```
