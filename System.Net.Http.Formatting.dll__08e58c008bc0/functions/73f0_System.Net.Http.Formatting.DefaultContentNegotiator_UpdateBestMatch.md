# System.Net.Http.Formatting.DefaultContentNegotiator::UpdateBestMatch

- ea: `0x73f0`
- end: `0x740c`
- name: `System.Net.Http.Formatting.DefaultContentNegotiator::UpdateBestMatch`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x6ec0`

## callees

- `0x73f0`
- `0x8ec0`

## pseudocode

```c

```

## disassembly

```asm
0x73f0  ldarg.2
0x73f1  brtrue.s loc_73F5
0x73f3  ldarg.1
0x73f4  ret
0x73f5  ldarg.1
0x73f6  brfalse.s loc_740A
0x73f8  ldarg.2
0x73f9  callvirt instance float64 System.Net.Http.Formatting.MediaTypeFormatterMatch::get_Quality()
0x73fe  ldarg.1
0x73ff  callvirt instance float64 System.Net.Http.Formatting.MediaTypeFormatterMatch::get_Quality()
0x7404  bgt.s    loc_7408
0x7406  ldarg.1
0x7407  ret
0x7408  ldarg.2
0x7409  ret
0x740a  ldarg.2
0x740b  ret
```
