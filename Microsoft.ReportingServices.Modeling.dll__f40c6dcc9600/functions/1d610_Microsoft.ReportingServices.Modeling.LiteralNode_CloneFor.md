# Microsoft.ReportingServices.Modeling.LiteralNode::CloneFor

- ea: `0x1d610`
- end: `0x1d625`
- name: `Microsoft.ReportingServices.Modeling.LiteralNode::CloneFor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9cf0`
- `0x1d610`

## string_xrefs

- `0x1d618`: `LiteralNode is not compiled.`

## pseudocode

```c

```

## disassembly

```asm
0x1d610  ldarg.0
0x1d611  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1d616  brtrue.s loc_1D623
0x1d618  ldstr    aLiteralnodeIsN// "LiteralNode is not compiled."
0x1d61d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1d622  throw
0x1d623  ldarg.0
0x1d624  ret
```
