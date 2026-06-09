# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::PbiParse

- ea: `0xa900`
- end: `0xab79`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::PbiParse`
- size: `633`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x9fb0`
- `0x9fc0`
- `0xa900`
- `0xacd0`
- `0xae50`
- `0xaea0`
- `0xaf10`

## string_xrefs

- `0xa97d`: `application/json`
- `0xa924`: `Content temp file doesn't exist`

## pseudocode

```c

```

## disassembly

```asm
0xa900  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0xa905  ldc.i4.8
0xa906  stloc.s  5
0xa908  ldloca.s 5
0xa90a  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0xa910  callvirt instance string [mscorlib]System.Object::ToString()
0xa915  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrException(string)
0xa91a  conv.r8
0xa91b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xa920  stloc.0
0xa921  ldarg.2
0xa922  brtrue.s loc_A92F
0xa924  ldstr    aContentTempFil// "Content temp file doesn't exist"
0xa929  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa92e  throw
0xa92f  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::GetFromCallContext()
0xa934  stloc.1
0xa935  ldstr    a0ApiReportprop_0// "{0}/api/reportpropertiesfromlocalfiles"
0xa93a  ldarg.3
0xa93b  call     string [mscorlib]System.String::Format(string, object)
0xa940  stloc.2
0xa941  ldarg.s  4
0xa943  ldc.i4.4
0xa944  ldstr    aParsingDatasou// "Parsing DataSources for file {0}, using"...
0xa949  ldarg.2
0xa94a  callvirt instance string [mscorlib]System.Object::ToString()
0xa94f  ldloc.2
0xa950  call     string [mscorlib]System.String::Format(string, object, object)
0xa955  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xa95a  ldloc.2
0xa95b  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0xa960  castclass [System]System.Net.HttpWebRequest
0xa965  stloc.3
0xa966  ldloc.3
0xa967  ldarg.s  5
0xa969  ldarg.s  6
0xa96b  call     class [System]System.Net.HttpWebRequest [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::PrepareWebRequestWithCorrespondingAuthMechanism(class [System]System.Net.HttpWebRequest, class [mscorlib]System.Security.Principal.IPrincipal, string)
0xa970  stloc.3
0xa971  ldloc.3
0xa972  ldstr    aPost// "POST"
0xa977  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0xa97c  ldloc.3
0xa97d  ldstr    aApplicationJso// "application/json"
0xa982  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0xa987  ldloc.3
0xa988  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xa98d  ldstr    aRequestid// "RequestId"
0xa992  ldloc.1
0xa993  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_RequestID()
0xa998  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xa99d  ldloc.3
0xa99e  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xa9a3  ldstr    aXSsrsClientses// "X-SSRS-ClientSessionId"
0xa9a8  ldloc.1
0xa9a9  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_ClientSessionID()
0xa9ae  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xa9b3  ldloc.3
0xa9b4  ldloca.s 0
0xa9b6  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa9bb  conv.i4
0xa9bc  callvirt instance void [System]System.Net.HttpWebRequest::set_ReadWriteTimeout(int32)
0xa9c1  ldloc.3
0xa9c2  ldloca.s 0
0xa9c4  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa9c9  conv.i4
0xa9ca  callvirt instance void [System]System.Net.WebRequest::set_Timeout(int32)
0xa9cf  ldarg.2
0xa9d0  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0xa9d5  stloc.s  4
0xa9d7  ldloc.3
0xa9d8  ldloc.s  4
0xa9da  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa9df  conv.i8
0xa9e0  callvirt instance void [System]System.Net.WebRequest::set_ContentLength(int64)
0xa9e5  ldloc.3
0xa9e6  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0xa9eb  stloc.s  6
0xa9ed  ldloc.s  6
0xa9ef  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0xa9f4  stloc.s  7
0xa9f6  ldloc.s  7
0xa9f8  ldloc.s  4
0xa9fa  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa9ff  leave.s  loc_AA19
0xaa01  ldloc.s  7
0xaa03  brfalse.s loc_AA0C
0xaa05  ldloc.s  7
0xaa07  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaa0c  endfinally
0xaa0d  ldloc.s  6
0xaa0f  brfalse.s loc_AA18
0xaa11  ldloc.s  6
0xaa13  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaa18  endfinally
0xaa19  ldloc.3
0xaa1a  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0xaa1f  castclass [System]System.Net.HttpWebResponse
0xaa24  dup
0xaa25  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0xaa2a  ldc.i4   0xC8
0xaa2f  beq.s    loc_AA42
0xaa31  ldstr    aFailedToCallPb_0// "Failed to call PBI Web API: "
0xaa36  ldloc.2
0xaa37  call     string [mscorlib]System.String::Concat(string, string)
0xaa3c  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xaa41  throw
0xaa42  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0xaa47  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xaa4c  stloc.s  8
0xaa4e  ldloc.s  8
0xaa50  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xaa55  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xaa5a  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0xaa5f  dup
0xaa60  ldstr    aStatuscode// "StatusCode"
0xaa65  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xaa6a  callvirt T0x2B0000DC
0xaa6f  stloc.s  9
0xaa71  ldstr    aBody// "Body"
0xaa76  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xaa7b  callvirt instance string [mscorlib]System.Object::ToString()
0xaa80  stloc.s  0xA
0xaa82  ldloc.s  9
0xaa84  ldc.i4   0xC8
0xaa89  bne.un   loc_AB1F
0xaa8e  ldloc.s  0xA
0xaa90  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xaa95  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0xaa9a  stloc.s  0xC
0xaa9c  ldloc.s  0xC
0xaa9e  ldstr    aProperties// "Properties"
0xaaa3  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xaaa8  callvirt instance string [mscorlib]System.Object::ToString()
0xaaad  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xaab2  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0xaab7  stloc.s  0xD
0xaab9  ldarg.1
0xaaba  ldloc.s  0xD
0xaabc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty> [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Properties()
0xaac1  ldsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <>c::<>9__21_0
0xaac6  dup
0xaac7  brtrue.s loc_AAE0
0xaac9  pop
0xaaca  ldsfld   class <>c <>c::<>9
0xaacf  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property <>c::<PbiParse>b__21_0(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty p)
0xaad5  newobj   instance void class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor(object, native int)
0xaada  dup
0xaadb  stsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <>c::<>9__21_0
0xaae0  call     T0x2B0000DE
0xaae5  call     T0x2B0000DF
0xaaea  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Properties(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0xaaef  ldarg.1
0xaaf0  ldarg.0
0xaaf1  ldloc.s  0xC
0xaaf3  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataModelParameters(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject bodyJObj)
0xaaf8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::set_DataModelParameters(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>)
0xaafd  ldarg.0
0xaafe  ldarg.1
0xaaff  ldloc.s  0xC
0xab01  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataSources(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject bodyJObj)
0xab06  ldarg.0
0xab07  ldarg.1
0xab08  ldloc.s  0xC
0xab0a  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataModelRoles(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject bodyJObj)
0xab0f  ldarg.0
0xab10  ldarg.1
0xab11  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DetermineIsModelRefreshAllowed(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity)
0xab16  call     class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::RenderingSupported()
0xab1b  stloc.s  0xE
0xab1d  leave.s  loc_AB76
0xab1f  ldc.i4.0
0xab20  stloc.s  0xB
0xab22  ldloc.s  9
0xab24  stloc.s  0xF
0xab26  ldloc.s  0xF
0xab28  ldc.i4   0x191
0xab2d  beq.s    loc_AB41
0xab2f  ldloc.s  0xF
0xab31  ldc.i4   0x1CE
0xab36  bne.un.s loc_AB46
0xab38  ldc.i4   0x1CE
0xab3d  stloc.s  0xB
0xab3f  br.s     loc_AB5D
0xab41  ldc.i4.1
0xab42  stloc.s  0xB
0xab44  br.s     loc_AB5D
0xab46  ldstr    aIsformatsuppor// "isformatsupported call returned unkown "...
0xab4b  ldloc.s  9
0xab4d  box      [System]System.Net.HttpStatusCode
0xab52  call     string [mscorlib]System.String::Format(string, object)
0xab57  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xab5c  throw
0xab5d  ldloc.s  0xB
0xab5f  ldloc.s  0xA
0xab61  call     class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::RenderingUnsupported(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode errorCode, string errorMessage)
0xab66  stloc.s  0xE
0xab68  leave.s  loc_AB76
0xab6a  ldloc.s  8
0xab6c  brfalse.s loc_AB75
0xab6e  ldloc.s  8
0xab70  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xab75  endfinally
0xab76  ldloc.s  0xE
0xab78  ret
```
