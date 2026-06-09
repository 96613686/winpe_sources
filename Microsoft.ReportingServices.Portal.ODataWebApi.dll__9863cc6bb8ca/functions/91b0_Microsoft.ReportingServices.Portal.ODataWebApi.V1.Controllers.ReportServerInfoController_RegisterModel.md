# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::RegisterModel

- ea: `0x91b0`
- end: `0x9351`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::RegisterModel`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0xbd0`

## string_xrefs

- `0x923a`: `ValidateExtensionSettings`
- `0x9229`: `ExtensionName`
- `0x9255`: `ExtensionName`
- `0x91c2`: `DeliveryExtensions`
- `0x91d8`: `DeliveryUIExtensions`
- `0x91ee`: `DataExtensions`
- `0x9204`: `RenderingExtensions`
- `0x921a`: `ExtensionParameters`
- `0x92ea`: `UpdateSettings`
- `0x930a`: `SetSystemPolicies`
- `0x9340`: `GetVirtualDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x91b0  ldarg.0
0x91b1  ldstr    aReportserverin// "ReportServerInfo"
0x91b6  callvirt T0x2B0000C4
0x91bb  pop
0x91bc  ldarg.0
0x91bd  callvirt T0x2B0000C5
0x91c2  ldstr    aDeliveryextens// "DeliveryExtensions"
0x91c7  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x91cc  callvirt T0x2B0000C6
0x91d1  pop
0x91d2  ldarg.0
0x91d3  callvirt T0x2B0000C5
0x91d8  ldstr    aDeliveryuiexte// "DeliveryUIExtensions"
0x91dd  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x91e2  callvirt T0x2B0000C6
0x91e7  pop
0x91e8  ldarg.0
0x91e9  callvirt T0x2B0000C5
0x91ee  ldstr    aDataextensions// "DataExtensions"
0x91f3  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x91f8  callvirt T0x2B0000C6
0x91fd  pop
0x91fe  ldarg.0
0x91ff  callvirt T0x2B0000C5
0x9204  ldstr    aRenderingexten// "RenderingExtensions"
0x9209  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x920e  callvirt T0x2B0000C6
0x9213  pop
0x9214  ldarg.0
0x9215  callvirt T0x2B0000C5
0x921a  ldstr    aExtensionparam// "ExtensionParameters"
0x921f  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x9224  callvirt T0x2B0000C7
0x9229  ldstr    aExtensionname// "ExtensionName"
0x922e  callvirt T0x2B000031
0x9233  pop
0x9234  ldarg.0
0x9235  callvirt T0x2B0000C5
0x923a  ldstr    aValidateextens// "ValidateExtensionSettings"
0x923f  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Action(string)
0x9244  callvirt T0x2B000059
0x9249  dup
0x924a  ldstr    aParametervalue_0// "ParameterValues"
0x924f  callvirt T0x2B00005A
0x9254  pop
0x9255  ldstr    aExtensionname// "ExtensionName"
0x925a  callvirt T0x2B000031
0x925f  pop
0x9260  ldarg.0
0x9261  callvirt T0x2B0000C5
0x9266  ldstr    aPolicies// "Policies"
0x926b  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x9270  callvirt T0x2B0000C8
0x9275  pop
0x9276  ldarg.0
0x9277  callvirt T0x2B0000C5
0x927c  ldstr    aRoles// "Roles"
0x9281  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x9286  callvirt T0x2B0000AD
0x928b  pop
0x928c  ldarg.0
0x928d  callvirt T0x2B0000C5
0x9292  ldstr    aRestrictedsett// "RestrictedSettings"
0x9297  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x929c  callvirt T0x2B0000C9
0x92a1  pop
0x92a2  ldarg.0
0x92a3  callvirt T0x2B0000C5
0x92a8  ldstr    aSettings// "Settings"
0x92ad  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x92b2  callvirt T0x2B0000C9
0x92b7  pop
0x92b8  ldarg.0
0x92b9  callvirt T0x2B0000C5
0x92be  ldstr    aServerproducti// "ServerProductInfo"
0x92c3  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x92c8  callvirt T0x2B0000C9
0x92cd  pop
0x92ce  ldarg.0
0x92cf  callvirt T0x2B0000C5
0x92d4  ldstr    aSitename// "SiteName"
0x92d9  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x92de  callvirt T0x2B0000B4
0x92e3  pop
0x92e4  ldarg.0
0x92e5  callvirt T0x2B0000C5
0x92ea  ldstr    aUpdatesettings// "UpdateSettings"
0x92ef  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Action(string)
0x92f4  callvirt T0x2B00006B
0x92f9  ldstr    aPropertyvalues// "PropertyValues"
0x92fe  callvirt T0x2B0000AC
0x9303  pop
0x9304  ldarg.0
0x9305  callvirt T0x2B0000C5
0x930a  ldstr    aSetsystempolic// "SetSystemPolicies"
0x930f  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Action(string)
0x9314  callvirt T0x2B00006B
0x9319  ldstr    aPolicy// "Policy"
0x931e  callvirt T0x2B0000AF
0x9323  pop
0x9324  ldarg.0
0x9325  callvirt T0x2B0000C5
0x932a  ldstr    aGetwebappurl// "GetWebAppUrl"
0x932f  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x9334  callvirt T0x2B0000B4
0x9339  pop
0x933a  ldarg.0
0x933b  callvirt T0x2B0000C5
0x9340  ldstr    aGetvirtualdire// "GetVirtualDirectory"
0x9345  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::Function(string)
0x934a  callvirt T0x2B0000B4
0x934f  pop
0x9350  ret
```
