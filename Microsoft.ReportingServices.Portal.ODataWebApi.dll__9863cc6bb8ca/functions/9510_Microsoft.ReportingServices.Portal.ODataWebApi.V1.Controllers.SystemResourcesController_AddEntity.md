# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::AddEntity

- ea: `0x9510`
- end: `0x95bb`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::AddEntity`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5fe0`

## callees

- `0x680`
- `0x690`
- `0x9510`

## pseudocode

```c

```

## disassembly

```asm
0x9510  ldarg.1
0x9511  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourcePackage
0x9516  stloc.0
0x9517  ldloc.0
0x9518  brtrue.s loc_9539
0x951a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x951f  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_NotExpectedTypeException()
0x9524  ldstr    aSystemresource_4// "SystemResourcePackage"
0x9529  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x952e  ldstr    aEntity// "entity"
0x9533  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9538  throw
0x9539  ldloc.0
0x953a  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourcePackage::get_PackageFileName()
0x953f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9544  brfalse.s loc_9556
0x9546  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException()
0x954b  ldstr    aPackagefilenam// "PackageFileName"
0x9550  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9555  throw
0x9556  ldloc.0
0x9557  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourcePackage::get_Content()
0x955c  brfalse.s loc_9567
0x955e  ldloc.0
0x955f  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourcePackage::get_Content()
0x9564  ldlen
0x9565  brtrue.s loc_9577
0x9567  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException()
0x956c  ldstr    aContent// "Content"
0x9571  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9576  throw
0x9577  ldloc.0
0x9578  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::get_TypeName()
0x957d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9582  brfalse.s loc_9594
0x9584  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException()
0x9589  ldstr    aTypename// "TypeName"
0x958e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9593  throw
0x9594  ldarg.2
0x9595  ldarg.0
0x9596  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::_systemResourceService
0x959b  ldarg.0
0x959c  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x95a1  ldloc.0
0x95a2  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourcePackage::get_Content()
0x95a7  ldloc.0
0x95a8  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourcePackage::get_PackageFileName()
0x95ad  ldarg.1
0x95ae  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::get_TypeName()
0x95b3  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService::InstallSystemResourcePackage(class [mscorlib]System.Security.Principal.IPrincipal, unsigned int8[], string, string)
0x95b8  stind.ref
0x95b9  ldc.i4.1
0x95ba  ret
```
