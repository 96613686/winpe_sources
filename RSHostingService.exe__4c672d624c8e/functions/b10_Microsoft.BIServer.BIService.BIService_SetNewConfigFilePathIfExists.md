# Microsoft.BIServer.BIService.BIService::SetNewConfigFilePathIfExists

- ea: `0xb10`
- end: `0xb39`
- name: `Microsoft.BIServer.BIService.BIService::SetNewConfigFilePathIfExists`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa60`
- `0x3390`
- `0x3970`

## callees

- `0xb10`
- `0x21c0`

## pseudocode

```c

```

## disassembly

```asm
0xb10  ldarg.1
0xb11  call     bool [mscorlib]System.IO.File::Exists(string)
0xb16  brfalse.s loc_B37
0xb18  ldarg.0
0xb19  ldarg.1
0xb1a  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0xb1f  stfld    string Microsoft.BIServer.BIService.BIService::_serviceConfigFilePath
0xb24  ldarg.0
0xb25  ldarg.0
0xb26  ldfld    string Microsoft.BIServer.BIService.BIService::_serviceConfigFilePath
0xb2b  newobj   instance void Microsoft.BIServer.BIService.ServiceConfig::.ctor(string serviceConfigFilePath)
0xb30  stfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0xb35  ldc.i4.1
0xb36  ret
0xb37  ldc.i4.0
0xb38  ret
```
