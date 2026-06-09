# Microsoft.ReportingServices.Modeling.NullNode::SetEntityKeyTarget

- ea: `0x1dc80`
- end: `0x1dc94`
- name: `Microsoft.ReportingServices.Modeling.NullNode::SetEntityKeyTarget`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9cf0`
- `0x1dc80`

## string_xrefs

- `0x1dc88`: `NullNode is not compiled.`

## pseudocode

```c

```

## disassembly

```asm
0x1dc80  ldarg.0
0x1dc81  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1dc86  brtrue.s loc_1DC93
0x1dc88  ldstr    aNullnodeIsNotC// "NullNode is not compiled."
0x1dc8d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1dc92  throw
0x1dc93  ret
```
