# Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::CouldNotWriteFile

- ea: `0x100`
- end: `0x10d`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::CouldNotWriteFile`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x2a0`

## callees

- `0x3ef0`

## string_xrefs

- `0x100`: `CouldNotWriteFile`

## pseudocode

```c

```

## disassembly

```asm
0x100  ldstr    aCouldnotwritef// "CouldNotWriteFile"
0x105  ldarg.0
0x106  ldarg.1
0x107  call     string Keys::GetString(string key, object arg0, object arg1)
0x10c  ret
```
