# DsvTableCollectionInfoDS::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize

- ea: `0x30830`
- end: `0x3083b`
- name: `DsvTableCollectionInfoDS::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x30830`: `Deserialize is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x30830  ldstr    aDeserializeIsN// "Deserialize is not supported."
0x30835  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x3083a  throw
```
