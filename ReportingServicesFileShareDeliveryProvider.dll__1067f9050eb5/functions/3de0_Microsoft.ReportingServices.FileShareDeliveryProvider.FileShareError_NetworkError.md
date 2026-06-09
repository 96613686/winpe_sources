# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::NetworkError

- ea: `0x3de0`
- end: `0x3dec`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::NetworkError`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1270`

## callees

- `0x42a0`

## pseudocode

```c

```

## disassembly

```asm
0x3de0  ldstr    aNetworkerror// "NetworkError"
0x3de5  ldarg.0
0x3de6  call     string Keys::GetString(string key, object arg0)
0x3deb  ret
```
