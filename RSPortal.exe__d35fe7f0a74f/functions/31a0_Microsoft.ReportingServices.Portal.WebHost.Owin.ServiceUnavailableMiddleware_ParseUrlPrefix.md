# Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::ParseUrlPrefix

- ea: `0x31a0`
- end: `0x31bf`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::ParseUrlPrefix`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x31a0`

## pseudocode

```c

```

## disassembly

```asm
0x31a0  ldarg.0
0x31a1  ldloca.s 1
0x31a3  ldloca.s 0
0x31a5  ldloca.s 4
0x31a7  ldloca.s 2
0x31a9  ldloca.s 3
0x31ab  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUrlPrefix(string, string&, string&, string&, string&, string&)
0x31b0  brfalse.s loc_31B4
0x31b2  ldloc.2
0x31b3  ret
0x31b4  ldstr    aInvalidUrlDete// "Invalid url detected"
0x31b9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x31be  throw
```
