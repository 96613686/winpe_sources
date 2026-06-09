# Microsoft.ReportingServices.Portal.ODataWebApi.MethodBasedRoutingConvention::.ctor

- ea: `0x370`
- end: `0x38c`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.MethodBasedRoutingConvention::.ctor`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb80`
- `0xba0`

## callees

- `0x370`

## pseudocode

```c

```

## disassembly

```asm
0x370  ldarg.0
0x371  call     instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.NavigationSourceRoutingConvention::.ctor()
0x376  ldarg.1
0x377  brtrue.s loc_384
0x379  ldstr    aLogger// "logger"
0x37e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x383  throw
0x384  ldarg.0
0x385  ldarg.1
0x386  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.MethodBasedRoutingConvention::_logger
0x38b  ret
```
