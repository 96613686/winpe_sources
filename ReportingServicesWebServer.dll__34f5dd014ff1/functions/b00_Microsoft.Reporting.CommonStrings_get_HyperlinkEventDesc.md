# Microsoft.Reporting.CommonStrings::get_HyperlinkEventDesc

- ea: `0xb00`
- end: `0xb0b`
- name: `Microsoft.Reporting.CommonStrings::get_HyperlinkEventDesc`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3a3e0`

## string_xrefs

- `0xb00`: `HyperlinkEventDesc`

## pseudocode

```c

```

## disassembly

```asm
0xb00  ldstr    aHyperlinkevent// "HyperlinkEventDesc"
0xb05  call     string Keys::GetString(string key)
0xb0a  ret
```
