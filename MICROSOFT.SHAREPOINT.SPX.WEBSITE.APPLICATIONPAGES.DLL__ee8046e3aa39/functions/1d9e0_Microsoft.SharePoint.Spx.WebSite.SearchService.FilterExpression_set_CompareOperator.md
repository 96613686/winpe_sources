# Microsoft.SharePoint.Spx.WebSite.SearchService.FilterExpression::set_CompareOperator

- ea: `0x1d9e0`
- end: `0x1da0b`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.FilterExpression::set_CompareOperator`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1d970`
- `0x1d9e0`

## string_xrefs

- `0x1da00`: `CompareOperator`

## pseudocode

```c

```

## disassembly

```asm
0x1d9e0  ldarg.0
0x1d9e1  ldfld    valuetype Microsoft.SharePoint.Spx.WebSite.SearchService.CompareOperator Microsoft.SharePoint.Spx.WebSite.SearchService.FilterExpression::CompareOperatorField
0x1d9e6  box      Microsoft.SharePoint.Spx.WebSite.SearchService.CompareOperator
0x1d9eb  ldarg.1
0x1d9ec  box      Microsoft.SharePoint.Spx.WebSite.SearchService.CompareOperator
0x1d9f1  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1d9f6  brtrue.s loc_1DA0A
0x1d9f8  ldarg.0
0x1d9f9  ldarg.1
0x1d9fa  stfld    valuetype Microsoft.SharePoint.Spx.WebSite.SearchService.CompareOperator Microsoft.SharePoint.Spx.WebSite.SearchService.FilterExpression::CompareOperatorField
0x1d9ff  ldarg.0
0x1da00  ldstr    aCompareoperato// "CompareOperator"
0x1da05  call     instance void Microsoft.SharePoint.Spx.WebSite.SearchService.FilterExpressionBase::RaisePropertyChanged(string propertyName)
0x1da0a  ret
```
