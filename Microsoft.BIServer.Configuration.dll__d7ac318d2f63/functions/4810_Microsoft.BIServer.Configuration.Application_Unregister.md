# Microsoft.BIServer.Configuration.Application::Unregister

- ea: `0x4810`
- end: `0x482d`
- name: `Microsoft.BIServer.Configuration.Application::Unregister`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x36e0`

## callees

- `0x4750`
- `0x4900`
- `0x4960`
- `0x6670`

## pseudocode

```c

```

## disassembly

```asm
0x4810  ldarg.1
0x4811  callvirt instance string Microsoft.BIServer.Configuration.URL::get_UrlString()
0x4816  ldarg.0
0x4817  call     instance string Microsoft.BIServer.Configuration.Application::get_VirtualDirectory()
0x481c  call     string [mscorlib]System.String::Concat(string, string)
0x4821  ldarg.1
0x4822  callvirt instance string Microsoft.BIServer.Configuration.URL::get_AccountSecurityDescriptor()
0x4827  call     void Microsoft.BIServer.Configuration.Http.UrlReservationManager::DeleteIfExists(string url, string securityDescriptor)
0x482c  ret
```
