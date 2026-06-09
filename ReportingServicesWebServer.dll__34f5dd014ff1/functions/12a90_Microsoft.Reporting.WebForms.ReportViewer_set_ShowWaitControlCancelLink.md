# Microsoft.Reporting.WebForms.ReportViewer::set_ShowWaitControlCancelLink

- ea: `0x12a90`
- end: `0x12ab0`
- name: `Microsoft.Reporting.WebForms.ReportViewer::set_ShowWaitControlCancelLink`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x12020`
- `0x12a80`

## string_xrefs

- `0x12a91`: `ShowWaitControlCancelLink`

## pseudocode

```c

```

## disassembly

```asm
0x12a90  ldarg.0
0x12a91  ldstr    aShowwaitcontro_0// "ShowWaitControlCancelLink"
0x12a96  ldarg.0
0x12a97  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_ShowWaitControlCancelLink()
0x12a9c  box      [mscorlib]System.Boolean
0x12aa1  ldarg.1
0x12aa2  box      [mscorlib]System.Boolean
0x12aa7  ldc.i4.s 0xE
0x12aa9  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::SetUnlockedViewStateProperty(string viewStateKey, object oldValue, object newValue, valuetype Microsoft.Reporting.WebForms.UpdateGroup updateGroup)
0x12aae  pop
0x12aaf  ret
```
