# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_OverrideOption

- ea: `0x3af0`
- end: `0x3afb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_OverrideOption`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x3af0  ldstr    aOverrideoption// "OverrideOption"
0x3af5  call     string Keys::GetString(string key)
0x3afa  ret
```
