# Microsoft.ReportingServices.Portal.Services.Configuration.LegacyCrypto::.ctor

- ea: `0x130d0`
- end: `0x130ec`
- name: `Microsoft.ReportingServices.Portal.Services.Configuration.LegacyCrypto::.ctor`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x130d0`

## string_xrefs

- `0x130d9`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x130d0  ldarg.0
0x130d1  call     instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::.ctor()
0x130d6  ldarg.1
0x130d7  brtrue.s loc_130E4
0x130d9  ldstr    aService// "service"
0x130de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x130e3  throw
0x130e4  ldarg.0
0x130e5  ldarg.1
0x130e6  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService Microsoft.ReportingServices.Portal.Services.Configuration.LegacyCrypto::_service
0x130eb  ret
```
