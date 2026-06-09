# Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::.ctor

- ea: `0xcde0`
- end: `0xce0f`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::.ctor`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a60`
- `0x3800`

## callees

- `0xb1a0`

## pseudocode

```c

```

## disassembly

```asm
0xcde0  ldarg.0
0xcde1  call     instance void [mscorlib]System.Object::.ctor()
0xcde6  ldarg.0
0xcde7  ldarg.1
0xcde8  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogRepository
0xcded  ldarg.0
0xcdee  ldarg.2
0xcdef  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogItemController
0xcdf4  ldarg.0
0xcdf5  ldarg.s  4
0xcdf7  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_logger
0xcdfc  ldarg.0
0xcdfd  ldarg.3
0xcdfe  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xce03  ldarg.0
0xce04  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::.ctor()
0xce09  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_pbixReportHelper
0xce0e  ret
```
