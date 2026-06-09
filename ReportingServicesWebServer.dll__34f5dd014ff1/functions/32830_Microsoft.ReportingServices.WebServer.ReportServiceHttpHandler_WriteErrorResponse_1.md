# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::WriteErrorResponse_1

- ea: `0x32830`
- end: `0x3297b`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::WriteErrorResponse_1`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x32730`
- `0x32760`

## callees

- `0x32830`
- `0x38cf0`
- `0x3c860`

## string_xrefs

- `0x3285a`: `reportServiceHandlerWriteError`

## pseudocode

```c

```

## disassembly

```asm
0x32830  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x32835  stloc.0
0x32836  ldloc.0
0x32837  ldstr    aShorthttpdescr// "shortHttpDescription"
0x3283c  ldarg.1
0x3283d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32842  ldloc.0
0x32843  ldstr    aCode// "code"
0x32848  ldarga.s 0
0x3284a  call     instance string [mscorlib]System.Int32::ToString()
0x3284f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32854  ldloc.0
0x32855  ldstr    aPath// "path"
0x3285a  ldstr    aReportserviceh_11// "reportServiceHandlerWriteError"
0x3285f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32864  ldarg.2
0x32865  brfalse.s loc_3287D
0x32867  ldloc.0
0x32868  ldstr    aExceptiontype// "exceptionType"
0x3286d  ldarg.2
0x3286e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x32873  callvirt instance string [mscorlib]System.Object::ToString()
0x32878  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3287d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x32882  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x32887  brfalse.s loc_328A0
0x32889  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x3288e  ldc.i4.1
0x3288f  ldstr    aRsServerHttpha// "RS.Server.HttpHandlerError"
0x32894  ldloc.0
0x32895  ldnull
0x32896  call     string [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Helpers.TelemetryUtils::GetSerializedEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>, class [mscorlib]System.Collections.Generic.IDictionary`2<string, float64>)
0x3289b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x328a0  call     class [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Interfaces.ITelemetryService [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Services.TelemetryService::get_Current()
0x328a5  ldstr    aRsServerHttpha// "RS.Server.HttpHandlerError"
0x328aa  ldloc.0
0x328ab  ldnull
0x328ac  callvirt instance void [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Interfaces.ITelemetryService::TrackEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>, class [mscorlib]System.Collections.Generic.IDictionary`2<string, float64>)
0x328b1  call     class [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Interfaces.ITelemetryService [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Services.TelemetryService::get_Current()
0x328b6  callvirt instance void [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Interfaces.ITelemetryService::FlushRequests()
0x328bb  ldc.i4.0
0x328bc  stloc.1
0x328bd  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x328c2  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x328c7  ldstr    aHeadersset// "HeadersSet"
0x328cc  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x328d1  brfalse.s loc_328D5
0x328d3  ldc.i4.1
0x328d4  stloc.1
0x328d5  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x328da  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x328df  ldarg.2
0x328e0  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x328e5  stloc.3
0x328e6  ldloc.3
0x328e7  brfalse.s loc_328FA
0x328e9  ldloc.3
0x328ea  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_SkipTopLevelMessage()
0x328ef  brfalse.s loc_328FA
0x328f1  ldloc.3
0x328f2  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x328f7  stloc.2
0x328f8  br.s     loc_328FC
0x328fa  ldarg.2
0x328fb  stloc.2
0x328fc  ldloc.2
0x328fd  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x32902  stloc.3
0x32903  ldarg.s  4
0x32905  brfalse.s loc_3291F
0x32907  ldloc.3
0x32908  brtrue.s loc_32912
0x3290a  ldloc.2
0x3290b  ldnull
0x3290c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x32911  stloc.3
0x32912  ldloc.3
0x32913  ldc.i4.0
0x32914  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::get_EnableRemoteErrors()
0x32919  call     class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ExceptionExtensions::WebServerToSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException, bool, bool)
0x3291e  stloc.2
0x3291f  ldloc.2
0x32920  ldloc.1
0x32921  ldarg.0
0x32922  ldarg.1
0x32923  ldloc.3
0x32924  brtrue.s loc_32929
0x32926  ldnull
0x32927  br.s     loc_3293E
0x32929  ldloc.3
0x3292a  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x3292f  stloc.s  4
0x32931  ldloca.s 4
0x32933  constrained. [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode
0x32939  callvirt instance string [mscorlib]System.Object::ToString()
0x3293e  call     string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductName()
0x32943  ldstr    asc_42244// " "
0x32948  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x3294d  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductVersion()
0x32952  call     string [mscorlib]System.String::Concat(string, string, string)
0x32957  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_CatalogCulture()
0x3295c  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x32961  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_ClientPrimaryCulture()
0x32966  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x3296b  ldarg.s  4
0x3296d  ldarg.3
0x3296e  ldarg.s  5
0x32970  newobj   instance void RSErrorResponseWriter::.ctor(class [System.Web]System.Web.HttpResponse response, class [mscorlib]System.Exception exception, bool responseFlushed, int32 httpStatusCode, string httpStatusDescription, string reportServerErrorCode, string generator, int32 productLocaleId, int32 countryLocaleId, bool errorResponseAsXml, string optionalMessage, class [System]System.Collections.Specialized.NameValueCollection additionalHeaders)
0x32975  callvirt instance void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteError()
0x3297a  ret
```
