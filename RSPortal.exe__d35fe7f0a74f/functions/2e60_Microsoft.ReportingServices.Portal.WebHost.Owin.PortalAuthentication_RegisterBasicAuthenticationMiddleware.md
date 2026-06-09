# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalAuthentication::RegisterBasicAuthenticationMiddleware

- ea: `0x2e60`
- end: `0x2e8c`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalAuthentication::RegisterBasicAuthenticationMiddleware`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2e60`

## pseudocode

```c

```

## disassembly

```asm
0x2e60  ldarg.1
0x2e61  callvirt instance valuetype [System]System.Net.AuthenticationSchemes [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_AuthenticationSchemes()
0x2e66  stloc.0
0x2e67  ldloc.0
0x2e68  box      [System]System.Net.AuthenticationSchemes
0x2e6d  ldc.i4.8
0x2e6e  box      [System]System.Net.AuthenticationSchemes
0x2e73  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x2e78  brfalse.s loc_2E8B
0x2e7a  ldarg.0
0x2e7b  ldc.i4.1
0x2e7c  newarr   [mscorlib]System.Object
0x2e81  dup
0x2e82  ldc.i4.0
0x2e83  ldarg.1
0x2e84  stelem.ref
0x2e85  call     T0x2B00000D
0x2e8a  pop
0x2e8b  ret
```
