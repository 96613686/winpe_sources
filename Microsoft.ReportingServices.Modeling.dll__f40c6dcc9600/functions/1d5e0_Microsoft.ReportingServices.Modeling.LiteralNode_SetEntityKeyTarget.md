# Microsoft.ReportingServices.Modeling.LiteralNode::SetEntityKeyTarget

- ea: `0x1d5e0`
- end: `0x1d608`
- name: `Microsoft.ReportingServices.Modeling.LiteralNode::SetEntityKeyTarget`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9cf0`
- `0x1d5e0`

## string_xrefs

- `0x1d5e8`: `LiteralNode is not compiled.`

## pseudocode

```c

```

## disassembly

```asm
0x1d5e0  ldarg.0
0x1d5e1  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1d5e6  brtrue.s loc_1D5F3
0x1d5e8  ldstr    aLiteralnodeIsN// "LiteralNode is not compiled."
0x1d5ed  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1d5f2  throw
0x1d5f3  ldarg.0
0x1d5f4  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.LiteralNode::m_dataType
0x1d5f9  ldc.i4.7
0x1d5fa  beq.s    loc_1D607
0x1d5fc  ldstr    aDataTypeMustBe// "Data type must be EntityKey."
0x1d601  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1d606  throw
0x1d607  ret
```
