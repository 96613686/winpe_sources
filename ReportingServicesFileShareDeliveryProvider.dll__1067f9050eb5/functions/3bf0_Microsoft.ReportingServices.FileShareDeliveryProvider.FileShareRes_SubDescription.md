# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::SubDescription

- ea: `0x3bf0`
- end: `0x3bfd`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::SubDescription`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2890`

## callees

- `0x41c0`

## pseudocode

```c

```

## disassembly

```asm
0x3bf0  ldstr    aSubdescription// "SubDescription"
0x3bf5  ldarg.0
0x3bf6  ldarg.1
0x3bf7  call     string Keys::GetString(string key, object arg0, object arg1)
0x3bfc  ret
```
