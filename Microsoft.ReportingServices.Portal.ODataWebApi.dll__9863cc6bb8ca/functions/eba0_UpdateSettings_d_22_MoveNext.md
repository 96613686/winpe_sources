# <UpdateSettings>d__22::MoveNext

- ea: `0xeba0`
- end: `0xecb9`
- name: `<UpdateSettings>d__22::MoveNext`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0xeba0`

## pseudocode

```c

```

## disassembly

```asm
0xeba0  ldarg.0
0xeba1  ldfld    int32 <UpdateSettings>d__22::<>1__state
0xeba6  stloc.0
0xeba7  ldarg.0
0xeba8  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController <UpdateSettings>d__22::<>4__this
0xebad  stloc.1
0xebae  ldloc.0
0xebaf  brfalse  loc_EC42
0xebb4  ldloc.1
0xebb5  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xebba  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xebbf  brfalse.s loc_EBD3
0xebc1  ldarg.0
0xebc2  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataActionParameters <UpdateSettings>d__22::actionParameters
0xebc7  ldstr    aPropertyvalues// "PropertyValues"
0xebcc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xebd1  brtrue.s loc_EBE5
0xebd3  ldloc.1
0xebd4  ldloc.1
0xebd5  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::GetModelStateValidationErrors()
0xebda  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::BadRequest(string)
0xebdf  stloc.2
0xebe0  leave    loc_ECA4
0xebe5  ldarg.0
0xebe6  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataActionParameters <UpdateSettings>d__22::actionParameters
0xebeb  ldstr    aPropertyvalues// "PropertyValues"
0xebf0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xebf5  castclass class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>
0xebfa  stloc.3
0xebfb  ldloc.1
0xebfc  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_systemService
0xec01  ldloc.3
0xec02  ldstr    aOfficeonlinedi// "OfficeOnlineDiscoveryUrl"
0xec07  ldstr    aExcelwopiclien// "ExcelWopiClientUrl"
0xec0c  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::ValidateWopiUrlProperty(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>, string, string)
0xec11  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>::GetAwaiter()
0xec16  stloc.s  5
0xec18  ldloca.s 5
0xec1a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>::get_IsCompleted()
0xec1f  brtrue.s loc_EC5F
0xec21  ldarg.0
0xec22  ldc.i4.0
0xec23  dup
0xec24  stloc.0
0xec25  stfld    int32 <UpdateSettings>d__22::<>1__state
0xec2a  ldarg.0
0xec2b  ldloc.s  5
0xec2d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <UpdateSettings>d__22::<>u__1
0xec32  ldarg.0
0xec33  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UpdateSettings>d__22::<>t__builder
0xec38  ldloca.s 5
0xec3a  ldarg.0
0xec3b  call     T0x2B00010A
0xec40  leave.s  loc_ECB8
0xec42  ldarg.0
0xec43  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <UpdateSettings>d__22::<>u__1
0xec48  stloc.s  5
0xec4a  ldarg.0
0xec4b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <UpdateSettings>d__22::<>u__1
0xec50  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>
0xec56  ldarg.0
0xec57  ldc.i4.m1
0xec58  dup
0xec59  stloc.0
0xec5a  stfld    int32 <UpdateSettings>d__22::<>1__state
0xec5f  ldloca.s 5
0xec61  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>::GetResult()
0xec66  stloc.3
0xec67  ldloc.1
0xec68  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_systemService
0xec6d  ldloc.1
0xec6e  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xec73  ldloc.3
0xec74  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::UpdateSystemProperties(class [mscorlib]System.Security.Principal.IPrincipal, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0xec79  stloc.s  4
0xec7b  ldloc.1
0xec7c  ldloc.s  4
0xec7e  box      [mscorlib]System.Boolean
0xec83  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::CreateOk(object)
0xec88  stloc.2
0xec89  leave.s  loc_ECA4
0xec8b  stloc.s  6
0xec8d  ldarg.0
0xec8e  ldc.i4.s 0xFE
0xec90  stfld    int32 <UpdateSettings>d__22::<>1__state
0xec95  ldarg.0
0xec96  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UpdateSettings>d__22::<>t__builder
0xec9b  ldloc.s  6
0xec9d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xeca2  leave.s  loc_ECB8
0xeca4  ldarg.0
0xeca5  ldc.i4.s 0xFE
0xeca7  stfld    int32 <UpdateSettings>d__22::<>1__state
0xecac  ldarg.0
0xecad  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UpdateSettings>d__22::<>t__builder
0xecb2  ldloc.2
0xecb3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xecb8  ret
```
