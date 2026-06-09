# Microsoft.BIServer.Configuration.Http.UrlReservationManager::InitializeInputConfigInfo

- ea: `0x66e0`
- end: `0x670a`
- name: `Microsoft.BIServer.Configuration.Http.UrlReservationManager::InitializeInputConfigInfo`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x65e0`
- `0x6670`

## callees

- `0x7800`
- `0x7820`

## pseudocode

```c

```

## disassembly

```asm
0x66e0  ldloca.s 0
0x66e2  ldarg.0
0x66e3  call     instance void HTTP_SERVICE_CONFIG_URLACL_KEY::.ctor(string urlPrefix)
0x66e8  ldloca.s 1
0x66ea  ldarg.1
0x66eb  call     instance void HTTP_SERVICE_CONFIG_URLACL_PARAM::.ctor(string securityDescriptor)
0x66f0  ldloca.s 2
0x66f2  initobj  HTTP_SERVICE_CONFIG_URLACL_SET
0x66f8  ldloca.s 2
0x66fa  ldloc.0
0x66fb  stfld    valuetype HTTP_SERVICE_CONFIG_URLACL_KEY HTTP_SERVICE_CONFIG_URLACL_SET::KeyDesc
0x6700  ldloca.s 2
0x6702  ldloc.1
0x6703  stfld    valuetype HTTP_SERVICE_CONFIG_URLACL_PARAM HTTP_SERVICE_CONFIG_URLACL_SET::ParamDesc
0x6708  ldloc.2
0x6709  ret
```
