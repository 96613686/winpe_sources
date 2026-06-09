# Microsoft.ReportingServices.Library.RepLibRes::get_TaskComment

- ea: `0x8260`
- end: `0x826b`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_TaskComment`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x63e0`

## callees

- `0x9870`

## string_xrefs

- `0x8260`: `TaskComment`

## pseudocode

```c

```

## disassembly

```asm
0x8260  ldstr    aTaskcomment// "TaskComment"
0x8265  call     string Keys::GetString(string key)
0x826a  ret
```
