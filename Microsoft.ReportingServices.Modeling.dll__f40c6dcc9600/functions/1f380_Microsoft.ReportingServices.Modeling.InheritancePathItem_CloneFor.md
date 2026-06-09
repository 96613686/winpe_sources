# Microsoft.ReportingServices.Modeling.InheritancePathItem::CloneFor

- ea: `0x1f380`
- end: `0x1f38b`
- name: `Microsoft.ReportingServices.Modeling.InheritancePathItem::CloneFor`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x1f380`: `InheritancePathItem.CloneFor should not be called`

## pseudocode

```c

```

## disassembly

```asm
0x1f380  ldstr    aInheritancepat_3// "InheritancePathItem.CloneFor should not"...
0x1f385  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1f38a  throw
```
