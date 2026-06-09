# Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::GetRedirectUri

- ea: `0x1c50`
- end: `0x1c7c`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::GetRedirectUri`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1c50  ldarg.0
0x1c51  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::_serverConfiguration
0x1c56  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerVirtualDirectory()
0x1c5b  ldstr    asc_571A// "/"
0x1c60  ldarg.1
0x1c61  callvirt instance string[] [System]System.Uri::get_Segments()
0x1c66  call     T0x2B000007
0x1c6b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c70  ldc.i4.2
0x1c71  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x1c76  callvirt instance string [mscorlib]System.Object::ToString()
0x1c7b  ret
```
