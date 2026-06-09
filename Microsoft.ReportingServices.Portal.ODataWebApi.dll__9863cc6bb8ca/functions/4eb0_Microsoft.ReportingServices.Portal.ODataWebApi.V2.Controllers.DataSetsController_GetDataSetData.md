# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController::GetDataSetData

- ea: `0x4eb0`
- end: `0x5053`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController::GetDataSetData`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4eb0`
- `0xe7a0`

## pseudocode

```c

```

## disassembly

```asm
0x4eb0  newobj   instance void <>c__DisplayClass24_0::.ctor()
0x4eb5  stloc.0
0x4eb6  ldsfld   string [mscorlib]System.String::Empty
0x4ebb  stloc.2
0x4ebc  ldarg.0
0x4ebd  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::get_CatalogItemControllerHelper()
0x4ec2  ldarg.1
0x4ec3  ldloca.s 2
0x4ec5  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::IsRequestByPath(string, string&)
0x4eca  brfalse.s loc_4EF5
0x4ecc  ldarg.0
0x4ecd  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::get_CatalogRepository()
0x4ed2  ldarg.0
0x4ed3  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x4ed8  ldloc.2
0x4ed9  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x4ede  stloc.s  7
0x4ee0  ldloc.s  7
0x4ee2  brtrue.s loc_4EEB
0x4ee4  ldarg.0
0x4ee5  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::NotFound()
0x4eea  ret
0x4eeb  ldloc.s  7
0x4eed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x4ef2  stloc.1
0x4ef3  br.s     loc_4F06
0x4ef5  ldarg.1
0x4ef6  ldloca.s 1
0x4ef8  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x4efd  brtrue.s loc_4F06
0x4eff  ldarg.0
0x4f00  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::NotFound()
0x4f05  ret
0x4f06  ldarg.0
0x4f07  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x4f0c  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetQueryNameValuePairs(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x4f11  call     T0x2B00007B
0x4f16  stloc.3
0x4f17  ldloc.0
0x4f18  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>::.ctor()
0x4f1d  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> <>c__DisplayClass24_0::dataSetParameters
0x4f22  ldloc.3
0x4f23  call     T0x2B00007C
0x4f28  ldc.i4.0
0x4f29  ble.s    loc_4F3D
0x4f2b  ldloc.3
0x4f2c  ldloc.0
0x4f2d  ldftn    instance void <>c__DisplayClass24_0::<GetDataSetData>b__0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> keyValuePair)
0x4f33  newobj   instance void class [mscorlib]System.Action`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::.ctor(object, native int)
0x4f38  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::ForEach(class [mscorlib]System.Action`1<var<u1>>)
0x4f3d  ldc.i4.0
0x4f3e  stloc.s  4
0x4f40  ldarg.0
0x4f41  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::get_DataService()
0x4f46  ldarg.0
0x4f47  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x4f4c  ldloc.1
0x4f4d  ldloc.0
0x4f4e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> <>c__DisplayClass24_0::dataSetParameters
0x4f53  ldloca.s 8
0x4f55  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4f5b  ldloc.s  8
0x4f5d  ldloca.s 4
0x4f5f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetDataSetTableJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, valuetype [mscorlib]System.Nullable`1<int32>, bool&)
0x4f64  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::Parse(string)
0x4f69  stloc.s  5
0x4f6b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetRow>::.ctor()
0x4f70  stloc.s  6
0x4f72  ldloc.s  5
0x4f74  ldstr    aRows// "Rows"
0x4f79  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0x4f7e  brfalse  loc_504A
0x4f83  ldloc.s  5
0x4f85  ldstr    aRows// "Rows"
0x4f8a  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0x4f8f  call     T0x2B00007D
0x4f94  ldc.i4.0
0x4f95  ble      loc_504A
0x4f9a  ldloc.s  5
0x4f9c  ldstr    aColumns// "Columns"
0x4fa1  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0x4fa6  stloc.s  9
0x4fa8  ldloc.s  5
0x4faa  ldstr    aRows// "Rows"
0x4faf  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0x4fb4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::GetEnumerator()
0x4fb9  stloc.s  0xA
0x4fbb  br.s     loc_5033
0x4fbd  ldloc.s  0xA
0x4fbf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::get_Current()
0x4fc4  stloc.s  0xB
0x4fc6  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetRow::.ctor()
0x4fcb  dup
0x4fcc  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4fd1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetRow::set_Id(valuetype [mscorlib]System.Guid)
0x4fd6  stloc.s  0xC
0x4fd8  ldc.i4.0
0x4fd9  stloc.s  0xD
0x4fdb  br.s     loc_501F
0x4fdd  ldloc.s  0xC
0x4fdf  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetRow::get_Properties()
0x4fe4  ldloc.s  9
0x4fe6  ldloc.s  0xD
0x4fe8  box      [mscorlib]System.Int32
0x4fed  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0x4ff2  ldstr    aName// "Name"
0x4ff7  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0x4ffc  callvirt instance string [mscorlib]System.Object::ToString()
0x5001  ldloc.s  0xB
0x5003  ldloc.s  0xD
0x5005  box      [mscorlib]System.Int32
0x500a  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0x500f  callvirt instance string [mscorlib]System.Object::ToString()
0x5014  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x5019  ldloc.s  0xD
0x501b  ldc.i4.1
0x501c  add
0x501d  stloc.s  0xD
0x501f  ldloc.s  0xD
0x5021  ldloc.s  9
0x5023  call     T0x2B00007D
0x5028  blt.s    loc_4FDD
0x502a  ldloc.s  6
0x502c  ldloc.s  0xC
0x502e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetRow>::Add(var<u1>)
0x5033  ldloc.s  0xA
0x5035  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x503a  brtrue.s loc_4FBD
0x503c  leave.s  loc_504A
0x503e  ldloc.s  0xA
0x5040  brfalse.s loc_5049
0x5042  ldloc.s  0xA
0x5044  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5049  endfinally
0x504a  ldarg.0
0x504b  ldloc.s  6
0x504d  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::CreateOk(object)
0x5052  ret
```
