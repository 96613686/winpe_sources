# Microsoft.Reporting.WebForms.DatePicker::GetDivFocusElement

- ea: `0x1f5b0`
- end: `0x1f5cc`
- name: `Microsoft.Reporting.WebForms.DatePicker::GetDivFocusElement`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1f5d0`

## callees

- `0x1f560`
- `0x1f5b0`

## string_xrefs

- `0x1f5ba`: `MoveNext`
- `0x1f5c1`: `MovePrevious`

## pseudocode

```c

```

## disassembly

```asm
0x1f5b0  ldarg.0
0x1f5b1  ldarg.1
0x1f5b2  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivName(int32 offset)
0x1f5b7  ldarg.2
0x1f5b8  brtrue.s loc_1F5C1
0x1f5ba  ldstr    aMovenext// "MoveNext"
0x1f5bf  br.s     loc_1F5C6
0x1f5c1  ldstr    aMoveprevious// "MovePrevious"
0x1f5c6  call     string [mscorlib]System.String::Concat(string, string)
0x1f5cb  ret
```
