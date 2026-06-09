# System.Web.UI.WebControls.Expressions.SearchExpression::get_ComparisonType

- ea: `0x27c40`
- end: `0x27c5d`
- name: `System.Web.UI.WebControls.Expressions.SearchExpression::get_ComparisonType`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x27d80`

## callees

- `0x268c0`
- `0x27c40`

## string_xrefs

- `0x27c46`: `ComparisonType`

## pseudocode

```c

```

## disassembly

```asm
0x27c40  ldarg.0
0x27c41  call     instance class [System.Web]System.Web.UI.StateBag System.Web.UI.WebControls.Expressions.DataSourceExpression::get_ViewState()
0x27c46  ldstr    aComparisontype// "ComparisonType"
0x27c4b  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x27c50  stloc.0
0x27c51  ldloc.0
0x27c52  brtrue.s loc_27C56
0x27c54  ldc.i4.5
0x27c55  ret
0x27c56  ldloc.0
0x27c57  unbox.any [mscorlib]System.StringComparison
0x27c5c  ret
```
