# Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetReportDefinitionPath

- ea: `0x9510`
- end: `0x9526`
- name: `Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetReportDefinitionPath`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9510`

## string_xrefs

- `0x9513`: `definitionPath`

## pseudocode

```c

```

## disassembly

```asm
0x9510  ldarg.1
0x9511  brtrue.s loc_951E
0x9513  ldstr    aDefinitionpath// "definitionPath"
0x9518  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x951d  throw
0x951e  ldarg.0
0x951f  ldarg.1
0x9520  stfld    var<u1> class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::m_reportDefinitionPath
0x9525  ret
```
