# Microsoft.ReportingServices.Library.StreamRequestHandler::ExecuteQuery

- ea: `0x6be10`
- end: `0x6bfcd`
- name: `Microsoft.ReportingServices.Library.StreamRequestHandler::ExecuteQuery`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6b8c0`

## callees

- `0x1e510`
- `0x36500`
- `0x37810`
- `0x66250`
- `0x66300`
- `0x6adf0`
- `0x6aeb0`
- `0x6aef0`
- `0x6af00`
- `0x6af40`
- `0x6af90`
- `0x6be10`

## string_xrefs

- `0x6be32`: `rs:CommandText`
- `0x6be72`: `rs:CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x6be10  ldstr    aStreamrequesth_4// "StreamRequestHandler.ExecuteQuery"
0x6be15  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x6be1a  stloc.0
0x6be1b  ldarg.0
0x6be1c  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6be21  ldstr    aRsDatasourcena// "rs:DataSourceName"
0x6be26  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6be2b  stloc.1
0x6be2c  ldarg.0
0x6be2d  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6be32  ldstr    aRsCommandtext// "rs:CommandText"
0x6be37  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6be3c  stloc.2
0x6be3d  ldc.i4.0
0x6be3e  stloc.3
0x6be3f  ldarg.0
0x6be40  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6be45  ldstr    aRsGetusermodel// "rs:GetUserModel"
0x6be4a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6be4f  ldstr    aTrue_0// "True"
0x6be54  ldc.i4.5
0x6be55  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6be5a  brtrue.s loc_6BE5E
0x6be5c  ldc.i4.1
0x6be5d  stloc.3
0x6be5e  ldloc.1
0x6be5f  brtrue.s loc_6BE6C
0x6be61  ldstr    aRsDatasourcena// "rs:DataSourceName"
0x6be66  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x6be6b  throw
0x6be6c  ldloc.2
0x6be6d  brtrue.s loc_6BE7D
0x6be6f  ldloc.3
0x6be70  brtrue.s loc_6BE7D
0x6be72  ldstr    aRsCommandtext// "rs:CommandText"
0x6be77  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x6be7c  throw
0x6be7d  ldloc.2
0x6be7e  brfalse  loc_6BF4D
0x6be83  ldc.i4.s 0x78
0x6be85  stloc.s  5
0x6be87  ldarg.0
0x6be88  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6be8d  ldstr    aRsTimeout// "rs:Timeout"
0x6be92  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6be97  stloc.s  6
0x6be99  ldloc.s  6
0x6be9b  brfalse.s loc_6BEB3
0x6be9d  ldloc.s  6
0x6be9f  ldloca.s 5
0x6bea1  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x6bea6  brtrue.s loc_6BEB3
0x6bea8  ldstr    aRsTimeout// "rs:Timeout"
0x6bead  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x6beb2  throw
0x6beb3  ldarg.0
0x6beb4  callvirt instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.StreamRequestHandler::get_Tracer()
0x6beb9  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x6bebe  brfalse.s loc_6BEDB
0x6bec0  ldarg.0
0x6bec1  callvirt instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.StreamRequestHandler::get_Tracer()
0x6bec6  ldc.i4.3
0x6bec7  ldstr    aCallToExecuteq// "Call to ExecuteQuery. DataSource='{0}'"
0x6becc  ldc.i4.1
0x6becd  newarr   [mscorlib]System.Object
0x6bed2  dup
0x6bed3  ldc.i4.0
0x6bed4  ldloc.1
0x6bed5  stelem.ref
0x6bed6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6bedb  ldc.i4.0
0x6bedc  newarr   [mscorlib]System.Boolean
0x6bee1  stloc.s  8
0x6bee3  ldarg.0
0x6bee4  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6bee9  ldloca.s 8
0x6beeb  ldloca.s 7
0x6beed  call     class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ExtractReportParameters(class [System]System.Collections.Specialized.NameValueCollection, bool[]&, class [System]System.Collections.Specialized.NameValueCollection&)
0x6bef2  stloc.s  9
0x6bef4  ldarg.0
0x6bef5  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x6befa  ldloc.1
0x6befb  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetPath(string)
0x6bf00  pop
0x6bf01  ldarg.0
0x6bf02  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6bf07  ldstr    aRsProgressives// "rs:ProgressiveSessionId"
0x6bf0c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6bf11  stloc.s  0xA
0x6bf13  ldarg.0
0x6bf14  callvirt instance class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x6bf19  callvirt instance string Microsoft.ReportingServices.Library.RSService::get_UserName()
0x6bf1e  ldloc.s  0xA
0x6bf20  newobj   instance void Microsoft.ReportingServices.Library.RenderEditRequest::.ctor(string userName, string sessionId)
0x6bf25  call     class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.IDbConnectionPool Microsoft.ReportingServices.Library.ProgressiveExecutionCacheManager::GetConnectionPool(class Microsoft.ReportingServices.Library.IRenderEditSession session)
0x6bf2a  stloc.s  0xB
0x6bf2c  ldarg.0
0x6bf2d  callvirt instance class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x6bf32  ldarg.0
0x6bf33  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x6bf38  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x6bf3d  ldloc.2
0x6bf3e  ldloc.s  9
0x6bf40  ldloc.s  5
0x6bf42  ldloc.s  0xB
0x6bf44  call     class Microsoft.ReportingServices.Library.RSStream Microsoft.ReportingServices.Library.ExecuteQueryCancelableStep::ExecuteQuery(class Microsoft.ReportingServices.Library.RSService rs, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath modelName, string query, class [System]System.Collections.Specialized.NameValueCollection parameters, int32 timeout, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.IDbConnectionPool connectionPool)
0x6bf49  stloc.s  4
0x6bf4b  br.s     loc_6BFB3
0x6bf4d  ldarg.0
0x6bf4e  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.StreamRequestHandler::get_RequestParameters()
0x6bf53  ldstr    aRsPerspectivei// "rs:PerspectiveID"
0x6bf58  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6bf5d  stloc.s  0xC
0x6bf5f  ldarg.0
0x6bf60  callvirt instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.StreamRequestHandler::get_Tracer()
0x6bf65  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x6bf6a  brfalse.s loc_6BF8C
0x6bf6c  ldarg.0
0x6bf6d  callvirt instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.StreamRequestHandler::get_Tracer()
0x6bf72  ldc.i4.3
0x6bf73  ldstr    aCallToGetuserm_1// "Call to GetUserModel. Model='{0}', Pers"...
0x6bf78  ldc.i4.2
0x6bf79  newarr   [mscorlib]System.Object
0x6bf7e  dup
0x6bf7f  ldc.i4.0
0x6bf80  ldloc.1
0x6bf81  stelem.ref
0x6bf82  dup
0x6bf83  ldc.i4.1
0x6bf84  ldloc.s  0xC
0x6bf86  stelem.ref
0x6bf87  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6bf8c  ldarg.0
0x6bf8d  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x6bf92  ldloc.1
0x6bf93  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetPath(string)
0x6bf98  pop
0x6bf99  ldarg.0
0x6bf9a  callvirt instance class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x6bf9f  ldarg.0
0x6bfa0  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x6bfa5  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x6bfaa  ldloc.s  0xC
0x6bfac  call     class Microsoft.ReportingServices.Library.RSStream Microsoft.ReportingServices.Library.GetUserModelCancelableStep::GetUserModel(class Microsoft.ReportingServices.Library.RSService rs, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath modelPath, string perspectiveID)
0x6bfb1  stloc.s  4
0x6bfb3  ldarg.0
0x6bfb4  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6bfb9  ldloc.s  4
0x6bfbb  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::WriteRSStream(class Microsoft.ReportingServices.Library.RSStream stream)
0x6bfc0  leave.s  loc_6BFCC
0x6bfc2  ldloc.0
0x6bfc3  brfalse.s loc_6BFCB
0x6bfc5  ldloc.0
0x6bfc6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6bfcb  endfinally
0x6bfcc  ret
```
