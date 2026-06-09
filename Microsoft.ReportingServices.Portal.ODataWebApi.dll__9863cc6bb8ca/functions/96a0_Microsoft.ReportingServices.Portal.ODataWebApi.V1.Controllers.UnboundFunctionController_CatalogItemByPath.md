# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CatalogItemByPath

- ea: `0x96a0`
- end: `0x9746`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CatalogItemByPath`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x96a0`
- `0x9990`
- `0x9aa0`

## pseudocode

```c

```

## disassembly

```asm
0x96a0  ldarg.0
0x96a1  ldarg.1
0x96a2  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CleanPath(string path)
0x96a7  starg.s  1
0x96a9  ldarg.0
0x96aa  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_catalogRepository
0x96af  ldarg.0
0x96b0  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x96b5  ldarg.1
0x96b6  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x96bb  stloc.0
0x96bc  ldloc.0
0x96bd  brtrue.s loc_96C6
0x96bf  ldarg.0
0x96c0  callvirt instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult [System.Web.Http]System.Web.Http.ApiController::NotFound()
0x96c5  ret
0x96c6  ldnull
0x96c7  stloc.1
0x96c8  ldloc.0
0x96c9  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x96ce  stloc.2
0x96cf  ldloc.2
0x96d0  ldc.i4.2
0x96d1  sub
0x96d2  switch   loc_970C, loc_96EA, loc_96FE
0x96e3  ldloc.2
0x96e4  ldc.i4.s 0xA
0x96e6  beq.s    loc_971A
0x96e8  br.s     loc_972C
0x96ea  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor()
0x96ef  dup
0x96f0  ldloc.0
0x96f1  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource
0x96f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::Add(var<u1>)
0x96fb  stloc.1
0x96fc  br.s     loc_972C
0x96fe  ldloc.0
0x96ff  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet
0x9704  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet::get_DataSources()
0x9709  stloc.1
0x970a  br.s     loc_972C
0x970c  ldloc.0
0x970d  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.Report
0x9712  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.Report::get_DataSources()
0x9717  stloc.1
0x9718  br.s     loc_972C
0x971a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor()
0x971f  dup
0x9720  ldloc.0
0x9721  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel
0x9726  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::Add(var<u1>)
0x972b  stloc.1
0x972c  ldarg.0
0x972d  ldloc.1
0x972e  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::SetPasswordToNull(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> dataSources)
0x9733  ldloc.0
0x9734  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor()
0x9739  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Properties(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0x973e  ldarg.0
0x973f  ldloc.0
0x9740  callvirt T0x2B0000D5
0x9745  ret
```
