# System.Web.UI.WebControls.Expressions.SearchExpression::CreateCallExpression

- ea: `0x27d80`
- end: `0x27e17`
- name: `System.Web.UI.WebControls.Expressions.SearchExpression::CreateCallExpression`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x27c80`

## callees

- `0x268c0`
- `0x27c00`
- `0x27c40`
- `0x27d80`

## string_xrefs

- `0x27d8e`: `ComparisonType`

## pseudocode

```c

```

## disassembly

```asm
0x27d80  ldarg.0
0x27d81  call     instance valuetype System.Web.UI.WebControls.Expressions.SearchType System.Web.UI.WebControls.Expressions.SearchExpression::get_SearchType()
0x27d86  brfalse.s loc_27D9A
0x27d88  ldarg.0
0x27d89  call     instance class [System.Web]System.Web.UI.StateBag System.Web.UI.WebControls.Expressions.DataSourceExpression::get_ViewState()
0x27d8e  ldstr    aComparisontype// "ComparisonType"
0x27d93  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x27d98  brtrue.s loc_27DCF
0x27d9a  ldarg.1
0x27d9b  ldarg.0
0x27d9c  call     instance valuetype System.Web.UI.WebControls.Expressions.SearchType System.Web.UI.WebControls.Expressions.SearchExpression::get_SearchType()
0x27da1  stloc.0
0x27da2  ldloca.s 0
0x27da4  constrained. System.Web.UI.WebControls.Expressions.SearchType
0x27daa  callvirt instance string [mscorlib]System.Object::ToString()
0x27daf  ldsfld   class [mscorlib]System.Type[] [mscorlib]System.Type::EmptyTypes
0x27db4  ldc.i4.1
0x27db5  newarr   [System.Core]System.Linq.Expressions.Expression
0x27dba  dup
0x27dbb  ldc.i4.0
0x27dbc  ldarg.2
0x27dbd  ldarg.1
0x27dbe  callvirt instance class [mscorlib]System.Type [System.Core]System.Linq.Expressions.Expression::get_Type()
0x27dc3  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x27dc8  stelem.ref
0x27dc9  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, string, class [mscorlib]System.Type[], class [System.Core]System.Linq.Expressions.Expression[])
0x27dce  ret
0x27dcf  ldarg.1
0x27dd0  ldarg.0
0x27dd1  call     instance valuetype System.Web.UI.WebControls.Expressions.SearchType System.Web.UI.WebControls.Expressions.SearchExpression::get_SearchType()
0x27dd6  stloc.0
0x27dd7  ldloca.s 0
0x27dd9  constrained. System.Web.UI.WebControls.Expressions.SearchType
0x27ddf  callvirt instance string [mscorlib]System.Object::ToString()
0x27de4  ldsfld   class [mscorlib]System.Type[] [mscorlib]System.Type::EmptyTypes
0x27de9  ldc.i4.2
0x27dea  newarr   [System.Core]System.Linq.Expressions.Expression
0x27def  dup
0x27df0  ldc.i4.0
0x27df1  ldarg.2
0x27df2  ldarg.1
0x27df3  callvirt instance class [mscorlib]System.Type [System.Core]System.Linq.Expressions.Expression::get_Type()
0x27df8  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x27dfd  stelem.ref
0x27dfe  dup
0x27dff  ldc.i4.1
0x27e00  ldarg.0
0x27e01  call     instance valuetype [mscorlib]System.StringComparison System.Web.UI.WebControls.Expressions.SearchExpression::get_ComparisonType()
0x27e06  box      [mscorlib]System.StringComparison
0x27e0b  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object)
0x27e10  stelem.ref
0x27e11  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, string, class [mscorlib]System.Type[], class [System.Core]System.Linq.Expressions.Expression[])
0x27e16  ret
```
