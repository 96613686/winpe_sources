# Microsoft.SharePoint.Client.Rest.RestService::HandleRestException

- ea: `0x271f0`
- end: `0x274e7`
- name: `Microsoft.SharePoint.Client.Rest.RestService::HandleRestException`
- size: `759`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x206e0`
- `0x267f0`

## callees

- `0x4d50`
- `0x8860`
- `0xac90`
- `0xe000`
- `0xe010`
- `0xe080`
- `0xe580`
- `0xe810`
- `0xe830`
- `0xe850`
- `0xe8b0`
- `0xe8d0`
- `0xe8f0`
- `0xe910`
- `0xe930`
- `0xe950`
- `0xe970`
- `0xe990`
- `0xe9b0`
- `0xebb0`
- `0xebf0`
- `0x18af0`
- `0x1eea0`
- `0x20100`
- `0x21bc0`
- `0x21c50`
- `0x21c60`
- `0x21c80`
- `0x21ca0`
- `0x21ce0`
- `0x26780`
- `0x271f0`
- `0x27510`

## string_xrefs

- `0x27262`: `application/xml`
- `0x2738a`: `HandleRestException: ClientServiceOperationContext.Current is null`
- `0x2748b`: `[ErrorInformation.ErrorValue={0}] is an invalid Uri for HTTP status code {1}.`
- `0x274c1`: `ErrorInformation.ErrorValue has an empty Uri for HTTP status code {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x271f0  ldarg.0
0x271f1  ldc.i4   0x59E220
0x271f6  ldc.i4.2
0x271f7  ldstr    aRestexception0// "RestException={0}"
0x271fc  ldc.i4.1
0x271fd  newarr   [mscorlib]System.Object
0x27202  stloc.s  0xE
0x27204  ldloc.s  0xE
0x27206  ldc.i4.0
0x27207  ldarg.1
0x27208  stelem.ref
0x27209  ldloc.s  0xE
0x2720b  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x27210  ldarg.1
0x27211  ldarg.0
0x27212  call     class Microsoft.SharePoint.Client.ErrorInformation Microsoft.SharePoint.Client.ClientMethodsProcessor::GetErrorInformation(class [mscorlib]System.Exception ex, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x27217  stloc.0
0x27218  ldarg.0
0x27219  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x2721e  stloc.1
0x2721f  newobj   instance void Microsoft.SharePoint.Utilities.ChunkStreamBuilder::.ctor()
0x27224  stloc.2
0x27225  ldloc.2
0x27226  newobj   instance void Microsoft.SharePoint.Client.Rest.OutputChunkStream::.ctor(class Microsoft.SharePoint.Utilities.ChunkStreamBuilder sb)
0x2722b  stloc.3
0x2722c  ldloc.3
0x2722d  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27232  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.IncomingWebRequestContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_IncomingRequest()
0x27237  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.IncomingWebRequestContext::get_Headers()
0x2723c  ldc.i4.s 0x14
0x2723e  callvirt instance string [System]System.Net.WebHeaderCollection::get_Item(valuetype [System]System.Net.HttpRequestHeader)
0x27243  ldloc.1
0x27244  ldnull
0x27245  ldc.i4.s 0xA
0x27247  ldarg.0
0x27248  ldnull
0x27249  ldloca.s 4
0x2724b  call     class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.RestService::CreateODataMessageWriter(class [mscorlib]System.IO.Stream stream, string orginalAcceptHeaderValue, class [System]System.Uri serviceBaseUri, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel edmModel, valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataPayloadKind payloadKind, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class Microsoft.SharePoint.Client.RESTfulQuery query, [out] class Microsoft.SharePoint.Client.Rest.RestResponseMessage& responseMessage)
0x27250  stloc.s  5
0x27252  leave.s  loc_27278
0x27254  stloc.s  6
0x27256  ldloc.s  6
0x27258  call     bool Microsoft.SharePoint.Client.Utility::FIsFatalException(class [mscorlib]System.Exception e)
0x2725d  brfalse.s loc_27261
0x2725f  rethrow
0x27261  ldloc.3
0x27262  ldstr    aApplicationXml// "application/xml"
0x27267  ldloc.1
0x27268  ldnull
0x27269  ldc.i4.s 0xA
0x2726b  ldarg.0
0x2726c  ldnull
0x2726d  ldloca.s 4
0x2726f  call     class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.RestService::CreateODataMessageWriter(class [mscorlib]System.IO.Stream stream, string orginalAcceptHeaderValue, class [System]System.Uri serviceBaseUri, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel edmModel, valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataPayloadKind payloadKind, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class Microsoft.SharePoint.Client.RESTfulQuery query, [out] class Microsoft.SharePoint.Client.Rest.RestResponseMessage& responseMessage)
0x27274  stloc.s  5
0x27276  leave.s  loc_27278
0x27278  ldloc.0
0x27279  callvirt instance string Microsoft.SharePoint.Client.ErrorInformation::get_Message()
0x2727e  stloc.s  7
0x27280  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataError::.ctor()
0x27285  stloc.s  8
0x27287  ldloc.s  8
0x27289  ldloc.s  7
0x2728b  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataError::set_Message(string)
0x27290  ldloc.s  8
0x27292  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x27297  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x2729c  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataError::set_MessageLanguage(string)
0x272a1  ldloc.s  8
0x272a3  ldarg.1
0x272a4  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataInnerError::.ctor(class [mscorlib]System.Exception)
0x272a9  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataError::set_InnerError(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInnerError)
0x272ae  ldloc.0
0x272af  callvirt instance string Microsoft.SharePoint.Client.ErrorInformation::get_RESTfulErrorCode()
0x272b4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x272b9  brtrue.s loc_272CA
0x272bb  ldloc.s  8
0x272bd  ldloc.0
0x272be  callvirt instance string Microsoft.SharePoint.Client.ErrorInformation::get_RESTfulErrorCode()
0x272c3  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataError::set_ErrorCode(string)
0x272c8  br.s     loc_272F5
0x272ca  ldloc.s  8
0x272cc  ldloc.0
0x272cd  callvirt instance int32 Microsoft.SharePoint.Client.ErrorInformation::get_ErrorCode()
0x272d2  stloc.s  0xF
0x272d4  ldloca.s 0xF
0x272d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x272db  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x272e0  ldstr    asc_40BB2// ", "
0x272e5  ldloc.0
0x272e6  callvirt instance string Microsoft.SharePoint.Client.ErrorInformation::get_ErrorTypeName()
0x272eb  call     string [mscorlib]System.String::Concat(string, string, string)
0x272f0  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataError::set_ErrorCode(string)
0x272f5  ldloc.0
0x272f6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ErrorInstanceAnnotation> Microsoft.SharePoint.Client.ErrorInformation::get_InstanceAnnotations()
0x272fb  brfalse  loc_27394
0x27300  call     class Microsoft.SharePoint.Client.ClientServiceOperationContext Microsoft.SharePoint.Client.ClientServiceOperationContext::get_Current()
0x27305  stloc.s  9
0x27307  ldloc.s  9
0x27309  brfalse.s loc_27383
0x2730b  ldloc.0
0x2730c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ErrorInstanceAnnotation> Microsoft.SharePoint.Client.ErrorInformation::get_InstanceAnnotations()
0x27311  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ErrorInstanceAnnotation>::GetEnumerator()
0x27316  stloc.s  0x10
0x27318  br.s     loc_2736C
0x2731a  ldloc.s  0x10
0x2731c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.ErrorInstanceAnnotation>::get_Current()
0x27321  stloc.s  0xA
0x27323  ldloc.s  0xA
0x27325  callvirt instance string Microsoft.SharePoint.Client.ErrorInstanceAnnotation::get_Namespace()
0x2732a  ldc.i4.s 0x2E
0x2732c  box      [mscorlib]System.Char
0x27331  ldloc.s  0xA
0x27333  callvirt instance string Microsoft.SharePoint.Client.ErrorInstanceAnnotation::get_Name()
0x27338  call     string [mscorlib]System.String::Concat(object, object, object)
0x2733d  ldloc.s  0xA
0x2733f  callvirt instance object Microsoft.SharePoint.Client.ErrorInstanceAnnotation::get_Value()
0x27344  ldloc.s  9
0x27346  callvirt instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientServiceOperationContext::get_ProxyContext()
0x2734b  ldc.i4.0
0x2734c  ldc.i4.1
0x2734d  call     object Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::ToODataValue(object value, class Microsoft.SharePoint.Client.ProxyContext proxyContext, bool ignoreNullPropertiesFromResponse, [opt] bool wrapPrimitives)
0x27352  castclass [Microsoft.Data.OData]Microsoft.Data.OData.ODataValue
0x27357  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation::.ctor(string, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataValue)
0x2735c  stloc.s  0xB
0x2735e  ldloc.s  8
0x27360  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation> [Microsoft.Data.OData]Microsoft.Data.OData.ODataError::get_InstanceAnnotations()
0x27365  ldloc.s  0xB
0x27367  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x2736c  ldloc.s  0x10
0x2736e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27373  brtrue.s loc_2731A
0x27375  leave.s  loc_27394
0x27377  ldloc.s  0x10
0x27379  brfalse.s loc_27382
0x2737b  ldloc.s  0x10
0x2737d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27382  endfinally
0x27383  ldarg.0
0x27384  ldc.i4   0x170C192
0x27389  ldc.i4.2
0x2738a  ldstr    aHandlerestexce// "HandleRestException: ClientServiceOpera"...
0x2738f  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x27394  ldloc.s  5
0x27396  ldloc.s  8
0x27398  ldarg.0
0x27399  callvirt instance class Microsoft.SharePoint.Client.ClientCallableSettings Microsoft.SharePoint.Client.ClientServiceHost::get_ClientCallableSettings()
0x2739e  callvirt instance bool Microsoft.SharePoint.Client.ClientCallableSettings::get_EnableStackTrace()
0x273a3  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::WriteError(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataError, bool)
0x273a8  ldloc.3
0x273a9  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x273ae  ldloc.s  4
0x273b0  callvirt instance string Microsoft.SharePoint.Client.Rest.RestResponseMessage::GetContentType()
0x273b5  ldloc.2
0x273b6  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x273bb  stloc.s  0xC
0x273bd  ldloc.s  0xC
0x273bf  ldloc.0
0x273c0  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.ErrorInformation::get_HttpStatusCode()
0x273c5  stloc.s  0x11
0x273c7  ldloca.s 0x11
0x273c9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_Value()
0x273ce  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0x273d3  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_StatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0x273d8  ldloc.s  0xC
0x273da  ldloc.0
0x273db  callvirt instance string Microsoft.SharePoint.Client.ErrorInformation::get_HttpStatusDescriptionOverride()
0x273e0  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_StatusDescriptionOverride(string value)
0x273e5  call     class [Microsoft.SharePoint.KillSwitch]Microsoft.SharePoint.Internal.IKillSwitch [Microsoft.SharePoint.KillSwitch]Microsoft.SharePoint.Internal.KillSwitch::get_Instance()
0x273ea  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Client.Rest.RestService::AdditionalHeadersKillSwitchId
0x273ef  ldstr    a1102018// "1/10/2018"
0x273f4  ldstr    aAdditionalhead// "AdditionalHeadersKillSwitchId"
0x273f9  callvirt instance bool [Microsoft.SharePoint.KillSwitch]Microsoft.SharePoint.Internal.IKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x273fe  brtrue.s loc_2740D
0x27400  ldloc.s  0xC
0x27402  ldloc.0
0x27403  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.ErrorInformation::get_AdditionalHeaders()
0x27408  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_AdditionalHeaders(class [System]System.Collections.Specialized.NameValueCollection value)
0x2740d  ldloc.s  0xC
0x2740f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.RestRequestResult::get_StatusCode()
0x27414  stloc.s  0x12
0x27416  ldloca.s 0x12
0x27418  dup
0x27419  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::GetValueOrDefault()
0x2741e  stloc.s  0x13
0x27420  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_HasValue()
0x27425  brfalse  loc_274E4
0x2742a  ldloc.s  0x13
0x2742c  ldc.i4   0x12D
0x27431  sub
0x27432  switch   loc_2745C, loc_2745C, loc_2745C, loc_274E4, loc_274E4, loc_274E4, loc_2745C, loc_2745C
0x27457  br       loc_274E4
0x2745c  ldloc.0
0x2745d  callvirt instance string Microsoft.SharePoint.Client.ErrorInformation::get_ErrorValue()
0x27462  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x27467  brtrue.s loc_274BA
0x27469  ldloc.0
0x2746a  callvirt instance string Microsoft.SharePoint.Client.ErrorInformation::get_ErrorValue()
0x2746f  ldc.i4.0
0x27470  ldloca.s 0xD
0x27472  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x27477  brfalse.s loc_27484
0x27479  ldloc.s  0xC
0x2747b  ldloc.s  0xD
0x2747d  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_Location(class [System]System.Uri value)
0x27482  br.s     loc_274E4
0x27484  ldarg.0
0x27485  ldc.i4   0x8D6490
0x2748a  ldc.i4.1
0x2748b  ldstr    aErrorinformati_0// "[ErrorInformation.ErrorValue={0}] is an"...
0x27490  ldc.i4.2
0x27491  newarr   [mscorlib]System.Object
0x27496  stloc.s  0x14
0x27498  ldloc.s  0x14
0x2749a  ldc.i4.0
0x2749b  ldloc.0
0x2749c  callvirt instance string Microsoft.SharePoint.Client.ErrorInformation::get_ErrorValue()
0x274a1  stelem.ref
0x274a2  ldloc.s  0x14
0x274a4  ldc.i4.1
0x274a5  ldloc.0
0x274a6  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.ErrorInformation::get_HttpStatusCode()
0x274ab  box      valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>
0x274b0  stelem.ref
0x274b1  ldloc.s  0x14
0x274b3  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x274b8  br.s     loc_274E4
0x274ba  ldarg.0
0x274bb  ldc.i4   0x8D6491
0x274c0  ldc.i4.1
0x274c1  ldstr    aErrorinformati_1// "ErrorInformation.ErrorValue has an empt"...
0x274c6  ldc.i4.1
0x274c7  newarr   [mscorlib]System.Object
0x274cc  stloc.s  0x15
0x274ce  ldloc.s  0x15
0x274d0  ldc.i4.0
0x274d1  ldloc.0
0x274d2  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.ErrorInformation::get_HttpStatusCode()
0x274d7  box      valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>
0x274dc  stelem.ref
0x274dd  ldloc.s  0x15
0x274df  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x274e4  ldloc.s  0xC
0x274e6  ret
```
