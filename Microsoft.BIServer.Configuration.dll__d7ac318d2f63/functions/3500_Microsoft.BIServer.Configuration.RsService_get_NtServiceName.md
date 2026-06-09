# Microsoft.BIServer.Configuration.RsService::get_NtServiceName

- ea: `0x3500`
- end: `0x3515`
- name: `Microsoft.BIServer.Configuration.RsService::get_NtServiceName`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x32c0`

## callees

- `0x3500`
- `0x3520`

## pseudocode

```c

```

## disassembly

```asm
0x3500  ldsfld   string Microsoft.BIServer.Configuration.RsService::_ntServiceName
0x3505  dup
0x3506  brtrue.s loc_3514
0x3508  pop
0x3509  call     string Microsoft.BIServer.Configuration.RsService::GetLocalizedNtService()
0x350e  dup
0x350f  stsfld   string Microsoft.BIServer.Configuration.RsService::_ntServiceName
0x3514  ret
```
