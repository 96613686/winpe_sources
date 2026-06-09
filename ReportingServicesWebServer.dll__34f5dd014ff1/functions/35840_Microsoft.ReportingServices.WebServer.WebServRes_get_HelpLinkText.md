# Microsoft.ReportingServices.WebServer.WebServRes::get_HelpLinkText

- ea: `0x35840`
- end: `0x3584b`
- name: `Microsoft.ReportingServices.WebServer.WebServRes::get_HelpLinkText`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3c8d0`

## callees

- `0x3cd30`

## string_xrefs

- `0x35840`: `HelpLinkText`

## pseudocode

```c

```

## disassembly

```asm
0x35840  ldstr    aHelplinktext// "HelpLinkText"
0x35845  call     string Keys::GetString(string key)
0x3584a  ret
```
