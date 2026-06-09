# Microsoft.ReportingServices.Modeling.InheritancePathItem::WriteTo

- ea: `0x1f370`
- end: `0x1f37b`
- name: `Microsoft.ReportingServices.Modeling.InheritancePathItem::WriteTo`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x1f370`: `InheritancePathItem.WriteTo should not be called`

## pseudocode

```c

```

## disassembly

```asm
0x1f370  ldstr    aInheritancepat_2// "InheritancePathItem.WriteTo should not "...
0x1f375  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1f37a  throw
```
