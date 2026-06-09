# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::UpdateDataModelParametersInPowerBI

- ea: `0xab80`
- end: `0xabc6`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::UpdateDataModelParametersInPowerBI`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xab80`
- `0xb070`
- `0xb140`

## pseudocode

```c

```

## disassembly

```asm
0xab80  ldarg.0
0xab81  ldarg.1
0xab82  ldarg.2
0xab83  ldarg.3
0xab84  ldarg.s  4
0xab86  ldarg.s  5
0xab88  ldarg.s  6
0xab8a  call     instance class [System]System.Net.HttpWebRequest Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::BuildUpdateDataModelParametersWebRequest(valuetype [mscorlib]System.Guid catalogId, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> dataModelParameters, string powerBiUri, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string reportServerHostName)
0xab8f  stloc.0
0xab90  ldarg.0
0xab91  ldloc.0
0xab92  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::GetUpdateDataModelParametersResponse(class [System]System.Net.HttpWebRequest request)
0xab97  call     T0x2B0000E0
0xab9c  ldsfld   class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__22_0
0xaba1  dup
0xaba2  brtrue.s loc_ABBB
0xaba4  pop
0xaba5  ldsfld   class <>c <>c::<>9
0xabaa  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c::<UpdateDataModelParametersInPowerBI>b__22_0(class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource pbiDs)
0xabb0  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor(object, native int)
0xabb5  dup
0xabb6  stsfld   class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__22_0
0xabbb  call     T0x2B0000E1
0xabc0  call     T0x2B0000E2
0xabc5  ret
```
