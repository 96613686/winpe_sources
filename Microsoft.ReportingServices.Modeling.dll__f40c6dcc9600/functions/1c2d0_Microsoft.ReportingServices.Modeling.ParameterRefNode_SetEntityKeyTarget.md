# Microsoft.ReportingServices.Modeling.ParameterRefNode::SetEntityKeyTarget

- ea: `0x1c2d0`
- end: `0x1c2f7`
- name: `Microsoft.ReportingServices.Modeling.ParameterRefNode::SetEntityKeyTarget`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x8570`
- `0x97d0`
- `0x9cf0`
- `0x1c2d0`

## string_xrefs

- `0x1c2d8`: `ParameterRefNode is not compiled.`
- `0x1c2eb`: `SetEntityKeyTarget is called on ParameterRefNode and ctx.ShouldReplaceParameterRefs is true.`

## pseudocode

```c

```

## disassembly

```asm
0x1c2d0  ldarg.0
0x1c2d1  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1c2d6  brtrue.s loc_1C2E3
0x1c2d8  ldstr    aParameterrefno// "ParameterRefNode is not compiled."
0x1c2dd  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1c2e2  throw
0x1c2e3  ldarg.2
0x1c2e4  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldReplaceParameterRefs()
0x1c2e9  brfalse.s loc_1C2F6
0x1c2eb  ldstr    aSetentitykeyta_3// "SetEntityKeyTarget is called on Paramet"...
0x1c2f0  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1c2f5  throw
0x1c2f6  ret
```
