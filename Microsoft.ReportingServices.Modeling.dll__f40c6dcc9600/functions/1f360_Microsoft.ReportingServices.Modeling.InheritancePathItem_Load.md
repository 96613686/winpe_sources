# Microsoft.ReportingServices.Modeling.InheritancePathItem::Load

- ea: `0x1f360`
- end: `0x1f36b`
- name: `Microsoft.ReportingServices.Modeling.InheritancePathItem::Load`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x1f360`: `InheritancePathItem.Load should not be called`

## pseudocode

```c

```

## disassembly

```asm
0x1f360  ldstr    aInheritancepat_1// "InheritancePathItem.Load should not be "...
0x1f365  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1f36a  throw
```
