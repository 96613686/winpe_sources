# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::.cctor

- ea: `0x5180`
- end: `0x51c7`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::.cctor`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x4fb0`
- `0x4fd0`
- `0x4ff0`
- `0x5030`
- `0x5100`

## string_xrefs

- `0x51ad`: `Microsoft.ReportingServices.SemanticQueryEngine`
- `0x51bc`: `Microsoft.ReportingServices.SemanticQueryEngine.SemanticQueryConnection`

## pseudocode

```c

```

## disassembly

```asm
0x5180  newobj   instance void Microsoft.ReportingServices.Diagnostics.Extension::.ctor()
0x5185  stsfld   class Microsoft.ReportingServices.Diagnostics.Extension Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_semanticQueryEngine
0x518a  ldsfld   class Microsoft.ReportingServices.Diagnostics.Extension Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_semanticQueryEngine
0x518f  ldstr    aData// "Data"
0x5194  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x5199  ldsfld   class Microsoft.ReportingServices.Diagnostics.Extension Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_semanticQueryEngine
0x519e  ldstr    aSemanticquerye// "SemanticQueryEngine"
0x51a3  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Name(string value)
0x51a8  ldsfld   class Microsoft.ReportingServices.Diagnostics.Extension Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_semanticQueryEngine
0x51ad  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.SemanticQue"...
0x51b2  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Assembly(string value)
0x51b7  ldsfld   class Microsoft.ReportingServices.Diagnostics.Extension Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_semanticQueryEngine
0x51bc  ldstr    aMicrosoftRepor_0// "Microsoft.ReportingServices.SemanticQue"...
0x51c1  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Class(string value)
0x51c6  ret
```
