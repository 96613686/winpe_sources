# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::RegisterModel

- ea: `0x7790`
- end: `0x7c51`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::RegisterModel`
- size: `1217`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xbd0`

## string_xrefs

- `0x7853`: `DeleteItems`
- `0x7862`: `CatalogItemPaths`
- `0x7893`: `CatalogItemPaths`
- `0x7878`: `MoveItems`
- `0x7888`: `TargetPath`
- `0x7c3b`: `UpdateReportDataSets`
- `0x77b8`: `RemoveFromFavorites`
- `0x794d`: `CreateSnapshot`
- `0x7999`: `CreateSnapshot`
- `0x7963`: `DeleteSnapshot`
- `0x79af`: `DeleteSnapshot`
- `0x7983`: `UpdateExecutionSnapshot`
- `0x7b72`: `UpdateItemDataSources`
- `0x7b8d`: `UpdateItemDataSources`
- `0x7ba8`: `GetCacheOptions`
- `0x7bbe`: `GetCacheOptions`
- `0x7bd4`: `GetCacheOptions`
- `0x7bea`: `SetCacheOptions`
- `0x7c05`: `SetCacheOptions`
- `0x7c20`: `SetCacheOptions`
- `0x7bf4`: `cacheOptions`
- `0x7c0f`: `cacheOptions`
- `0x7c2a`: `cacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x7790  ldarg.0
0x7791  ldstr    aCatalogitems// "CatalogItems"
0x7796  callvirt T0x2B00004F
0x779b  pop
0x779c  ldarg.0
0x779d  callvirt T0x2B000050
0x77a2  ldstr    aAddtofavorites// "AddToFavorites"
0x77a7  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x77ac  callvirt T0x2B00006B
0x77b1  pop
0x77b2  ldarg.0
0x77b3  callvirt T0x2B000050
0x77b8  ldstr    aRemovefromfavo// "RemoveFromFavorites"
0x77bd  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x77c2  callvirt T0x2B00006B
0x77c7  pop
0x77c8  ldarg.0
0x77c9  callvirt T0x2B000050
0x77ce  ldstr    aGetproperties// "GetProperties"
0x77d3  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x77d8  callvirt T0x2B0000AB
0x77dd  ldstr    aRequestedprope// "RequestedProperties"
0x77e2  callvirt T0x2B0000AC
0x77e7  pop
0x77e8  ldarg.0
0x77e9  callvirt T0x2B000050
0x77ee  ldstr    aSetproperties// "SetProperties"
0x77f3  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x77f8  callvirt T0x2B00006B
0x77fd  ldstr    aProperties// "Properties"
0x7802  callvirt T0x2B0000AC
0x7807  pop
0x7808  ldarg.0
0x7809  callvirt T0x2B000050
0x780e  ldstr    aGetdependentit// "GetDependentItems"
0x7813  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Function(string)
0x7818  ldstr    aCatalogitems// "CatalogItems"
0x781d  callvirt T0x2B000032
0x7822  pop
0x7823  ldarg.0
0x7824  callvirt T0x2B000050
0x7829  ldstr    aSearchitems// "SearchItems"
0x782e  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Function(string)
0x7833  ldstr    aCatalogitems// "CatalogItems"
0x7838  callvirt T0x2B000032
0x783d  ldstr    aSearchtext// "SearchText"
0x7842  callvirt T0x2B000031
0x7847  pop
0x7848  ldarg.0
0x7849  callvirt T0x2B000050
0x784e  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::get_Collection()
0x7853  ldstr    aDeleteitems// "DeleteItems"
0x7858  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x785d  callvirt T0x2B000051
0x7862  ldstr    aCatalogitempat// "CatalogItemPaths"
0x7867  callvirt T0x2B000052
0x786c  pop
0x786d  ldarg.0
0x786e  callvirt T0x2B000050
0x7873  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::get_Collection()
0x7878  ldstr    aMoveitems// "MoveItems"
0x787d  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x7882  callvirt T0x2B000051
0x7887  dup
0x7888  ldstr    aTargetpath// "TargetPath"
0x788d  callvirt T0x2B000031
0x7892  pop
0x7893  ldstr    aCatalogitempat// "CatalogItemPaths"
0x7898  callvirt T0x2B000052
0x789d  pop
0x789e  ldarg.0
0x789f  callvirt T0x2B000050
0x78a4  ldstr    aGetroles// "GetRoles"
0x78a9  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Function(string)
0x78ae  callvirt T0x2B0000AD
0x78b3  pop
0x78b4  ldarg.0
0x78b5  callvirt T0x2B000050
0x78ba  ldstr    aGetpolicies// "GetPolicies"
0x78bf  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Function(string)
0x78c4  callvirt T0x2B0000AE
0x78c9  pop
0x78ca  ldarg.0
0x78cb  callvirt T0x2B000050
0x78d0  ldstr    aSetpolicies// "SetPolicies"
0x78d5  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x78da  callvirt T0x2B00006B
0x78df  ldstr    aPolicy// "Policy"
0x78e4  callvirt T0x2B0000AF
0x78e9  pop
0x78ea  ldarg.0
0x78eb  ldstr    aReportparamete// "ReportParameters"
0x78f0  callvirt T0x2B000080
0x78f5  pop
0x78f6  ldarg.0
0x78f7  callvirt T0x2B000081
0x78fc  ldstr    aSetparameterpr// "SetParameterProperties"
0x7901  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x7906  ldstr    aParameterprope// "ParameterProperties"
0x790b  callvirt T0x2B0000B0
0x7910  pop
0x7911  ldarg.0
0x7912  callvirt T0x2B000081
0x7917  ldstr    aSetreporthisto// "SetReportHistorySnapshotsOptions"
0x791c  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x7921  ldstr    aReporthistorys// "ReportHistorySnapshotsOptions"
0x7926  callvirt T0x2B0000B1
0x792b  pop
0x792c  ldarg.0
0x792d  callvirt T0x2B00006A
0x7932  ldstr    aSetreporthisto// "SetReportHistorySnapshotsOptions"
0x7937  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::Action(string)
0x793c  ldstr    aReporthistorys// "ReportHistorySnapshotsOptions"
0x7941  callvirt T0x2B0000B1
0x7946  pop
0x7947  ldarg.0
0x7948  callvirt T0x2B000081
0x794d  ldstr    aCreatesnapshot// "CreateSnapshot"
0x7952  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x7957  callvirt T0x2B000055
0x795c  pop
0x795d  ldarg.0
0x795e  callvirt T0x2B000081
0x7963  ldstr    aDeletesnapshot// "DeleteSnapshot"
0x7968  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x796d  callvirt T0x2B00006B
0x7972  ldstr    aHistoryid// "HistoryId"
0x7977  callvirt T0x2B000031
0x797c  pop
0x797d  ldarg.0
0x797e  callvirt T0x2B000081
0x7983  ldstr    aUpdateexecutio// "UpdateExecutionSnapshot"
0x7988  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x798d  callvirt T0x2B00006B
0x7992  pop
0x7993  ldarg.0
0x7994  callvirt T0x2B00006A
0x7999  ldstr    aCreatesnapshot// "CreateSnapshot"
0x799e  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::Action(string)
0x79a3  callvirt T0x2B000055
0x79a8  pop
0x79a9  ldarg.0
0x79aa  callvirt T0x2B00006A
0x79af  ldstr    aDeletesnapshot// "DeleteSnapshot"
0x79b4  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::Action(string)
0x79b9  callvirt T0x2B00006B
0x79be  ldstr    aHistoryid// "HistoryId"
0x79c3  callvirt T0x2B000031
0x79c8  pop
0x79c9  ldarg.0
0x79ca  callvirt T0x2B000081
0x79cf  ldstr    aGethistoryopti// "GetHistoryOptions"
0x79d4  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Function(string)
0x79d9  callvirt T0x2B0000B2
0x79de  pop
0x79df  ldarg.0
0x79e0  callvirt T0x2B000081
0x79e5  ldstr    aGetreporthisto// "GetReportHistorySnapshotsOptions"
0x79ea  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Function(string)
0x79ef  callvirt T0x2B0000B3
0x79f4  pop
0x79f5  ldarg.0
0x79f6  callvirt T0x2B00006A
0x79fb  ldstr    aGetreporthisto// "GetReportHistorySnapshotsOptions"
0x7a00  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::Function(string)
0x7a05  callvirt T0x2B0000B3
0x7a0a  pop
0x7a0b  ldarg.0
0x7a0c  callvirt T0x2B000074
0x7a11  ldstr    aGetschema// "GetSchema"
0x7a16  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::Function(string)
0x7a1b  callvirt T0x2B000075
0x7a20  pop
0x7a21  ldarg.0
0x7a22  callvirt T0x2B000074
0x7a27  ldstr    aGettable// "GetTable"
0x7a2c  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::Function(string)
0x7a31  callvirt T0x2B0000B4
0x7a36  pop
0x7a37  ldarg.0
0x7a38  callvirt T0x2B000074
0x7a3d  ldstr    aGettable// "GetTable"
0x7a42  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::Function(string)
0x7a47  callvirt T0x2B0000B4
0x7a4c  ldstr    aMaxrows// "maxRows"
0x7a51  callvirt T0x2B0000B5
0x7a56  pop
0x7a57  ldarg.0
0x7a58  callvirt T0x2B000074
0x7a5d  ldstr    aGetdata// "GetData"
0x7a62  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::Action(string)
0x7a67  callvirt T0x2B000055
0x7a6c  dup
0x7a6d  ldstr    aParameters// "Parameters"
0x7a72  callvirt T0x2B000076
0x7a77  pop
0x7a78  ldstr    aMaxrows// "maxRows"
0x7a7d  callvirt T0x2B000077
0x7a82  pop
0x7a83  ldarg.0
0x7a84  callvirt T0x2B000074
0x7a89  ldstr    aGetkpitrendset// "GetKpiTrendsetData"
0x7a8e  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::Action(string)
0x7a93  callvirt T0x2B000055
0x7a98  dup
0x7a99  ldstr    aParameters// "Parameters"
0x7a9e  callvirt T0x2B000076
0x7aa3  pop
0x7aa4  ldstr    aColumnname// "columnName"
0x7aa9  callvirt T0x2B000031
0x7aae  pop
0x7aaf  ldarg.0
0x7ab0  callvirt T0x2B000074
0x7ab5  ldstr    aGetaggregatedv// "GetAggregatedValue"
0x7aba  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::Action(string)
0x7abf  callvirt T0x2B000055
0x7ac4  ldstr    aParameters// "Parameters"
0x7ac9  callvirt T0x2B000076
0x7ace  pop
0x7acf  ldarg.0
0x7ad0  callvirt T0x2B000081
0x7ad5  ldstr    aCheckdatasourc// "CheckDataSourceConnection"
0x7ada  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x7adf  callvirt T0x2B00005F
0x7ae4  ldstr    aDatasourcename// "DataSourceName"
0x7ae9  callvirt T0x2B000031
0x7aee  pop
0x7aef  ldarg.0
0x7af0  callvirt T0x2B00006F
0x7af5  ldstr    aCheckconnectio// "CheckConnection"
0x7afa  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::Action(string)
0x7aff  callvirt T0x2B00005F
0x7b04  pop
0x7b05  ldarg.0
0x7b06  callvirt T0x2B00006F
0x7b0b  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Collection()
0x7b10  ldstr    aCheckconnectio// "CheckConnection"
0x7b15  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::Action(string)
0x7b1a  callvirt T0x2B00005F
0x7b1f  ldstr    aDatasource// "dataSource"
0x7b24  callvirt T0x2B000070
0x7b29  pop
0x7b2a  ldarg.0
0x7b2b  callvirt T0x2B00006F
0x7b30  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Collection()
0x7b35  ldstr    aGetqueryfields// "GetQueryFields"
0x7b3a  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::Action(string)
0x7b3f  callvirt T0x2B000071
0x7b44  dup
0x7b45  ldstr    aDatasource// "dataSource"
0x7b4a  callvirt T0x2B000070
0x7b4f  pop
0x7b50  dup
0x7b51  ldstr    aQuery// "query"
0x7b56  callvirt T0x2B000072
0x7b5b  pop
0x7b5c  ldstr    aSubscriptionid// "subscriptionId"
0x7b61  callvirt T0x2B000031
0x7b66  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ParameterConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ParameterConfiguration::Optional()
0x7b6b  pop
0x7b6c  ldarg.0
0x7b6d  callvirt T0x2B000081
0x7b72  ldstr    aUpdateitemdata// "UpdateItemDataSources"
0x7b77  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x7b7c  ldstr    aDatasources_0// "dataSources"
0x7b81  callvirt T0x2B0000B6
0x7b86  pop
0x7b87  ldarg.0
0x7b88  callvirt T0x2B000074
0x7b8d  ldstr    aUpdateitemdata// "UpdateItemDataSources"
0x7b92  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::Action(string)
0x7b97  ldstr    aDatasources_0// "dataSources"
0x7b9c  callvirt T0x2B0000B6
0x7ba1  pop
0x7ba2  ldarg.0
0x7ba3  callvirt T0x2B000081
0x7ba8  ldstr    aGetcacheoption// "GetCacheOptions"
0x7bad  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Function(string)
0x7bb2  callvirt T0x2B0000B7
0x7bb7  pop
0x7bb8  ldarg.0
0x7bb9  callvirt T0x2B00006A
0x7bbe  ldstr    aGetcacheoption// "GetCacheOptions"
0x7bc3  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::Function(string)
0x7bc8  callvirt T0x2B0000B7
0x7bcd  pop
0x7bce  ldarg.0
0x7bcf  callvirt T0x2B000074
0x7bd4  ldstr    aGetcacheoption// "GetCacheOptions"
0x7bd9  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::Function(string)
0x7bde  callvirt T0x2B0000B7
0x7be3  pop
0x7be4  ldarg.0
0x7be5  callvirt T0x2B000081
0x7bea  ldstr    aSetcacheoption// "SetCacheOptions"
0x7bef  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::Action(string)
0x7bf4  ldstr    aCacheoptions// "cacheOptions"
0x7bf9  callvirt T0x2B0000B8
0x7bfe  pop
0x7bff  ldarg.0
  ... truncated ...
```
