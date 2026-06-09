# Microsoft.ReportingServices.Modeling.InheritancePathItem::AddOutOfContextError

- ea: `0x1f310`
- end: `0x1f31b`
- name: `Microsoft.ReportingServices.Modeling.InheritancePathItem::AddOutOfContextError`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x1f310`: `InheritancePathItem.AddOutOfContextError should not be called.`

## pseudocode

```c

```

## disassembly

```asm
0x1f310  ldstr    aInheritancepat_0// "InheritancePathItem.AddOutOfContextErro"...
0x1f315  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1f31a  throw
```
