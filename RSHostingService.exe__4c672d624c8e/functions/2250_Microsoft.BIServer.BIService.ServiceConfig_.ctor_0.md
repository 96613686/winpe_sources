# Microsoft.BIServer.BIService.ServiceConfig::.ctor_0

- ea: `0x2250`
- end: `0x227d`
- name: `Microsoft.BIServer.BIService.ServiceConfig::.ctor_0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2250`
- `0x2280`

## string_xrefs

- `0x226b`: `Exception occurred while parsing config file content`

## pseudocode

```c

```

## disassembly

```asm
0x2250  ldarg.0
0x2251  call     instance void [mscorlib]System.Object::.ctor()
0x2256  ldarg.2
0x2257  ldnull
0x2258  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::.ctor(class [mscorlib]System.IO.Stream, string)
0x225d  call     void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::set_Current(class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader)
0x2262  ldarg.0
0x2263  ldarg.1
0x2264  call     instance void Microsoft.BIServer.BIService.ServiceConfig::ConfigureServiceConfig(string serviceConfigFileContent)
0x2269  leave.s  loc_227C
0x226b  ldstr    aExceptionOccur_0// "Exception occurred while parsing config"...
0x2270  call     T0x2B000001
0x2275  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x227a  rethrow
0x227c  ret
```
