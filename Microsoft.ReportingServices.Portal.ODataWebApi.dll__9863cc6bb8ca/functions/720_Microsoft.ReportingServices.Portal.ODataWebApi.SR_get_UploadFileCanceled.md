# Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_UploadFileCanceled

- ea: `0x720`
- end: `0x72b`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_UploadFileCanceled`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6490`

## callees

- `0xd270`

## pseudocode

```c

```

## disassembly

```asm
0x720  ldstr    aUploadfilecanc// "UploadFileCanceled"
0x725  call     string Keys::GetString(string key)
0x72a  ret
```
