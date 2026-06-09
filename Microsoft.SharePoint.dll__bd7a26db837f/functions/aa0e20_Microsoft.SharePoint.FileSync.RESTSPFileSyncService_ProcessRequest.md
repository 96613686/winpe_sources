# Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequest

- ea: `0xaa0e20`
- end: `0xaa15ae`
- name: `Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequest`
- size: `1934`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a18c0`
- `0x45f170`
- `0x4cd8e0`
- `0x4cddc0`
- `0x93dae0`
- `0x957d90`
- `0xa99d90`
- `0xa9c460`
- `0xa9c590`
- `0xa9c830`
- `0xa9c970`
- `0xa9caa0`
- `0xa9cbd0`
- `0xa9d800`
- `0xa9e090`
- `0xa9e680`
- `0xa9f5e0`
- `0xaa00a0`
- `0xaa00b0`
- `0xaa0160`
- `0xaa0e20`
- `0xaa15b0`
- `0xaa15d0`
- `0xaa16c0`
- `0xaa16d0`
- `0xaa19c0`

## string_xrefs

- `0xaa0ed6`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa0f26`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa0f76`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa0fc6`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1016`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1066`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa10b6`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1106`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1156`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa11a6`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa11f6`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1246`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1296`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa12e6`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1336`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1386`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1414`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1464`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa14b4`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa1517`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`
- `0xaa155b`: `RESTSPFileSyncService.ProcessRequest: Exception happened {0}.`

## pseudocode

```c

```

## disassembly

```asm
0xaa0e20  newobj   instance void Microsoft.SharePoint.FileSync.SyncApiTelemetry::.ctor()
0xaa0e25  stloc.0
0xaa0e26  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xaa0e2b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xaa0e30  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0xaa0e35  call     class [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ThreadTracer Microsoft.SharePoint.PerformanceTracing::CreateThreadTracerFromRequestHeaders(class [System]System.Collections.Specialized.NameValueCollection headers)
0xaa0e3a  stloc.1
0xaa0e3b  ldc.i4   0x271A
0xaa0e40  ldstr    aProcessrequest// "ProcessRequest"
0xaa0e45  ldstr    aDDbsElZltDevSt_39// "d:\\dbs\\el\\zlt\\dev\\sts\\stsom\\SkyS"...
0xaa0e4a  ldc.i4.s 0x33
0xaa0e4c  call     class [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer::Create(valuetype [Microsoft.Cobalt.Base]Cobalt.ComponentId, string, string, int32)
0xaa0e51  stloc.s  0x1F
0xaa0e53  ldsfld   class Microsoft.SharePoint.FileSync.Killswitch Microsoft.SharePoint.FileSync.Killswitch::Global
0xaa0e58  callvirt instance void Microsoft.SharePoint.FileSync.Killswitch::Test()
0xaa0e5d  ldloca.s 2
0xaa0e5f  call     class Microsoft.SharePoint.FileSync.IEndpoint Microsoft.SharePoint.FileSync.Endpoint::GetEndpoint([out] class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.FileSync.UriParameterType, string>& uriParameters)
0xaa0e64  stloc.3
0xaa0e65  ldloc.2
0xaa0e66  ldarg.2
0xaa0e67  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0xaa0e6c  brtrue.s loc_AA0E71
0xaa0e6e  ldnull
0xaa0e6f  br.s     loc_AA0E7B
0xaa0e71  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0xaa0e76  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0xaa0e7b  ldloc.1
0xaa0e7c  newobj   instance void Microsoft.SharePoint.FileSync.SyncRequestContext::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.FileSync.UriParameterType, string> uriParameters, class [mscorlib]System.IO.Stream inputStream, class Microsoft.SharePoint.SPWeb web, [opt] class [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ThreadTracer threadTracer)
0xaa0e81  stloc.s  4
0xaa0e83  ldloc.s  4
0xaa0e85  ldloc.0
0xaa0e86  callvirt instance void Microsoft.SharePoint.FileSync.SyncRequestContext::set_ApiTelemetry(class Microsoft.SharePoint.FileSync.SyncApiTelemetry value)
0xaa0e8b  ldloc.s  4
0xaa0e8d  callvirt instance class Microsoft.SharePoint.FileSync.SyncApiTelemetry Microsoft.SharePoint.FileSync.SyncRequestContext::get_ApiTelemetry()
0xaa0e92  ldloc.3
0xaa0e93  callvirt instance valuetype Microsoft.SharePoint.FileSync.EndpointType Microsoft.SharePoint.FileSync.IEndpoint::get_EndpointType()
0xaa0e98  ldloc.s  4
0xaa0e9a  callvirt instance void Microsoft.SharePoint.FileSync.SyncApiTelemetry::AddRequestInfo(valuetype Microsoft.SharePoint.FileSync.EndpointType endpointType, class Microsoft.SharePoint.FileSync.SyncRequestContext syncRequestContext)
0xaa0e9f  ldloc.3
0xaa0ea0  ldloc.s  4
0xaa0ea2  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.IEndpoint::ProcessRequest(class Microsoft.SharePoint.FileSync.SyncRequestContext requestContext)
0xaa0ea7  stloc.s  5
0xaa0ea9  ldloc.s  5
0xaa0eab  stloc.s  0x1E
0xaa0ead  leave    loc_AA15AB
0xaa0eb2  ldloc.s  0x1F
0xaa0eb4  brfalse.s loc_AA0EBD
0xaa0eb6  ldloc.s  0x1F
0xaa0eb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaa0ebd  endfinally
0xaa0ebe  ldloc.1
0xaa0ebf  brfalse.s loc_AA0EC7
0xaa0ec1  ldloc.1
0xaa0ec2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaa0ec7  endfinally
0xaa0ec8  stloc.s  6
0xaa0eca  ldc.i4   0x3D839C
0xaa0ecf  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa0ed4  ldc.i4.s 0xF
0xaa0ed6  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa0edb  ldc.i4.1
0xaa0edc  newarr   [mscorlib]System.Object
0xaa0ee1  stloc.s  0x20
0xaa0ee3  ldloc.s  0x20
0xaa0ee5  ldc.i4.0
0xaa0ee6  ldloc.s  6
0xaa0ee8  stelem.ref
0xaa0ee9  ldloc.s  0x20
0xaa0eeb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa0ef0  ldloc.0
0xaa0ef1  ldc.i4   0x1F5
0xaa0ef6  ldloc.s  6
0xaa0ef8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa0efd  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa0f02  ldloc.s  6
0xaa0f04  ldloc.s  6
0xaa0f06  callvirt instance int32 Microsoft.SharePoint.FileSync.ClientSyncNotImplementedException::get_SyncError()
0xaa0f0b  ldnull
0xaa0f0c  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa0f11  stloc.s  0x1E
0xaa0f13  leave    loc_AA15AB
0xaa0f18  stloc.s  7
0xaa0f1a  ldc.i4   0x3D839D
0xaa0f1f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa0f24  ldc.i4.s 0xF
0xaa0f26  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa0f2b  ldc.i4.1
0xaa0f2c  newarr   [mscorlib]System.Object
0xaa0f31  stloc.s  0x21
0xaa0f33  ldloc.s  0x21
0xaa0f35  ldc.i4.0
0xaa0f36  ldloc.s  7
0xaa0f38  stelem.ref
0xaa0f39  ldloc.s  0x21
0xaa0f3b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa0f40  ldloc.0
0xaa0f41  ldc.i4   0x194
0xaa0f46  ldloc.s  7
0xaa0f48  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa0f4d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa0f52  ldloc.s  7
0xaa0f54  ldloc.s  7
0xaa0f56  callvirt instance int32 Microsoft.SharePoint.FileSync.ClientSyncResoureNotFoundException::get_SyncError()
0xaa0f5b  ldnull
0xaa0f5c  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa0f61  stloc.s  0x1E
0xaa0f63  leave    loc_AA15AB
0xaa0f68  stloc.s  8
0xaa0f6a  ldc.i4   0x4C1308
0xaa0f6f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa0f74  ldc.i4.s 0xF
0xaa0f76  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa0f7b  ldc.i4.1
0xaa0f7c  newarr   [mscorlib]System.Object
0xaa0f81  stloc.s  0x22
0xaa0f83  ldloc.s  0x22
0xaa0f85  ldc.i4.0
0xaa0f86  ldloc.s  8
0xaa0f88  stelem.ref
0xaa0f89  ldloc.s  0x22
0xaa0f8b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa0f90  ldloc.0
0xaa0f91  ldc.i4   0x195
0xaa0f96  ldloc.s  8
0xaa0f98  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa0f9d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa0fa2  ldloc.s  8
0xaa0fa4  ldloc.s  8
0xaa0fa6  callvirt instance int32 Microsoft.SharePoint.FileSync.ClientSyncMethodNotAllowedException::get_SyncError()
0xaa0fab  ldnull
0xaa0fac  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa0fb1  stloc.s  0x1E
0xaa0fb3  leave    loc_AA15AB
0xaa0fb8  stloc.s  9
0xaa0fba  ldc.i4   0x44718F
0xaa0fbf  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa0fc4  ldc.i4.s 0xF
0xaa0fc6  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa0fcb  ldc.i4.1
0xaa0fcc  newarr   [mscorlib]System.Object
0xaa0fd1  stloc.s  0x23
0xaa0fd3  ldloc.s  0x23
0xaa0fd5  ldc.i4.0
0xaa0fd6  ldloc.s  9
0xaa0fd8  stelem.ref
0xaa0fd9  ldloc.s  0x23
0xaa0fdb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa0fe0  ldloc.0
0xaa0fe1  ldc.i4   0x196
0xaa0fe6  ldloc.s  9
0xaa0fe8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa0fed  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa0ff2  ldloc.s  9
0xaa0ff4  ldloc.s  9
0xaa0ff6  callvirt instance int32 Microsoft.SharePoint.FileSync.ClientSyncNotAcceptableException::get_SyncError()
0xaa0ffb  ldnull
0xaa0ffc  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa1001  stloc.s  0x1E
0xaa1003  leave    loc_AA15AB
0xaa1008  stloc.s  0xA
0xaa100a  ldc.i4   0x41E1C0
0xaa100f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa1014  ldc.i4.s 0xF
0xaa1016  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa101b  ldc.i4.1
0xaa101c  newarr   [mscorlib]System.Object
0xaa1021  stloc.s  0x24
0xaa1023  ldloc.s  0x24
0xaa1025  ldc.i4.0
0xaa1026  ldloc.s  0xA
0xaa1028  stelem.ref
0xaa1029  ldloc.s  0x24
0xaa102b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa1030  ldloc.0
0xaa1031  ldc.i4   0x190
0xaa1036  ldloc.s  0xA
0xaa1038  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa103d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa1042  ldloc.s  0xA
0xaa1044  ldloc.s  0xA
0xaa1046  callvirt instance int32 Microsoft.SharePoint.FileSync.ClientSyncBadRequestException::get_SyncError()
0xaa104b  ldnull
0xaa104c  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa1051  stloc.s  0x1E
0xaa1053  leave    loc_AA15AB
0xaa1058  stloc.s  0xB
0xaa105a  ldc.i4   0x4C1309
0xaa105f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa1064  ldc.i4.s 0xF
0xaa1066  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa106b  ldc.i4.1
0xaa106c  newarr   [mscorlib]System.Object
0xaa1071  stloc.s  0x25
0xaa1073  ldloc.s  0x25
0xaa1075  ldc.i4.0
0xaa1076  ldloc.s  0xB
0xaa1078  stelem.ref
0xaa1079  ldloc.s  0x25
0xaa107b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa1080  ldloc.0
0xaa1081  ldc.i4   0x194
0xaa1086  ldloc.s  0xB
0xaa1088  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa108d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa1092  ldloc.s  0xB
0xaa1094  ldloc.s  0xB
0xaa1096  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncException::get_SyncError()
0xaa109b  ldnull
0xaa109c  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa10a1  stloc.s  0x1E
0xaa10a3  leave    loc_AA15AB
0xaa10a8  stloc.s  0xC
0xaa10aa  ldc.i4   0x4C130A
0xaa10af  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa10b4  ldc.i4.s 0xA
0xaa10b6  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa10bb  ldc.i4.1
0xaa10bc  newarr   [mscorlib]System.Object
0xaa10c1  stloc.s  0x26
0xaa10c3  ldloc.s  0x26
0xaa10c5  ldc.i4.0
0xaa10c6  ldloc.s  0xC
0xaa10c8  stelem.ref
0xaa10c9  ldloc.s  0x26
0xaa10cb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa10d0  ldloc.0
0xaa10d1  ldc.i4   0x190
0xaa10d6  ldloc.s  0xC
0xaa10d8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa10dd  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa10e2  ldloc.s  0xC
0xaa10e4  ldloc.s  0xC
0xaa10e6  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncException::get_SyncError()
0xaa10eb  ldnull
0xaa10ec  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa10f1  stloc.s  0x1E
0xaa10f3  leave    loc_AA15AB
0xaa10f8  stloc.s  0xD
0xaa10fa  ldc.i4   0x50671C
0xaa10ff  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa1104  ldc.i4.s 0xF
0xaa1106  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa110b  ldc.i4.1
0xaa110c  newarr   [mscorlib]System.Object
0xaa1111  stloc.s  0x27
0xaa1113  ldloc.s  0x27
0xaa1115  ldc.i4.0
0xaa1116  ldloc.s  0xD
0xaa1118  stelem.ref
0xaa1119  ldloc.s  0x27
0xaa111b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa1120  ldloc.0
0xaa1121  ldc.i4   0x1F5
0xaa1126  ldloc.s  0xD
0xaa1128  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa112d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa1132  ldloc.s  0xD
0xaa1134  ldloc.s  0xD
0xaa1136  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncException::get_SyncError()
0xaa113b  ldnull
0xaa113c  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa1141  stloc.s  0x1E
0xaa1143  leave    loc_AA15AB
0xaa1148  stloc.s  0xE
0xaa114a  ldc.i4   0x4C130C
0xaa114f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa1154  ldc.i4.s 0xF
0xaa1156  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa115b  ldc.i4.1
0xaa115c  newarr   [mscorlib]System.Object
0xaa1161  stloc.s  0x28
0xaa1163  ldloc.s  0x28
0xaa1165  ldc.i4.0
0xaa1166  ldloc.s  0xE
0xaa1168  stelem.ref
0xaa1169  ldloc.s  0x28
0xaa116b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaa1170  ldloc.0
0xaa1171  ldc.i4   0x190
0xaa1176  ldloc.s  0xE
0xaa1178  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaa117d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xaa1182  ldloc.s  0xE
0xaa1184  ldloc.s  0xE
0xaa1186  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncException::get_SyncError()
0xaa118b  ldnull
0xaa118c  call     class [mscorlib]System.IO.Stream Microsoft.SharePoint.FileSync.RESTSPFileSyncService::ProcessRequestException(class Microsoft.SharePoint.FileSync.SyncApiTelemetry ApiTelemetry, valuetype [System]System.Net.HttpStatusCode statusCode, [opt] string ExceptionName, [opt] class [mscorlib]System.Exception exception, [opt] int32 syncError, [opt] class [System]System.Collections.Specialized.NameValueCollection responseHeaders)
0xaa1191  stloc.s  0x1E
0xaa1193  leave    loc_AA15AB
0xaa1198  stloc.s  0xF
0xaa119a  ldc.i4   0x4C130D
0xaa119f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaa11a4  ldc.i4.s 0xF
0xaa11a6  ldstr    aRestspfilesync// "RESTSPFileSyncService.ProcessRequest: E"...
0xaa11ab  ldc.i4.1
0xaa11ac  newarr   [mscorlib]System.Object
0xaa11b1  stloc.s  0x29
0xaa11b3  ldloc.s  0x29
0xaa11b5  ldc.i4.0
0xaa11b6  ldloc.s  0xF
  ... truncated ...
```
