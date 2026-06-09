# Microsoft.ReportingServices.Diagnostics.Encryption::Encrypt

- ea: `0x9cc0`
- end: `0x9cce`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::Encrypt`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d10`
- `0x9d90`

## callees

- `0x9c40`
- `0x9c80`

## pseudocode

```c

```

## disassembly

```asm
0x9cc0  ldarg.0
0x9cc1  call     instance void Microsoft.ReportingServices.Diagnostics.Encryption::CheckEncryptionOnce()
0x9cc6  ldarg.0
0x9cc7  ldarg.1
0x9cc8  callvirt instance unsigned int8[] Microsoft.ReportingServices.Diagnostics.Encryption::EncryptInternal(unsigned int8[] data)
0x9ccd  ret
```
