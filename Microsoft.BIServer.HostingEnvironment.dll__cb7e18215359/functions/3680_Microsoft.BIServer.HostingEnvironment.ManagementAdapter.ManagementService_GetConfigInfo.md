# Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetConfigInfo

- ea: `0x3680`
- end: `0x3696`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetConfigInfo`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6c10`

## string_xrefs

- `0x3680`: `{0}/api/v1.0/DBConfigInfo`

## pseudocode

```c

```

## disassembly

```asm
0x3680  ldstr    a0ApiV10Dbconfi// "{0}/api/v1.0/DBConfigInfo"
0x3685  ldarg.0
0x3686  ldfld    class [System]System.Uri Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::_managementUrl
0x368b  call     string [mscorlib]System.String::Format(string, object)
0x3690  newobj   instance void [System]System.Uri::.ctor(string)
0x3695  ret
```
