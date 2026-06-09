# Microsoft.ReportingServices.Modeling.Parameter::CreateReplacementExpression

- ea: `0x22f40`
- end: `0x23109`
- name: `Microsoft.ReportingServices.Modeling.Parameter::CreateReplacementExpression`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c1a0`
- `0x23f50`

## callees

- `0x8e0`
- `0x85a0`
- `0x97d0`
- `0x9cf0`
- `0x186b0`
- `0x18890`
- `0x189b0`
- `0x1c4c0`
- `0x1cae0`
- `0x1cc80`
- `0x1ccc0`
- `0x1dbd0`
- `0x22f10`
- `0x22f40`
- `0x25310`
- `0x25330`
- `0x25350`
- `0x25360`
- `0x25b70`

## string_xrefs

- `0x22f5b`: `Parameter is not compiled`
- `0x22fe0`: `m_defaultValueExpr cardinality mismatch for compiled parameter`

## pseudocode

```c

```

## disassembly

```asm
0x22f40  ldarg.1
0x22f41  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Modeling.CompilationContext::get_ParameterValues()
0x22f46  brtrue.s loc_22F53
0x22f48  ldstr    aCtxParameterva// "ctx.ParameterValues is null"
0x22f4d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x22f52  throw
0x22f53  ldarg.0
0x22f54  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x22f59  brtrue.s loc_22F66
0x22f5b  ldstr    aParameterIsNot// "Parameter is not compiled"
0x22f60  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x22f65  throw
0x22f66  ldarg.1
0x22f67  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Modeling.CompilationContext::get_ParameterValues()
0x22f6c  ldarg.0
0x22f6d  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x22f72  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x22f77  brtrue   loc_2301B
0x22f7c  ldarg.0
0x22f7d  ldfld    bool Microsoft.ReportingServices.Modeling.Parameter::m_compiledExprIsValid
0x22f82  brfalse  loc_23019
0x22f87  ldarg.0
0x22f88  ldarg.0
0x22f89  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22f8e  call     instance bool Microsoft.ReportingServices.Modeling.Parameter::CheckDefaultValue(class Microsoft.ReportingServices.Modeling.Expression expr)
0x22f93  brtrue.s loc_22FB9
0x22f95  ldstr    aMDefaultvaluee// "m_defaultValueExpr is invalid '{0}'"
0x22f9a  ldc.i4.1
0x22f9b  newarr   [mscorlib]System.Object
0x22fa0  dup
0x22fa1  ldc.i4.0
0x22fa2  ldarg.0
0x22fa3  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22fa8  callvirt instance string [mscorlib]System.Object::ToString()
0x22fad  stelem.ref
0x22fae  call     string Microsoft.ReportingServices.Common.StringUtil::FormatInvariant(string format, object[] args)
0x22fb3  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x22fb8  throw
0x22fb9  ldarg.0
0x22fba  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22fbf  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsLiteral()
0x22fc4  brfalse.s loc_2300D
0x22fc6  ldarg.0
0x22fc7  ldfld    valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.Parameter::m_cardinality
0x22fcc  brtrue.s loc_22FF7
0x22fce  ldarg.0
0x22fcf  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22fd4  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsLiteral()
0x22fd9  callvirt instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.LiteralNode::get_Cardinality()
0x22fde  brfalse.s loc_22FEB
0x22fe0  ldstr    aMDefaultvaluee_0// "m_defaultValueExpr cardinality mismatch"...
0x22fe5  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x22fea  throw
0x22feb  ldarg.0
0x22fec  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22ff1  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Expression::Clone()
0x22ff6  ret
0x22ff7  ldarg.0
0x22ff8  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22ffd  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsLiteral()
0x23002  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.LiteralNode::ToSet()
0x23007  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x2300c  ret
0x2300d  ldarg.0
0x2300e  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x23013  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Expression::Clone()
0x23018  ret
0x23019  ldnull
0x2301a  ret
0x2301b  ldarg.1
0x2301c  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Modeling.CompilationContext::get_ParameterValues()
0x23021  ldarg.0
0x23022  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x23027  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x2302c  stloc.0
0x2302d  ldloc.0
0x2302e  brfalse.s loc_23038
0x23030  ldloc.0
0x23031  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x23036  bne.un.s loc_23060
0x23038  ldarg.0
0x23039  ldfld    bool Microsoft.ReportingServices.Modeling.Parameter::m_nullable
0x2303e  brtrue.s loc_23055
0x23040  ldarg.1
0x23041  ldc.i4.s 0x6E
0x23043  ldarg.0
0x23044  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x23049  call     string Microsoft.ReportingServices.Modeling.SRErrors::NullParameterValue(string parameterName)
0x2304e  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x23053  ldnull
0x23054  ret
0x23055  newobj   instance void Microsoft.ReportingServices.Modeling.NullNode::.ctor()
0x2305a  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x2305f  ret
0x23060  ldloc.0
0x23061  isinst   [mscorlib]System.Collections.IList
0x23066  brfalse.s loc_230B9
0x23068  ldarg.0
0x23069  ldfld    valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.Parameter::m_cardinality
0x2306e  ldc.i4.1
0x2306f  beq.s    loc_23086
0x23071  ldarg.1
0x23072  ldc.i4.s 0x6D
0x23074  ldarg.0
0x23075  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x2307a  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidParameterValueCardinality(string parameterName)
0x2307f  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x23084  ldnull
0x23085  ret
0x23086  ldloc.0
0x23087  castclass [mscorlib]System.Collections.IList
0x2308c  ldarg.0
0x2308d  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.Parameter::m_dataType
0x23092  call     class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.LiteralNode::FromObjectList(class [mscorlib]System.Collections.IList valueList, valuetype Microsoft.ReportingServices.Modeling.DataType dataType)
0x23097  dup
0x23098  brtrue.s loc_230B3
0x2309a  ldarg.1
0x2309b  ldc.i4.s 0x6C
0x2309d  ldarg.0
0x2309e  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x230a3  ldarg.0
0x230a4  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.Parameter::m_dataType
0x230a9  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidParameterValueType_MultipleValues(string parameterName, valuetype Microsoft.ReportingServices.Modeling.DataType dataType)
0x230ae  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x230b3  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x230b8  ret
0x230b9  ldarg.0
0x230ba  ldfld    valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.Parameter::m_cardinality
0x230bf  brtrue.s loc_230D0
0x230c1  ldloc.0
0x230c2  ldarg.0
0x230c3  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.Parameter::m_dataType
0x230c8  call     class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.LiteralNode::FromObject(object value, valuetype Microsoft.ReportingServices.Modeling.DataType dataType)
0x230cd  stloc.1
0x230ce  br.s     loc_230E6
0x230d0  ldc.i4.1
0x230d1  newarr   [mscorlib]System.Object
0x230d6  dup
0x230d7  ldc.i4.0
0x230d8  ldloc.0
0x230d9  stelem.ref
0x230da  ldarg.0
0x230db  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.Parameter::m_dataType
0x230e0  call     class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.LiteralNode::FromObjectList(class [mscorlib]System.Collections.IList valueList, valuetype Microsoft.ReportingServices.Modeling.DataType dataType)
0x230e5  stloc.1
0x230e6  ldloc.1
0x230e7  brtrue.s loc_23102
0x230e9  ldarg.1
0x230ea  ldc.i4.s 0x6C
0x230ec  ldarg.0
0x230ed  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x230f2  ldarg.0
0x230f3  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.Parameter::m_dataType
0x230f8  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidParameterValueType(string parameterName, valuetype Microsoft.ReportingServices.Modeling.DataType dataType)
0x230fd  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x23102  ldloc.1
0x23103  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x23108  ret
```
