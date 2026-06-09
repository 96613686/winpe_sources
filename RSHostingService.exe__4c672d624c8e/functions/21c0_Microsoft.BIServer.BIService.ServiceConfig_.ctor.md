# Microsoft.BIServer.BIService.ServiceConfig::.ctor

- ea: `0x21c0`
- end: `0x2241`
- name: `Microsoft.BIServer.BIService.ServiceConfig::.ctor`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb10`
- `0xfb0`

## callees

- `0x21c0`
- `0x2280`
- `0x2370`

## string_xrefs

- `0x21da`: `Can't load config from missing file at [{0}]`
- `0x21ff`: `rsConfigFilePath`
- `0x2220`: `Exception occurred while parsing config file at [{0}]`

## pseudocode

```c

```

## disassembly

```asm
0x21c0  ldarg.0
0x21c1  call     instance void [mscorlib]System.Object::.ctor()
0x21c6  ldarg.0
0x21c7  ldarg.1
0x21c8  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x21cd  stfld    string Microsoft.BIServer.BIService.ServiceConfig::_serviceConfigFilePath
0x21d2  ldarg.1
0x21d3  call     bool [mscorlib]System.IO.File::Exists(string)
0x21d8  brtrue.s loc_21EB
0x21da  ldstr    aCanTLoadConfig// "Can't load config from missing file at "...
0x21df  ldarg.0
0x21e0  ldfld    string Microsoft.BIServer.BIService.ServiceConfig::_serviceConfigFilePath
0x21e5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x21ea  throw
0x21eb  nop
0x21ec  ldarg.0
0x21ed  ldarg.0
0x21ee  ldfld    string Microsoft.BIServer.BIService.ServiceConfig::_serviceConfigFilePath
0x21f3  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x21f8  call     instance void Microsoft.BIServer.BIService.ServiceConfig::ConfigureServiceConfig(string serviceConfigFileContent)
0x21fd  ldarg.0
0x21fe  ldarg.0
0x21ff  ldstr    aRsconfigfilepa// "rsConfigFilePath"
0x2204  call     instance string Microsoft.BIServer.BIService.ServiceConfig::GetRequiredConfig(string key)
0x2209  stfld    string Microsoft.BIServer.BIService.ServiceConfig::_rsConfigFilePath
0x220e  ldarg.0
0x220f  ldfld    string Microsoft.BIServer.BIService.ServiceConfig::_rsConfigFilePath
0x2214  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::.ctor(string)
0x2219  call     void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::set_Current(class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader)
0x221e  leave.s  loc_2240
0x2220  ldstr    aExceptionOccur// "Exception occurred while parsing config"...
0x2225  ldc.i4.1
0x2226  newarr   [mscorlib]System.Object
0x222b  dup
0x222c  ldc.i4.0
0x222d  ldarg.0
0x222e  ldfld    string Microsoft.BIServer.BIService.ServiceConfig::_serviceConfigFilePath
0x2233  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x2238  stelem.ref
0x2239  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x223e  rethrow
0x2240  ret
```
