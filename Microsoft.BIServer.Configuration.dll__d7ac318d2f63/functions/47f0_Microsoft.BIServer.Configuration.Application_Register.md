# Microsoft.BIServer.Configuration.Application::Register

- ea: `0x47f0`
- end: `0x480d`
- name: `Microsoft.BIServer.Configuration.Application::Register`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3670`

## callees

- `0x4750`
- `0x4900`
- `0x4960`
- `0x65e0`

## pseudocode

```c

```

## disassembly

```asm
0x47f0  ldarg.1
0x47f1  callvirt instance string Microsoft.BIServer.Configuration.URL::get_UrlString()
0x47f6  ldarg.0
0x47f7  call     instance string Microsoft.BIServer.Configuration.Application::get_VirtualDirectory()
0x47fc  call     string [mscorlib]System.String::Concat(string, string)
0x4801  ldarg.1
0x4802  callvirt instance string Microsoft.BIServer.Configuration.URL::get_AccountSecurityDescriptor()
0x4807  call     void Microsoft.BIServer.Configuration.Http.UrlReservationManager::ReserveAndDeleteIfExists(string url, string securityDescriptor)
0x480c  ret
```
