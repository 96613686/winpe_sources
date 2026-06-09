# RolePathItemResolveReferences::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize

- ea: `0x37380`
- end: `0x3738b`
- name: `RolePathItemResolveReferences::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x37380`: `Deserialize is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x37380  ldstr    aDeserializeIsN// "Deserialize is not supported."
0x37385  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x3738a  throw
```
