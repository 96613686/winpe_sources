# DsvColumnInfoDS::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize

- ea: `0x30cf0`
- end: `0x30cfb`
- name: `DsvColumnInfoDS::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x30cf0`: `Deserialize is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x30cf0  ldstr    aDeserializeIsN// "Deserialize is not supported."
0x30cf5  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x30cfa  throw
```
