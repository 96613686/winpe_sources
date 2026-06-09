# Microsoft.ReportingServices.Modeling.InheritancePathItem::get_PropertyName

- ea: `0x1f290`
- end: `0x1f29b`
- name: `Microsoft.ReportingServices.Modeling.InheritancePathItem::get_PropertyName`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x1f290`: `InheritancePathItem.PropertyName should not be called`

## pseudocode

```c

```

## disassembly

```asm
0x1f290  ldstr    aInheritancepat// "InheritancePathItem.PropertyName should"...
0x1f295  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1f29a  throw
```
