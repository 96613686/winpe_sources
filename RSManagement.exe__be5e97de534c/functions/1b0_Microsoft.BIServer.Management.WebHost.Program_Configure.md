# Microsoft.BIServer.Management.WebHost.Program::Configure

- ea: `0x1b0`
- end: `0x1cf`
- name: `Microsoft.BIServer.Management.WebHost.Program::Configure`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x450`

## callees

- `0x1d0`
- `0x2f0`

## pseudocode

```c

```

## disassembly

```asm
0x1b0  ldarg.0
0x1b1  call     void Microsoft.BIServer.Management.WebHost.Program::EnableWindowsAuthentication(class [Owin]Owin.IAppBuilder appBuilder)
0x1b6  ldarg.0
0x1b7  call     T0x2B000001
0x1bc  call     T0x2B000002
0x1c1  pop
0x1c2  ldarg.0
0x1c3  call     class [System.Web.Http]System.Web.Http.HttpConfiguration Microsoft.BIServer.Management.WebHost.WebApiConfigFactory::CreateWebApiConfig()
0x1c8  call     class [Owin]Owin.IAppBuilder [System.Web.Http.Owin]Owin.WebApiAppBuilderExtensions::UseWebApi(class [Owin]Owin.IAppBuilder, class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x1cd  pop
0x1ce  ret
```
