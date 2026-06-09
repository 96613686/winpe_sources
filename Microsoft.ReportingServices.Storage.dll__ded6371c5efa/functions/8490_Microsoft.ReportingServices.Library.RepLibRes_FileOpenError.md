# Microsoft.ReportingServices.Library.RepLibRes::FileOpenError

- ea: `0x8490`
- end: `0x849d`
- name: `Microsoft.ReportingServices.Library.RepLibRes::FileOpenError`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x98b0`

## string_xrefs

- `0x8490`: `FileOpenError`

## pseudocode

```c

```

## disassembly

```asm
0x8490  ldstr    aFileopenerror// "FileOpenError"
0x8495  ldarg.0
0x8496  ldarg.1
0x8497  call     string Keys::GetString(string key, object arg0, object arg1)
0x849c  ret
```
