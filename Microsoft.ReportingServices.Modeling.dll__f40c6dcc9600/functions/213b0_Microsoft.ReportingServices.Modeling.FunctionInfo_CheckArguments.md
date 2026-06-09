# Microsoft.ReportingServices.Modeling.FunctionInfo::CheckArguments

- ea: `0x213b0`
- end: `0x2170b`
- name: `Microsoft.ReportingServices.Modeling.FunctionInfo::CheckArguments`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x212d0`

## callees

- `0x8f0`
- `0x18820`
- `0x18830`
- `0x18890`
- `0x18a50`
- `0x19cd0`
- `0x19d10`
- `0x1a090`
- `0x1c4b0`
- `0x1c4c0`
- `0x1c710`
- `0x210c0`
- `0x21120`
- `0x21130`
- `0x21370`
- `0x213b0`
- `0x21710`
- `0x24ea0`
- `0x24ec0`
- `0x24ef0`
- `0x24f30`
- `0x24f50`
- `0x24f70`
- `0x24f90`
- `0x24fb0`
- `0x25a90`
- `0x25b70`
- `0x25b80`

## pseudocode

```c

```

## disassembly

```asm
0x213b0  ldarg.0
0x213b1  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.FunctionInfo::get_Arguments()
0x213b6  stloc.0
0x213b7  ldarg.0
0x213b8  callvirt instance bool Microsoft.ReportingServices.Modeling.FunctionInfo::get_RepeatingArguments()
0x213bd  brfalse.s loc_213F9
0x213bf  ldarg.0
0x213c0  ldarg.1
0x213c1  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Count()
0x213c6  call     bool Microsoft.ReportingServices.Modeling.FunctionInfo::NumArgsMatch(class Microsoft.ReportingServices.Modeling.FunctionInfo fInfo, int32 numArguments)
0x213cb  brfalse.s loc_213F9
0x213cd  ldarg.1
0x213ce  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Count()
0x213d3  newarr   Microsoft.ReportingServices.Modeling.ResultType
0x213d8  stloc.2
0x213d9  ldc.i4.0
0x213da  stloc.3
0x213db  br.s     loc_213EE
0x213dd  ldloc.0
0x213de  ldloc.2
0x213df  ldloc.3
0x213e0  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::CopyTo(var<u1>[], !!T0)
0x213e5  ldloc.3
0x213e6  ldloc.0
0x213e7  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Count()
0x213ec  add
0x213ed  stloc.3
0x213ee  ldloc.3
0x213ef  ldarg.1
0x213f0  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Count()
0x213f5  blt.s    loc_213DD
0x213f7  ldloc.2
0x213f8  stloc.0
0x213f9  ldc.i4.0
0x213fa  stloc.1
0x213fb  ldarg.s  4
0x213fd  ldc.i4.0
0x213fe  stind.i4
0x213ff  ldarg.s  5
0x21401  ldc.i4.0
0x21402  stind.i1
0x21403  ldloc.0
0x21404  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Count()
0x21409  ldarg.1
0x2140a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Count()
0x2140f  beq.s    loc_2142F
0x21411  ldarg.3
0x21412  brfalse.s loc_2142D
0x21414  ldarg.3
0x21415  ldc.i4.s 0x4B
0x21417  ldarg.3
0x21418  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x2141d  ldarg.0
0x2141e  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x21423  call     string Microsoft.ReportingServices.Modeling.SRErrors::WrongNumberOfArguments(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName)
0x21428  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x2142d  ldc.i4.0
0x2142e  ret
0x2142f  ldc.i4.0
0x21430  stloc.s  4
0x21432  br       loc_216E9
0x21437  ldloc.0
0x21438  ldloc.s  4
0x2143a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Item(!!T0)
0x2143f  ldarg.1
0x21440  ldloc.s  4
0x21442  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Item(!!T0)
0x21447  call     valuetype ArgumentMatch Microsoft.ReportingServices.Modeling.FunctionInfo::CheckArgument(valuetype Microsoft.ReportingServices.Modeling.ResultType funcArg, valuetype Microsoft.ReportingServices.Modeling.ResultType inputArg)
0x2144c  stloc.s  5
0x2144e  ldloc.s  5
0x21450  ldc.i4.3
0x21451  and
0x21452  ldc.i4.3
0x21453  bne.un.s loc_21487
0x21455  ldloc.s  5
0x21457  ldc.i4.4
0x21458  and
0x21459  brfalse.s loc_21481
0x2145b  ldarg.3
0x2145c  brfalse.s loc_2147D
0x2145e  ldarg.3
0x2145f  ldc.i4.s 0x54
0x21461  ldarg.3
0x21462  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21467  ldarg.0
0x21468  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x2146d  ldloc.s  4
0x2146f  ldc.i4.1
0x21470  add
0x21471  call     string Microsoft.ReportingServices.Modeling.SRErrors::ImplicitDecimalCastToFloat(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, int32 argumentIndex)
0x21476  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedWarning(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x2147b  br.s     loc_21481
0x2147d  ldarg.s  5
0x2147f  ldc.i4.1
0x21480  stind.i1
0x21481  ldloc.1
0x21482  ldc.i4.1
0x21483  add
0x21484  stloc.1
0x21485  br.s     loc_214E4
0x21487  ldloc.s  5
0x21489  ldc.i4.1
0x2148a  and
0x2148b  brtrue.s loc_214BE
0x2148d  ldarg.3
0x2148e  brfalse.s loc_214BE
0x21490  ldarg.3
0x21491  ldc.i4.s 0x4C
0x21493  ldarg.3
0x21494  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21499  ldarg.0
0x2149a  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x2149f  ldloc.s  4
0x214a1  ldc.i4.1
0x214a2  add
0x214a3  ldarg.1
0x214a4  ldloc.s  4
0x214a6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Item(!!T0)
0x214ab  stloc.s  6
0x214ad  ldloca.s 6
0x214af  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x214b4  call     string Microsoft.ReportingServices.Modeling.SRErrors::ArgumentDataTypeMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, int32 argumentIndex, valuetype Microsoft.ReportingServices.Modeling.DataType inputDataType)
0x214b9  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x214be  ldloc.s  5
0x214c0  ldc.i4.2
0x214c1  and
0x214c2  brtrue.s loc_214E4
0x214c4  ldarg.3
0x214c5  brfalse.s loc_214E4
0x214c7  ldarg.3
0x214c8  ldc.i4.s 0x4D
0x214ca  ldarg.3
0x214cb  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x214d0  ldarg.0
0x214d1  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x214d6  ldloc.s  4
0x214d8  ldc.i4.1
0x214d9  add
0x214da  call     string Microsoft.ReportingServices.Modeling.SRErrors::ArgumentCardinalityMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, int32 argumentIndex)
0x214df  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x214e4  ldloc.s  5
0x214e6  ldc.i4.1
0x214e7  and
0x214e8  brfalse.s loc_21503
0x214ea  ldloc.s  4
0x214ec  ldc.i4.s 0x18
0x214ee  bge.s    loc_21503
0x214f0  ldarg.s  4
0x214f2  ldarg.s  4
0x214f4  ldind.i4
0x214f5  ldc.i4.1
0x214f6  ldc.i4.s 0x18
0x214f8  ldloc.s  4
0x214fa  sub
0x214fb  ldc.i4.1
0x214fc  sub
0x214fd  ldc.i4.s 0x1F
0x214ff  and
0x21500  shl
0x21501  add
0x21502  stind.i4
0x21503  ldarg.2
0x21504  brfalse  loc_216E3
0x21509  ldc.i4.0
0x2150a  stloc.s  7
0x2150c  ldarg.0
0x2150d  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x21512  ldc.i4.s 0x30
0x21514  beq.s    loc_21523
0x21516  ldarg.0
0x21517  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x2151c  ldc.i4.s 0x2F
0x2151e  bne.un   loc_215FF
0x21523  ldloc.s  4
0x21525  brtrue   loc_215FF
0x2152a  ldarg.2
0x2152b  ldloc.s  4
0x2152d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x21532  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsLiteral()
0x21537  brfalse.s loc_2154D
0x21539  ldarg.2
0x2153a  ldloc.s  4
0x2153c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x21541  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.Expression::get_Path()
0x21546  callvirt instance bool class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::get_IsEmpty()
0x2154b  brtrue.s loc_21575
0x2154d  ldarg.3
0x2154e  brfalse.s loc_2156D
0x21550  ldarg.3
0x21551  ldc.i4.s 0x50
0x21553  ldarg.3
0x21554  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21559  ldarg.0
0x2155a  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x2155f  ldloc.s  4
0x21561  ldc.i4.1
0x21562  add
0x21563  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidDateIntervalArgument(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, int32 argumentIndex)
0x21568  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x2156d  ldc.i4.1
0x2156e  stloc.s  7
0x21570  br       loc_215FF
0x21575  ldarg.2
0x21576  ldloc.s  4
0x21578  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x2157d  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsLiteral()
0x21582  callvirt instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.LiteralNode::get_DataType()
0x21587  brtrue.s loc_215FF
0x21589  ldarg.2
0x2158a  ldloc.s  4
0x2158c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x21591  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsLiteral()
0x21596  callvirt instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.LiteralNode::get_Cardinality()
0x2159b  brtrue.s loc_215FF
0x2159d  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.ReportingServices.Modeling.FunctionInfo::DateIntervals
0x215a2  ldarg.2
0x215a3  ldloc.s  4
0x215a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x215aa  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsLiteral()
0x215af  callvirt instance string Microsoft.ReportingServices.Modeling.LiteralNode::get_ValueAsString()
0x215b4  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::Contains(var<u1>)
0x215b9  brtrue.s loc_215FF
0x215bb  ldarg.3
0x215bc  brfalse.s loc_215FC
0x215be  ldarg.3
0x215bf  ldc.i4.s 0x51
0x215c1  ldarg.3
0x215c2  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x215c7  ldarg.0
0x215c8  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x215cd  ldloc.s  4
0x215cf  ldc.i4.1
0x215d0  add
0x215d1  ldarg.2
0x215d2  ldloc.s  4
0x215d4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x215d9  callvirt instance class Microsoft.ReportingServices.Modeling.LiteralNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsLiteral()
0x215de  callvirt instance string Microsoft.ReportingServices.Modeling.LiteralNode::get_ValueAsString()
0x215e3  ldstr    asc_41A14// ", "
0x215e8  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.ReportingServices.Modeling.FunctionInfo::DateIntervals
0x215ed  call     string Microsoft.ReportingServices.Common.StringUtil::Join(string separator, class [mscorlib]System.Collections.Generic.IList`1<string> strings)
0x215f2  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidDateIntervalValue(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, int32 argumentIndex, string actualValue, string expectedValues)
0x215f7  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x215fc  ldc.i4.1
0x215fd  stloc.s  7
0x215ff  ldarg.0
0x21600  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x21605  ldc.i4.s 0x3D
0x21607  bne.un   loc_21694
0x2160c  ldloc.s  4
0x2160e  ldc.i4.1
0x2160f  bne.un   loc_21694
0x21614  ldarg.2
0x21615  ldloc.s  4
0x21617  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x2161c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::TryGetResultType()
0x21621  stloc.s  8
0x21623  ldarg.2
0x21624  ldloc.s  4
0x21626  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x2162b  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::get_Node()
0x21630  callvirt instance bool Microsoft.ReportingServices.Modeling.ExpressionNode::get_IsConstantValue()
0x21635  brfalse.s loc_21658
0x21637  ldloca.s 8
0x21639  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x2163e  brfalse.s loc_21655
0x21640  ldloca.s 8
0x21642  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Value()
0x21647  stloc.s  6
0x21649  ldloca.s 6
0x2164b  call     instance bool Microsoft.ReportingServices.Modeling.ResultType::get_Nullable()
0x21650  ldc.i4.0
0x21651  ceq
0x21653  br.s     loc_21659
0x21655  ldc.i4.1
0x21656  br.s     loc_21659
0x21658  ldc.i4.0
0x21659  brfalse.s loc_2166F
0x2165b  ldarg.2
0x2165c  ldloc.s  4
0x2165e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x21663  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.Expression::get_Path()
0x21668  callvirt instance bool class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::get_IsEmpty()
0x2166d  brtrue.s loc_216DB
0x2166f  ldarg.3
0x21670  brfalse.s loc_2168F
0x21672  ldarg.3
0x21673  ldc.i4.s 0x52
0x21675  ldarg.3
0x21676  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x2167b  ldarg.0
0x2167c  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x21681  ldloc.s  4
0x21683  ldc.i4.1
0x21684  add
0x21685  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidInSetArgument(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, int32 argumentIndex)
0x2168a  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x2168f  ldc.i4.1
0x21690  stloc.s  7
0x21692  br.s     loc_216DB
  ... truncated ...
```
