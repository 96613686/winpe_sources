# Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::.ctor_0

- ea: `0x12f80`
- end: `0x12fab`
- name: `Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::.ctor_0`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x13640`

## callees

- `0x12fc0`
- `0x12fe0`
- `0x13000`
- `0x13020`
- `0x13040`

## pseudocode

```c

```

## disassembly

```asm
0x12f80  ldarg.0
0x12f81  call     instance void [mscorlib]System.Object::.ctor()
0x12f86  ldarg.0
0x12f87  ldarg.1
0x12f88  call     instance void Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::set_ConnectionString(string value)
0x12f8d  ldarg.0
0x12f8e  ldarg.2
0x12f8f  call     instance void Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::set_WindowsUser(string value)
0x12f94  ldarg.0
0x12f95  ldarg.s  4
0x12f97  call     instance void Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::set_WindowsPassword(string value)
0x12f9c  ldarg.0
0x12f9d  ldarg.3
0x12f9e  call     instance void Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::set_WindowsDomain(string value)
0x12fa3  ldarg.0
0x12fa4  ldc.i4.1
0x12fa5  call     instance void Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::set_UseImpersonation(bool value)
0x12faa  ret
```
