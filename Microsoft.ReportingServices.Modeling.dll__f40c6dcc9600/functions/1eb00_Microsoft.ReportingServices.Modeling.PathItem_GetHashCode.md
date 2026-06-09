# Microsoft.ReportingServices.Modeling.PathItem::GetHashCode

- ea: `0x1eb00`
- end: `0x1eb0b`
- name: `Microsoft.ReportingServices.Modeling.PathItem::GetHashCode`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x1eb00`: `PathItem.GetHashCode called`

## pseudocode

```c

```

## disassembly

```asm
0x1eb00  ldstr    aPathitemGethas// "PathItem.GetHashCode called"
0x1eb05  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1eb0a  throw
```
