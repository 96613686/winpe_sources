# Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Register

- ea: `0x33c0`
- end: `0x33e0`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Register`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x38f0`

## callees

- `0x3410`

## pseudocode

```c

```

## disassembly

```asm
0x33c0  ldarg.0
0x33c1  ldc.i4.1
0x33c2  newarr   [mscorlib]System.Object
0x33c7  dup
0x33c8  ldc.i4.0
0x33c9  ldarg.1
0x33ca  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x33cf  ldarg.2
0x33d0  ldarg.3
0x33d1  ldarg.s  4
0x33d3  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::.ctor(string virtualRoot, string classicBasePath, string newBasePath, bool appendItemPath)
0x33d8  stelem.ref
0x33d9  call     T0x2B000010
0x33de  pop
0x33df  ret
```
