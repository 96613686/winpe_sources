# Microsoft.ReportingServices.Modeling.FunctionNode::ProcessFunctionEntityKeyTargets

- ea: `0x1a9a0`
- end: `0x1aa02`
- name: `Microsoft.ReportingServices.Modeling.FunctionNode::ProcessFunctionEntityKeyTargets`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a5f0`

## callees

- `0x84f0`
- `0x97d0`
- `0x19cd0`
- `0x19d40`
- `0x1a9a0`
- `0x1aa10`

## string_xrefs

- `0x1a9c3`: `m_arguments must be compiled if ctx.ShouldPersist is true.`

## pseudocode

```c

```

## disassembly

```asm
0x1a9a0  ldarg.3
0x1a9a1  brtrue.s loc_1A9AE
0x1a9a3  ldstr    aEntitykeytarge_0// "entityKeyTarget is null."
0x1a9a8  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1a9ad  throw
0x1a9ae  ldarg.1
0x1a9af  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1a9b4  brfalse.s loc_1A9CE
0x1a9b6  ldarg.0
0x1a9b7  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a9bc  callvirt instance bool class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_IsReadOnly()
0x1a9c1  brtrue.s loc_1A9CE
0x1a9c3  ldstr    aMArgumentsMust// "m_arguments must be compiled if ctx.Sho"...
0x1a9c8  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1a9cd  throw
0x1a9ce  ldarg.0
0x1a9cf  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a9d4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x1a9d9  ldc.i4.1
0x1a9da  ble.s    loc_1A9E4
0x1a9dc  ldarg.0
0x1a9dd  ldarg.3
0x1a9de  ldarg.1
0x1a9df  call     instance void Microsoft.ReportingServices.Modeling.FunctionNode::SetEntityKeyTargetOnArguments(class Microsoft.ReportingServices.Modeling.IQueryEntity entityKeyTarget, class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x1a9e4  ldarga.s 2
0x1a9e6  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x1a9eb  ldc.i4.7
0x1a9ec  beq.s    loc_1A9F8
0x1a9ee  ldarga.s 2
0x1a9f0  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x1a9f5  ldc.i4.8
0x1a9f6  bne.un.s loc_1AA00
0x1a9f8  ldarga.s 2
0x1a9fa  ldarg.3
0x1a9fb  call     instance void Microsoft.ReportingServices.Modeling.ResultType::SetEntityKeyTarget(class Microsoft.ReportingServices.Modeling.IQueryEntity entityKeyTarget)
0x1aa00  ldarg.2
0x1aa01  ret
```
