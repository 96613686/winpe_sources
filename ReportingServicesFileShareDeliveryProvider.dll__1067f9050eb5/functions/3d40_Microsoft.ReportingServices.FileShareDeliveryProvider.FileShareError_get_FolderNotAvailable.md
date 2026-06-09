# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_FolderNotAvailable

- ea: `0x3d40`
- end: `0x3d4b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_FolderNotAvailable`
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
0x3d40  ldstr    aFoldernotavail// "FolderNotAvailable"
0x3d45  call     string Keys::GetString(string key)
0x3d4a  ret
```
