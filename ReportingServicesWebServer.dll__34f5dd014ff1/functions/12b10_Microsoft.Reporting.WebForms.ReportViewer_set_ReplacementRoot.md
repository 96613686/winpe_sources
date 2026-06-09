# Microsoft.Reporting.WebForms.ReportViewer::set_ReplacementRoot

- ea: `0x12b10`
- end: `0x12b25`
- name: `Microsoft.Reporting.WebForms.ReportViewer::set_ReplacementRoot`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x34050`

## callees

- `0x12050`
- `0x12af0`

## string_xrefs

- `0x12b11`: `ReplacementRoot`

## pseudocode

```c

```

## disassembly

```asm
0x12b10  ldarg.0
0x12b11  ldstr    aReplacementroo// "ReplacementRoot"
0x12b16  ldarg.0
0x12b17  call     instance string Microsoft.Reporting.WebForms.ReportViewer::get_ReplacementRoot()
0x12b1c  ldarg.1
0x12b1d  ldc.i4.2
0x12b1e  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::SetViewStateProperty(string viewStateKey, object oldValue, object newValue, valuetype Microsoft.Reporting.WebForms.UpdateGroup group)
0x12b23  pop
0x12b24  ret
```
