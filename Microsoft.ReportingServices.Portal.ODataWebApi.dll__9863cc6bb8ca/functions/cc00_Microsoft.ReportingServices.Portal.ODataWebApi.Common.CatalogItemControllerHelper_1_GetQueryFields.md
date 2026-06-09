# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetQueryFields

- ea: `0xcc00`
- end: `0xcdb4`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetQueryFields`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x6830`
- `0xcc00`

## pseudocode

```c

```

## disassembly

```asm
0xcc00  ldarg.0
0xcc01  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcc06  callvirt instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xcc0b  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xcc10  brfalse.s loc_CC22
0xcc12  ldarg.1
0xcc13  brfalse.s loc_CC22
0xcc15  ldarg.1
0xcc16  ldstr    aQuery// "query"
0xcc1b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xcc20  brtrue.s loc_CC39
0xcc22  ldarg.0
0xcc23  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcc28  ldarg.0
0xcc29  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcc2e  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xcc33  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xcc38  ret
0xcc39  ldarg.1
0xcc3a  ldstr    aQuery// "query"
0xcc3f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xcc44  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.Query
0xcc49  stloc.0
0xcc4a  ldnull
0xcc4b  stloc.1
0xcc4c  ldarg.1
0xcc4d  ldstr    aDatasource// "dataSource"
0xcc52  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xcc57  brfalse.s loc_CC6A
0xcc59  ldarg.1
0xcc5a  ldstr    aDatasource// "dataSource"
0xcc5f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xcc64  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource
0xcc69  stloc.1
0xcc6a  ldsfld   string [mscorlib]System.String::Empty
0xcc6f  stloc.2
0xcc70  ldarg.1
0xcc71  ldstr    aSubscriptionid// "subscriptionId"
0xcc76  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xcc7b  brfalse.s loc_CC8E
0xcc7d  ldarg.1
0xcc7e  ldstr    aSubscriptionid// "subscriptionId"
0xcc83  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xcc88  isinst   [mscorlib]System.String
0xcc8d  stloc.2
0xcc8e  ldloc.0
0xcc8f  brtrue.s loc_CCA8
0xcc91  ldarg.0
0xcc92  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcc97  ldarg.0
0xcc98  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcc9d  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xcca2  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xcca7  ret
0xcca8  ldloc.1
0xcca9  brfalse.s loc_CCC5
0xccab  ldloc.1
0xccac  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0xccb1  brtrue.s loc_CCC5
0xccb3  ldloc.1
0xccb4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataSourceType()
0xccb9  brtrue.s loc_CCC5
0xccbb  ldloc.1
0xccbc  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_IsReference()
0xccc1  brtrue.s loc_CCC5
0xccc3  ldnull
0xccc4  stloc.1
0xccc5  ldloc.1
0xccc6  brtrue.s loc_CCE7
0xccc8  ldloc.2
0xccc9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xccce  brfalse.s loc_CCE7
0xccd0  ldarg.0
0xccd1  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xccd6  ldarg.0
0xccd7  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xccdc  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xcce1  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xcce6  ret
0xcce7  ldloc.1
0xcce8  brtrue   loc_CD82
0xcced  ldarg.0
0xccee  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xccf3  ldarg.0
0xccf4  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xccf9  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xccfe  ldloc.2
0xccff  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xcd04  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataRetrievalPlanFromCatalog(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xcd09  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataRetrievalPlan::get_DataSource()
0xcd0e  stloc.1
0xcd0f  ldloc.1
0xcd10  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_IsReference()
0xcd15  brtrue.s loc_CD82
0xcd17  ldloc.1
0xcd18  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialRetrievalType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialRetrieval()
0xcd1d  ldc.i4.1
0xcd1e  bne.un.s loc_CD82
0xcd20  ldloc.1
0xcd21  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0xcd26  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::get_Password()
0xcd2b  brtrue.s loc_CD82
0xcd2d  ldnull
0xcd2e  stloc.s  4
0xcd30  ldarg.0
0xcd31  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xcd36  ldarg.0
0xcd37  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcd3c  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xcd41  ldloc.2
0xcd42  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xcd47  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataSourcePasswordForSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xcd4c  stloc.s  4
0xcd4e  leave.s  loc_CD62
0xcd50  pop
0xcd51  ldstr    aRetrievingTheP// "Retrieving the password from server fai"...
0xcd56  call     T0x2B0000F3
0xcd5b  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0xcd60  leave.s  loc_CD62
0xcd62  ldloc.s  4
0xcd64  brfalse.s loc_CD82
0xcd66  ldloc.1
0xcd67  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0xcd6c  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.CatalogEncryption::get_Instance()
0xcd71  ldloc.s  4
0xcd73  ldstr    aPassword// "Password"
0xcd78  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString(unsigned int8[], string)
0xcd7d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::set_Password(string)
0xcd82  nop
0xcd83  ldarg.0
0xcd84  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xcd89  ldarg.0
0xcd8a  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcd8f  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xcd94  ldloc.1
0xcd95  ldloc.0
0xcd96  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetQueryFields(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Query)
0xcd9b  stloc.3
0xcd9c  leave.s  loc_CDA7
0xcd9e  ldc.i4.s 0x48
0xcda0  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AllowSoapDetailException(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code)
0xcda5  rethrow
0xcda7  ldarg.0
0xcda8  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcdad  ldloc.3
0xcdae  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::CreateOk(object)
0xcdb3  ret
```
