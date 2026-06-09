# Microsoft.ReportingServices.Modeling.PathItem::Equals

- ea: `0x1eaf0`
- end: `0x1eafb`
- name: `Microsoft.ReportingServices.Modeling.PathItem::Equals`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`

## string_xrefs

- `0x1eaf0`: `PathItem.Equals called`

## pseudocode

```c

```

## disassembly

```asm
0x1eaf0  ldstr    aPathitemEquals// "PathItem.Equals called"
0x1eaf5  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1eafa  throw
```
