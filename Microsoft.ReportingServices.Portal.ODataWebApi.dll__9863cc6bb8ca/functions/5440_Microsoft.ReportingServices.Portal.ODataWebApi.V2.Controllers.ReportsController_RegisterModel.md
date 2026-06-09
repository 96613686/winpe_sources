# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ReportsController::RegisterModel

- ea: `0x5440`
- end: `0x54f3`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ReportsController::RegisterModel`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x11c0`

## string_xrefs

- `0x545d`: `UpdateCacheSnapshot`
- `0x5493`: `UpdateReportDataSets`

## pseudocode

```c

```

## disassembly

```asm
0x5440  ldarg.0
0x5441  ldstr    aReports// "Reports"
0x5446  call     void class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::RegisterModel(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder, string)
0x544b  ldarg.0
0x544c  ldstr    aParameterdefin// "ParameterDefinitions"
0x5451  callvirt T0x2B000080
0x5456  pop
0x5457  ldarg.0
0x5458  callvirt T0x2B000081
0x545d  ldstr    aUpdatecachesna// "UpdateCacheSnapshot"
0x5462  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x5467  callvirt T0x2B00006B
0x546c  pop
0x546d  ldarg.0
0x546e  callvirt T0x2B000081
0x5473  ldstr    aCheckdatasourc// "CheckDataSourceConnection"
0x5478  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x547d  callvirt T0x2B00005F
0x5482  ldstr    aDatasourcename// "DataSourceName"
0x5487  callvirt T0x2B000031
0x548c  pop
0x548d  ldarg.0
0x548e  callvirt T0x2B000081
0x5493  ldstr    aUpdatereportda// "UpdateReportDataSets"
0x5498  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x549d  ldstr    aDatasets// "DataSets"
0x54a2  callvirt T0x2B000082
0x54a7  pop
0x54a8  ldarg.0
0x54a9  callvirt T0x2B000081
0x54ae  ldstr    aGetparameters// "GetParameters"
0x54b3  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x54b8  ldstr    aParameterdefin// "ParameterDefinitions"
0x54bd  callvirt T0x2B000083
0x54c2  ldstr    aParametervalue_0// "ParameterValues"
0x54c7  callvirt T0x2B00005A
0x54cc  pop
0x54cd  ldarg.0
0x54ce  callvirt T0x2B000081
0x54d3  ldstr    aProcessparamet// "ProcessParameters"
0x54d8  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x54dd  ldstr    aParameterdefin// "ParameterDefinitions"
0x54e2  callvirt T0x2B000083
0x54e7  ldstr    aParametervalue_0// "ParameterValues"
0x54ec  callvirt T0x2B00005A
0x54f1  pop
0x54f2  ret
```
