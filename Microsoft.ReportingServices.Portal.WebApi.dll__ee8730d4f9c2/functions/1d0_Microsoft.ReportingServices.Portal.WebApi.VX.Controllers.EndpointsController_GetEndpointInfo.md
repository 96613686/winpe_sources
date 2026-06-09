# Microsoft.ReportingServices.Portal.WebApi.VX.Controllers.EndpointsController::GetEndpointInfo

- ea: `0x1d0`
- end: `0x1e1`
- name: `Microsoft.ReportingServices.Portal.WebApi.VX.Controllers.EndpointsController::GetEndpointInfo`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x190`
- `0x1a0`

## pseudocode

```c

```

## disassembly

```asm
0x1d0  newobj   instance void Microsoft.ReportingServices.Portal.WebApi.VX.Models.EndpointInfo::.ctor()
0x1d5  dup
0x1d6  ldsfld   string[] Microsoft.ReportingServices.Portal.WebApi.VX.Controllers.EndpointsController::apiVersions
0x1db  callvirt instance void Microsoft.ReportingServices.Portal.WebApi.VX.Models.EndpointInfo::set_SupportedEndpoints(string[] value)
0x1e0  ret
```
