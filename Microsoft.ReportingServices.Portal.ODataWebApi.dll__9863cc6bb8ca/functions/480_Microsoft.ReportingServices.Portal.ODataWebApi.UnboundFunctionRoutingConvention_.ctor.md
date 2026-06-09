# Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::.ctor

- ea: `0x480`
- end: `0x49c`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::.ctor`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb80`
- `0xba0`

## callees

- `0x480`

## pseudocode

```c

```

## disassembly

```asm
0x480  ldarg.0
0x481  call     instance void [mscorlib]System.Object::.ctor()
0x486  ldarg.1
0x487  brtrue.s loc_494
0x489  ldstr    aLogger// "logger"
0x48e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x493  throw
0x494  ldarg.0
0x495  ldarg.1
0x496  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::_logger
0x49b  ret
```
