# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::RestrictedSettings

- ea: `0x8f70`
- end: `0x900c`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::RestrictedSettings`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8f70`

## pseudocode

```c

```

## disassembly

```asm
0x8f70  ldc.i4.5
0x8f71  newarr   [mscorlib]System.String
0x8f76  dup
0x8f77  ldc.i4.0
0x8f78  ldstr    aSitename// "SiteName"
0x8f7d  stelem.ref
0x8f7e  dup
0x8f7f  ldc.i4.1
0x8f80  ldstr    aSystemreportti// "SystemReportTimeout"
0x8f85  stelem.ref
0x8f86  dup
0x8f87  ldc.i4.2
0x8f88  ldstr    aSystemsnapshot// "SystemSnapshotLimit"
0x8f8d  stelem.ref
0x8f8e  dup
0x8f8f  ldc.i4.3
0x8f90  ldstr    aOfficeonlinedi// "OfficeOnlineDiscoveryUrl"
0x8f95  stelem.ref
0x8f96  dup
0x8f97  ldc.i4.4
0x8f98  ldstr    aExcelwopiclien// "ExcelWopiClientUrl"
0x8f9d  stelem.ref
0x8f9e  stloc.0
0x8f9f  ldarg.0
0x8fa0  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_systemService
0x8fa5  ldarg.0
0x8fa6  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8fab  ldloc.0
0x8fac  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetSystemProperties(class [mscorlib]System.Security.Principal.IPrincipal, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x8fb1  call     T0x2B00008C
0x8fb6  stloc.1
0x8fb7  ldloc.1
0x8fb8  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__18_0
0x8fbd  dup
0x8fbe  brtrue.s loc_8FD7
0x8fc0  pop
0x8fc1  ldsfld   class <>c <>c::<>9
0x8fc6  ldftn    instance bool <>c::<RestrictedSettings>b__18_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property s)
0x8fcc  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0x8fd1  dup
0x8fd2  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__18_0
0x8fd7  call     T0x2B000064
0x8fdc  stloc.2
0x8fdd  ldloc.2
0x8fde  brfalse.s loc_9004
0x8fe0  ldloc.2
0x8fe1  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x8fe6  ldstr    aDefault// "Default"
0x8feb  ldc.i4.3
0x8fec  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x8ff1  brfalse.s loc_9004
0x8ff3  ldloc.2
0x8ff4  ldarg.0
0x8ff5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_systemService
0x8ffa  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetDefaultServerProductName()
0x8fff  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::set_Value(string)
0x9004  ldarg.0
0x9005  ldloc.1
0x9006  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::CreateOk(object)
0x900b  ret
```
