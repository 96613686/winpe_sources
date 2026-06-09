# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::ShouldReShred

- ea: `0xa4c0`
- end: `0xa66d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::ShouldReShred`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xa4c0`

## string_xrefs

- `0xa4d8`: `{0}/api/servicestate`
- `0xa4e7`: `Getting service state using: {0}`
- `0xa52f`: `Failed to call PBIX servicestate API`

## pseudocode

```c

```

## disassembly

```asm
0xa4c0  ldsflda  float64 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::ShredderVersion
0xa4c5  ldc.r8   0.0
0xa4ce  call     instance bool [mscorlib]System.Double::Equals(float64)
0xa4d3  brfalse  loc_A5A0
0xa4d8  ldstr    a0ApiServicesta// "{0}/api/servicestate"
0xa4dd  ldarg.2
0xa4de  call     string [mscorlib]System.String::Format(string, object)
0xa4e3  stloc.s  4
0xa4e5  ldarg.3
0xa4e6  ldc.i4.4
0xa4e7  ldstr    aGettingService// "Getting service state using: {0}"
0xa4ec  ldloc.s  4
0xa4ee  call     string [mscorlib]System.String::Format(string, object)
0xa4f3  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xa4f8  ldloc.s  4
0xa4fa  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0xa4ff  castclass [System]System.Net.HttpWebRequest
0xa504  ldarg.s  4
0xa506  ldarg.s  5
0xa508  call     class [System]System.Net.HttpWebRequest [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::PrepareWebRequestWithCorrespondingAuthMechanism(class [System]System.Net.HttpWebRequest, class [mscorlib]System.Security.Principal.IPrincipal, string)
0xa50d  dup
0xa50e  ldstr    aGet// "GET"
0xa513  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0xa518  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0xa51d  castclass [System]System.Net.HttpWebResponse
0xa522  dup
0xa523  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0xa528  ldc.i4   0xC8
0xa52d  beq.s    loc_A53A
0xa52f  ldstr    aFailedToCallPb// "Failed to call PBIX servicestate API"
0xa534  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xa539  throw
0xa53a  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0xa53f  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xa544  stloc.s  5
0xa546  ldloc.s  5
0xa548  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xa54d  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xa552  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0xa557  stloc.s  6
0xa559  ldloc.s  6
0xa55b  ldstr    aPbixshredderve// "PbixShredderVersion"
0xa560  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xa565  callvirt instance string [mscorlib]System.Object::ToString()
0xa56a  ldsflda  float64 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::ShredderVersion
0xa56f  call     bool [mscorlib]System.Double::TryParse(string, float64&)
0xa574  brtrue.s loc_A592
0xa576  ldstr    aPbixServerRetu// "PBIX Server returned unexpected data fo"...
0xa57b  ldloc.s  6
0xa57d  ldstr    aPbixshredderve// "PbixShredderVersion"
0xa582  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xa587  call     string [mscorlib]System.String::Format(string, object)
0xa58c  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xa591  throw
0xa592  leave.s  loc_A5A0
0xa594  ldloc.s  5
0xa596  brfalse.s loc_A59F
0xa598  ldloc.s  5
0xa59a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa59f  endfinally
0xa5a0  ldc.r8   0.0
0xa5a9  stloc.0
0xa5aa  ldarg.1
0xa5ab  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0xa5b0  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__19_0
0xa5b5  dup
0xa5b6  brtrue.s loc_A5CF
0xa5b8  pop
0xa5b9  ldsfld   class <>c <>c::<>9
0xa5be  ldftn    instance bool <>c::<ShouldReShred>b__19_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property p)
0xa5c4  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0xa5c9  dup
0xa5ca  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__19_0
0xa5cf  call     T0x2B000064
0xa5d4  stloc.1
0xa5d5  ldloc.1
0xa5d6  brfalse.s loc_A5FD
0xa5d8  ldloc.1
0xa5d9  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0xa5de  ldloca.s 0
0xa5e0  call     bool [mscorlib]System.Double::TryParse(string, float64&)
0xa5e5  brtrue.s loc_A5FD
0xa5e7  ldstr    aPbixCatalogIte// "PBIX Catalog item has unexpected data f"...
0xa5ec  ldstr    aPbixshredderve// "PbixShredderVersion"
0xa5f1  ldloc.1
0xa5f2  call     string [mscorlib]System.String::Format(string, object, object)
0xa5f7  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xa5fc  throw
0xa5fd  ldc.i4.0
0xa5fe  stloc.2
0xa5ff  ldarg.1
0xa600  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0xa605  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__19_1
0xa60a  dup
0xa60b  brtrue.s loc_A624
0xa60d  pop
0xa60e  ldsfld   class <>c <>c::<>9
0xa613  ldftn    instance bool <>c::<ShouldReShred>b__19_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property p)
0xa619  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0xa61e  dup
0xa61f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__19_1
0xa624  call     T0x2B000064
0xa629  stloc.3
0xa62a  ldloc.3
0xa62b  brfalse.s loc_A652
0xa62d  ldloc.3
0xa62e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0xa633  ldloca.s 2
0xa635  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0xa63a  brtrue.s loc_A652
0xa63c  ldstr    aPbixCatalogIte// "PBIX Catalog item has unexpected data f"...
0xa641  ldstr    aHasembeddedmod// "HasEmbeddedModels"
0xa646  ldloc.3
0xa647  call     string [mscorlib]System.String::Format(string, object, object)
0xa64c  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xa651  throw
0xa652  ldloc.0
0xa653  ldc.r8   3.0
0xa65c  clt
0xa65e  ldloc.2
0xa65f  and
0xa660  brfalse.s loc_A664
0xa662  ldc.i4.0
0xa663  ret
0xa664  ldsfld   float64 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::ShredderVersion
0xa669  ldloc.0
0xa66a  cgt
0xa66c  ret
```
