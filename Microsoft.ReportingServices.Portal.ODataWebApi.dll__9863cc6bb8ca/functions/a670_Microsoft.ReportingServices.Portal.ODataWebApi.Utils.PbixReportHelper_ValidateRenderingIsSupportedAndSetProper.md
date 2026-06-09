# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::ValidateRenderingIsSupportedAndSetProperties

- ea: `0xa670`
- end: `0xa8f8`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::ValidateRenderingIsSupportedAndSetProperties`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x9fb0`
- `0x9fc0`
- `0xa670`
- `0xacd0`
- `0xae50`
- `0xaea0`
- `0xaf10`

## pseudocode

```c

```

## disassembly

```asm
0xa670  ldarg.1
0xa671  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::HasContent()
0xa676  brtrue.s loc_A683
0xa678  ldstr    aEntityDoesNotH// "entity does not have content"
0xa67d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa682  throw
0xa683  ldarg.1
0xa684  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetContentStream()
0xa689  stloc.0
0xa68a  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::GetFromCallContext()
0xa68f  stloc.1
0xa690  ldstr    a0ApiReportprop// "{0}/api/reportproperties"
0xa695  ldarg.2
0xa696  call     string [mscorlib]System.String::Format(string, object)
0xa69b  stloc.2
0xa69c  ldarg.3
0xa69d  ldc.i4.4
0xa69e  ldstr    aGettingReportP// "Getting report properties if pbix file "...
0xa6a3  ldloc.2
0xa6a4  call     string [mscorlib]System.String::Format(string, object)
0xa6a9  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xa6ae  ldloc.2
0xa6af  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0xa6b4  castclass [System]System.Net.HttpWebRequest
0xa6b9  ldarg.s  4
0xa6bb  ldarg.s  5
0xa6bd  call     class [System]System.Net.HttpWebRequest [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::PrepareWebRequestWithCorrespondingAuthMechanism(class [System]System.Net.HttpWebRequest, class [mscorlib]System.Security.Principal.IPrincipal, string)
0xa6c2  ldloc.0
0xa6c3  brtrue.s loc_A6CF
0xa6c5  ldarg.1
0xa6c6  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0xa6cb  ldlen
0xa6cc  conv.i4
0xa6cd  br.s     loc_A6D6
0xa6cf  ldloc.0
0xa6d0  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0xa6d5  conv.i4
0xa6d6  stloc.3
0xa6d7  dup
0xa6d8  ldstr    aPost// "POST"
0xa6dd  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0xa6e2  dup
0xa6e3  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0xa6e8  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0xa6ed  dup
0xa6ee  ldloc.3
0xa6ef  conv.i8
0xa6f0  callvirt instance void [System]System.Net.WebRequest::set_ContentLength(int64)
0xa6f5  dup
0xa6f6  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xa6fb  ldstr    aRequestid// "RequestId"
0xa700  ldloc.1
0xa701  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_RequestID()
0xa706  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xa70b  dup
0xa70c  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xa711  ldstr    aXSsrsClientses// "X-SSRS-ClientSessionId"
0xa716  ldloc.1
0xa717  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_ClientSessionID()
0xa71c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xa721  dup
0xa722  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0xa727  stloc.s  4
0xa729  ldloc.0
0xa72a  brfalse.s loc_A736
0xa72c  ldloc.0
0xa72d  ldloc.s  4
0xa72f  callvirt instance void [mscorlib]System.IO.Stream::CopyTo(class [mscorlib]System.IO.Stream)
0xa734  br.s     loc_A745
0xa736  ldloc.s  4
0xa738  ldarg.1
0xa739  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0xa73e  ldc.i4.0
0xa73f  ldloc.3
0xa740  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0xa745  ldloc.s  4
0xa747  callvirt instance void [mscorlib]System.IO.Stream::Close()
0xa74c  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0xa751  castclass [System]System.Net.HttpWebResponse
0xa756  dup
0xa757  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0xa75c  ldc.i4   0xC8
0xa761  beq.s    loc_A76E
0xa763  ldstr    aFailedToCallRe// "Failed to call reportproperties API"
0xa768  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xa76d  throw
0xa76e  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0xa773  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xa778  stloc.s  5
0xa77a  ldloc.s  5
0xa77c  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xa781  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xa786  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0xa78b  dup
0xa78c  ldstr    aStatuscode// "StatusCode"
0xa791  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xa796  callvirt T0x2B0000DC
0xa79b  stloc.s  6
0xa79d  ldstr    aBody// "Body"
0xa7a2  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xa7a7  callvirt instance string [mscorlib]System.Object::ToString()
0xa7ac  stloc.s  7
0xa7ae  ldloc.s  6
0xa7b0  ldc.i4   0xC8
0xa7b5  bne.un   loc_A89E
0xa7ba  ldloc.s  7
0xa7bc  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xa7c1  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0xa7c6  stloc.s  9
0xa7c8  ldloc.s  9
0xa7ca  ldstr    aProperties// "Properties"
0xa7cf  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xa7d4  callvirt instance string [mscorlib]System.Object::ToString()
0xa7d9  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xa7de  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0xa7e3  stloc.s  0xA
0xa7e5  ldloc.s  0xA
0xa7e7  ldstr    aDatamodel// "DataModel"
0xa7ec  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xa7f1  brfalse.s loc_A838
0xa7f3  ldloc.s  0xA
0xa7f5  ldstr    aDatamodel// "DataModel"
0xa7fa  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xa7ff  call     T0x2B0000DD
0xa804  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa809  brtrue.s loc_A82B
0xa80b  ldloc.s  0xA
0xa80d  ldstr    aDatamodel// "DataModel"
0xa812  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xa817  call     unsigned int8[] [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::op_Explicit(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0xa81c  stloc.s  0xB
0xa81e  ldarg.1
0xa81f  ldloc.s  0xB
0xa821  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0xa826  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::SetModelStream(class [mscorlib]System.IO.Stream)
0xa82b  ldloc.s  0xA
0xa82d  ldstr    aDatamodel// "DataModel"
0xa832  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Remove(string)
0xa837  pop
0xa838  ldarg.1
0xa839  ldloc.s  0xA
0xa83b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty> [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Properties()
0xa840  ldsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <>c::<>9__20_0
0xa845  dup
0xa846  brtrue.s loc_A85F
0xa848  pop
0xa849  ldsfld   class <>c <>c::<>9
0xa84e  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property <>c::<ValidateRenderingIsSupportedAndSetProperties>b__20_0(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty p)
0xa854  newobj   instance void class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor(object, native int)
0xa859  dup
0xa85a  stsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <>c::<>9__20_0
0xa85f  call     T0x2B0000DE
0xa864  call     T0x2B0000DF
0xa869  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Properties(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0xa86e  ldarg.1
0xa86f  ldarg.0
0xa870  ldloc.s  9
0xa872  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataModelParameters(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject bodyJObj)
0xa877  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::set_DataModelParameters(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>)
0xa87c  ldarg.0
0xa87d  ldarg.1
0xa87e  ldloc.s  9
0xa880  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataSources(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject bodyJObj)
0xa885  ldarg.0
0xa886  ldarg.1
0xa887  ldloc.s  9
0xa889  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataModelRoles(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject bodyJObj)
0xa88e  ldarg.0
0xa88f  ldarg.1
0xa890  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DetermineIsModelRefreshAllowed(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity)
0xa895  call     class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::RenderingSupported()
0xa89a  stloc.s  0xC
0xa89c  leave.s  loc_A8F5
0xa89e  ldc.i4.0
0xa89f  stloc.s  8
0xa8a1  ldloc.s  6
0xa8a3  stloc.s  0xD
0xa8a5  ldloc.s  0xD
0xa8a7  ldc.i4   0x191
0xa8ac  beq.s    loc_A8C0
0xa8ae  ldloc.s  0xD
0xa8b0  ldc.i4   0x1CE
0xa8b5  bne.un.s loc_A8C5
0xa8b7  ldc.i4   0x1CE
0xa8bc  stloc.s  8
0xa8be  br.s     loc_A8DC
0xa8c0  ldc.i4.1
0xa8c1  stloc.s  8
0xa8c3  br.s     loc_A8DC
0xa8c5  ldstr    aIsformatsuppor// "isformatsupported call returned unkown "...
0xa8ca  ldloc.s  6
0xa8cc  box      [System]System.Net.HttpStatusCode
0xa8d1  call     string [mscorlib]System.String::Format(string, object)
0xa8d6  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xa8db  throw
0xa8dc  ldloc.s  8
0xa8de  ldloc.s  7
0xa8e0  call     class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::RenderingUnsupported(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode errorCode, string errorMessage)
0xa8e5  stloc.s  0xC
0xa8e7  leave.s  loc_A8F5
0xa8e9  ldloc.s  5
0xa8eb  brfalse.s loc_A8F4
0xa8ed  ldloc.s  5
0xa8ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa8f4  endfinally
0xa8f5  ldloc.s  0xC
0xa8f7  ret
```
