# Microsoft.ReportingServices.Modeling.Expression::CloneFor

- ea: `0x19480`
- end: `0x194ea`
- name: `Microsoft.ReportingServices.Modeling.Expression::CloneFor`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0xfda0`
- `0x194f0`

## callees

- `0x97d0`
- `0x9cf0`
- `0x9d30`
- `0x9eb0`
- `0x9ee0`
- `0x186f0`
- `0x18800`
- `0x19480`
- `0x1a1c0`
- `0x1e590`

## string_xrefs

- `0x19488`: `Expression is not compiled`

## pseudocode

```c

```

## disassembly

```asm
0x19480  ldarg.0
0x19481  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x19486  brtrue.s loc_19493
0x19488  ldstr    aExpressionIsNo// "Expression is not compiled"
0x1948d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x19492  throw
0x19493  ldarg.0
0x19494  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.Expression::m_path
0x19499  ldarg.1
0x1949a  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.ExpressionPath::CloneFor(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0x1949f  stloc.0
0x194a0  ldloc.0
0x194a1  brtrue.s loc_194A5
0x194a3  ldnull
0x194a4  ret
0x194a5  ldarg.0
0x194a6  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::m_node
0x194ab  ldarg.1
0x194ac  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.ExpressionNode::CloneFor(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0x194b1  stloc.1
0x194b2  ldloc.1
0x194b3  brtrue.s loc_194B7
0x194b5  ldnull
0x194b6  ret
0x194b7  ldloc.1
0x194b8  ldloc.0
0x194b9  ldc.i4.0
0x194ba  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node, class Microsoft.ReportingServices.Modeling.ExpressionPath path, bool clonePath)
0x194bf  dup
0x194c0  ldarg.0
0x194c1  ldfld    string Microsoft.ReportingServices.Modeling.Expression::m_name
0x194c6  callvirt instance void Microsoft.ReportingServices.Modeling.Expression::set_Name(string value)
0x194cb  dup
0x194cc  ldarg.0
0x194cd  call     instance class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::get_CustomProperties()
0x194d2  callvirt instance void Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::set_CustomProperties(class Microsoft.ReportingServices.Modeling.CustomPropertyCollection value)
0x194d7  dup
0x194d8  ldarg.0
0x194d9  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::m_compiledResultType
0x194de  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::m_compiledResultType
0x194e3  dup
0x194e4  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingObject::SetCompiledIndicator()
0x194e9  ret
```
