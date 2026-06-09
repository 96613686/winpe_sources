# Microsoft.ReportingServices.Library.RepLibRes::get_ParentDirectoryLink

- ea: `0x8420`
- end: `0x842b`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_ParentDirectoryLink`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9870`

## string_xrefs

- `0x8420`: `ParentDirectoryLink`

## pseudocode

```c

```

## disassembly

```asm
0x8420  ldstr    aParentdirector// "ParentDirectoryLink"
0x8425  call     string Keys::GetString(string key)
0x842a  ret
```
