# Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::.ctor

- ea: `0x28c0`
- end: `0x28e4`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::.ctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x28c0`
- `0x2900`
- `0x29d0`

## pseudocode

```c

```

## disassembly

```asm
0x28c0  ldarg.0
0x28c1  call     instance void [mscorlib]System.Object::.ctor()
0x28c6  ldarg.0
0x28c7  ldarg.1
0x28c8  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::ParseCredential(string credentialStr)
0x28cd  ldarg.0
0x28ce  ldarg.2
0x28cf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x28d4  brtrue.s loc_28D9
0x28d6  ldarg.2
0x28d7  br.s     loc_28DE
0x28d9  ldstr    asc_5380// "."
0x28de  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::set_DefaultDomain(string value)
0x28e3  ret
```
