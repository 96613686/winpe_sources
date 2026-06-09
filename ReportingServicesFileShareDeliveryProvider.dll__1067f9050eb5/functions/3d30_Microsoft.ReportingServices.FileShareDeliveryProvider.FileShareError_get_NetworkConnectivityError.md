# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NetworkConnectivityError

- ea: `0x3d30`
- end: `0x3d3b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NetworkConnectivityError`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3d30  ldstr    aNetworkconnect// "NetworkConnectivityError"
0x3d35  call     string Keys::GetString(string key)
0x3d3a  ret
```
