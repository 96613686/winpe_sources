# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::CouldNotWriteFile

- ea: `0x3df0`
- end: `0x3dfd`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::CouldNotWriteFile`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1270`

## callees

- `0x42c0`

## string_xrefs

- `0x3df0`: `CouldNotWriteFile`

## pseudocode

```c

```

## disassembly

```asm
0x3df0  ldstr    aCouldnotwritef// "CouldNotWriteFile"
0x3df5  ldarg.0
0x3df6  ldarg.1
0x3df7  call     string Keys::GetString(string key, object arg0, object arg1)
0x3dfc  ret
```
