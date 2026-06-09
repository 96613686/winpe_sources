# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::DuplicateSetting

- ea: `0x3e40`
- end: `0x3e4c`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::DuplicateSetting`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`

## callees

- `0x42a0`

## pseudocode

```c

```

## disassembly

```asm
0x3e40  ldstr    aDuplicatesetti// "DuplicateSetting"
0x3e45  ldarg.0
0x3e46  call     string Keys::GetString(string key, object arg0)
0x3e4b  ret
```
