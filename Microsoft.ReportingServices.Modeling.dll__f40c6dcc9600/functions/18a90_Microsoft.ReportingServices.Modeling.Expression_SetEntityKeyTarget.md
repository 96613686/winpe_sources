# Microsoft.ReportingServices.Modeling.Expression::SetEntityKeyTarget

- ea: `0x18a90`
- end: `0x18ad1`
- name: `Microsoft.ReportingServices.Modeling.Expression::SetEntityKeyTarget`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1aa10`

## callees

- `0x97d0`
- `0x9cf0`
- `0x18a90`
- `0x19d40`
- `0x1a1a0`

## string_xrefs

- `0x18a98`: `SetEntityKeyTarget is called on a non-compiled expression.`

## pseudocode

```c

```

## disassembly

```asm
0x18a90  ldarg.0
0x18a91  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x18a96  brtrue.s loc_18AA3
0x18a98  ldstr    aSetentitykeyta// "SetEntityKeyTarget is called on a non-c"...
0x18a9d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x18aa2  throw
0x18aa3  ldarg.0
0x18aa4  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::m_compiledResultType
0x18aa9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Value()
0x18aae  stloc.0
0x18aaf  ldloca.s 0
0x18ab1  ldarg.1
0x18ab2  call     instance void Microsoft.ReportingServices.Modeling.ResultType::SetEntityKeyTarget(class Microsoft.ReportingServices.Modeling.IQueryEntity entityKeyTarget)
0x18ab7  ldarg.0
0x18ab8  ldloc.0
0x18ab9  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::.ctor(var<u1>)
0x18abe  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::m_compiledResultType
0x18ac3  ldarg.0
0x18ac4  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::m_node
0x18ac9  ldarg.1
0x18aca  ldarg.2
0x18acb  callvirt instance void Microsoft.ReportingServices.Modeling.ExpressionNode::SetEntityKeyTarget(class Microsoft.ReportingServices.Modeling.IQueryEntity entityKeyTarget, class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x18ad0  ret
```
