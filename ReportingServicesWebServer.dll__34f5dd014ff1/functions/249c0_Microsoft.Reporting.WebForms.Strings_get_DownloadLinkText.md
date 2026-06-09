# Microsoft.Reporting.WebForms.Strings::get_DownloadLinkText

- ea: `0x249c0`
- end: `0x249cb`
- name: `Microsoft.Reporting.WebForms.Strings::get_DownloadLinkText`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4eb0`

## callees

- `0x3b900`

## string_xrefs

- `0x249c0`: `DownloadLinkText`

## pseudocode

```c

```

## disassembly

```asm
0x249c0  ldstr    aDownloadlinkte// "DownloadLinkText"
0x249c5  call     string Keys::GetString(string key)
0x249ca  ret
```
