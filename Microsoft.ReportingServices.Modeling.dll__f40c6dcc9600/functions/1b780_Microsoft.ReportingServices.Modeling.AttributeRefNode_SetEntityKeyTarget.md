# Microsoft.ReportingServices.Modeling.AttributeRefNode::SetEntityKeyTarget

- ea: `0x1b780`
- end: `0x1b7b4`
- name: `Microsoft.ReportingServices.Modeling.AttributeRefNode::SetEntityKeyTarget`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x8530`
- `0x97d0`
- `0x9cf0`
- `0x1b780`
- `0x231d0`

## string_xrefs

- `0x1b788`: `AttributeRefNode is not compiled.`
- `0x1b7a8`: `SetEntityKeyTarget is called on AttributeRefNode and m_attribute.ReplaceWithExpression && ctx.ShouldNormalize.`

## pseudocode

```c

```

## disassembly

```asm
0x1b780  ldarg.0
0x1b781  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1b786  brtrue.s loc_1B793
0x1b788  ldstr    aAttributerefno// "AttributeRefNode is not compiled."
0x1b78d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b792  throw
0x1b793  ldarg.0
0x1b794  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b799  callvirt instance bool Microsoft.ReportingServices.Modeling.IQueryAttributeInternal::get_ReplaceWithExpression()
0x1b79e  brfalse.s loc_1B7B3
0x1b7a0  ldarg.2
0x1b7a1  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldNormalize()
0x1b7a6  brfalse.s loc_1B7B3
0x1b7a8  ldstr    aSetentitykeyta_1// "SetEntityKeyTarget is called on Attribu"...
0x1b7ad  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b7b2  throw
0x1b7b3  ret
```
