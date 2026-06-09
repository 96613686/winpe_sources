# Microsoft.ReportingServices.Diagnostics.ItemPathBase::SafeValue

- ea: `0x8bf0`
- end: `0x8bfc`
- name: `Microsoft.ReportingServices.Diagnostics.ItemPathBase::SafeValue`
- size: `12`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8c50`
- `0x8c70`
- `0x9290`
- `0x9440`

## callees

- `0x8b50`
- `0x8bf0`

## pseudocode

```c

```

## disassembly

```asm
0x8bf0  ldarg.0
0x8bf1  brtrue.s loc_8BF5
0x8bf3  ldnull
0x8bf4  ret
0x8bf5  ldarg.0
0x8bf6  callvirt instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x8bfb  ret
```
