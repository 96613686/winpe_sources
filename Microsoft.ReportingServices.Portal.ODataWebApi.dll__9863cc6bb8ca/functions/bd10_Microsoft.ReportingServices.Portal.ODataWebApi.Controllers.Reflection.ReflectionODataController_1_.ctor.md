# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1::.ctor

- ea: `0xbd10`
- end: `0xbd6d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1::.ctor`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xb230`
- `0xb330`
- `0xb420`

## pseudocode

```c

```

## disassembly

```asm
0xbd10  ldarg.0
0xbd11  ldarg.1
0xbd12  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>::.ctor()
0xbd17  dup
0xbd18  ldstr    aCast// "cast"
0xbd1d  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.CastSegmentHandler::.ctor()
0xbd22  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>::Add(var<u1>, !!T0)
0xbd27  dup
0xbd28  ldstr    aNavigation// "navigation"
0xbd2d  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.PropertySegmentHandler::.ctor()
0xbd32  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>::Add(var<u1>, !!T0)
0xbd37  dup
0xbd38  ldstr    aProperty// "property"
0xbd3d  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.PropertySegmentHandler::.ctor()
0xbd42  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>::Add(var<u1>, !!T0)
0xbd47  dup
0xbd48  ldstr    aValue// "$value"
0xbd4d  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.NoOpSegmentHandler::.ctor()
0xbd52  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>::Add(var<u1>, !!T0)
0xbd57  dup
0xbd58  ldstr    aCount_0// "$count"
0xbd5d  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.NoOpSegmentHandler::.ctor()
0xbd62  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>::Add(var<u1>, !!T0)
0xbd67  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>)
0xbd6c  ret
```
