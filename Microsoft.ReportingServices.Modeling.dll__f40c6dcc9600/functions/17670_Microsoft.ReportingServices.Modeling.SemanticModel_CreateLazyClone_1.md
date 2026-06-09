# Microsoft.ReportingServices.Modeling.SemanticModel::CreateLazyClone_1

- ea: `0x17670`
- end: `0x1767b`
- name: `Microsoft.ReportingServices.Modeling.SemanticModel::CreateLazyClone_1`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x17670`: `Model.CreateLazyClone was called`

## pseudocode

```c

```

## disassembly

```asm
0x17670  ldstr    aModelCreatelaz// "Model.CreateLazyClone was called"
0x17675  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1767a  throw
```
