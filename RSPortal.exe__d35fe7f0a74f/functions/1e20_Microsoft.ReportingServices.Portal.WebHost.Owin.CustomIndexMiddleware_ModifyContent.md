# Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::ModifyContent

- ea: `0x1e20`
- end: `0x1e63`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::ModifyContent`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cc0`

## pseudocode

```c

```

## disassembly

```asm
0x1e20  ldarg.1
0x1e21  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x1e26  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x1e2b  ldstr    aBaseHref0// "<base href=\"/{0}/\" >"
0x1e30  ldarg.0
0x1e31  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::_serverConfiguration
0x1e36  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x1e3b  call     string [mscorlib]System.String::Format(string, object)
0x1e40  ldstr    asc_5DD8// "//"
0x1e45  ldstr    asc_571A// "/"
0x1e4a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1e4f  stloc.0
0x1e50  dup
0x1e51  ldstr    aInjectBasehref// "<!--Inject:BaseHref-->"
0x1e56  ldloc.0
0x1e57  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x1e5c  pop
0x1e5d  callvirt instance string [mscorlib]System.Object::ToString()
0x1e62  ret
```
