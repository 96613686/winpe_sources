# Microsoft.ReportingServices.Modeling.NullNode::CloneFor

- ea: `0x1dca0`
- end: `0x1dcb5`
- name: `Microsoft.ReportingServices.Modeling.NullNode::CloneFor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9cf0`
- `0x1dca0`

## string_xrefs

- `0x1dca8`: `NullNode is not compiled.`

## pseudocode

```c

```

## disassembly

```asm
0x1dca0  ldarg.0
0x1dca1  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1dca6  brtrue.s loc_1DCB3
0x1dca8  ldstr    aNullnodeIsNotC// "NullNode is not compiled."
0x1dcad  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1dcb2  throw
0x1dcb3  ldarg.0
0x1dcb4  ret
```
