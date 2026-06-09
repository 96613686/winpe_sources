# Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::get_Domain

- ea: `0x2910`
- end: `0x2935`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::get_Domain`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x28f0`
- `0x2910`
- `0x2970`

## pseudocode

```c

```

## disassembly

```asm
0x2910  ldarg.0
0x2911  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::_domain
0x2916  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x291b  brfalse.s loc_292E
0x291d  ldarg.0
0x291e  call     instance bool Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::get_IsUsernameUPN()
0x2923  brtrue.s loc_292C
0x2925  ldarg.0
0x2926  call     instance string Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::get_DefaultDomain()
0x292b  ret
0x292c  ldnull
0x292d  ret
0x292e  ldarg.0
0x292f  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::_domain
0x2934  ret
```
