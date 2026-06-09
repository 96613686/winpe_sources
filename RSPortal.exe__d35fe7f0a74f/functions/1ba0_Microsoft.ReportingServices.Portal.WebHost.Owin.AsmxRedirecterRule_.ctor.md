# Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::.ctor

- ea: `0x1ba0`
- end: `0x1c1a`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::.ctor`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x38f0`

## string_xrefs

- `0x1bd9`: `/reportservice2010.asmx`
- `0x1bf1`: `/reportservice2006.asmx`
- `0x1c09`: `/reportservice2005.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x1ba0  ldarg.0
0x1ba1  call     instance void [mscorlib]System.Object::.ctor()
0x1ba6  ldarg.0
0x1ba7  ldarg.1
0x1ba8  stfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::_serverConfiguration
0x1bad  ldarg.0
0x1bae  ldc.i4.4
0x1baf  newarr   [mscorlib]System.String
0x1bb4  dup
0x1bb5  ldc.i4.0
0x1bb6  ldarg.0
0x1bb7  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::_serverConfiguration
0x1bbc  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x1bc1  ldstr    aReportexecutio// "/reportexecution2005.asmx"
0x1bc6  call     string [mscorlib]System.String::Concat(string, string)
0x1bcb  stelem.ref
0x1bcc  dup
0x1bcd  ldc.i4.1
0x1bce  ldarg.0
0x1bcf  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::_serverConfiguration
0x1bd4  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x1bd9  ldstr    aReportservice2// "/reportservice2010.asmx"
0x1bde  call     string [mscorlib]System.String::Concat(string, string)
0x1be3  stelem.ref
0x1be4  dup
0x1be5  ldc.i4.2
0x1be6  ldarg.0
0x1be7  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::_serverConfiguration
0x1bec  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x1bf1  ldstr    aReportservice2_0// "/reportservice2006.asmx"
0x1bf6  call     string [mscorlib]System.String::Concat(string, string)
0x1bfb  stelem.ref
0x1bfc  dup
0x1bfd  ldc.i4.3
0x1bfe  ldarg.0
0x1bff  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::_serverConfiguration
0x1c04  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x1c09  ldstr    aReportservice2_1// "/reportservice2005.asmx"
0x1c0e  call     string [mscorlib]System.String::Concat(string, string)
0x1c13  stelem.ref
0x1c14  stfld    string[] Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::KnownAsmxFilePaths
0x1c19  ret
```
