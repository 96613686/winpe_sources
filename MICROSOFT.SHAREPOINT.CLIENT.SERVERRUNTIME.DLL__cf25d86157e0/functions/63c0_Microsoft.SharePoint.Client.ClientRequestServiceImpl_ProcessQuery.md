# Microsoft.SharePoint.Client.ClientRequestServiceImpl::ProcessQuery

- ea: `0x63c0`
- end: `0x66a4`
- name: `Microsoft.SharePoint.Client.ClientRequestServiceImpl::ProcessQuery`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x69c0`

## callees

- `0x63c0`
- `0x66b0`
- `0x9880`
- `0x9890`
- `0x9f90`
- `0xa7b0`
- `0xaab0`
- `0xdef0`
- `0xe000`
- `0xe010`
- `0xe0f0`
- `0xe230`
- `0xe310`
- `0xe320`
- `0xe590`
- `0xe620`
- `0xebb0`
- `0xecc0`
- `0x12e20`
- `0x13000`
- `0x13030`
- `0x13210`
- `0x13880`
- `0x16f10`
- `0x17f20`
- `0x18010`
- `0x188b0`
- `0x18af0`
- `0x2c2a0`

## string_xrefs

- `0x63c7`: `ClientRequestServiceImpl.ProcessQuery`
- `0x63fb`: `The user is not authenticated, send access denied. NullUser={0}, NullIdentity={1}, IsAuthenticated={2}`
- `0x64bf`: `application/json; charset=utf-8`

## pseudocode

```c

```

## disassembly

```asm
0x63c0  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x63c5  stloc.0
0x63c6  ldloc.0
0x63c7  ldstr    aClientrequests// "ClientRequestServiceImpl.ProcessQuery"
0x63cc  ldc.i4.2
0x63cd  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(string name, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x63d2  stloc.s  0xC
0x63d4  ldloc.0
0x63d5  ldc.i4   0x215784
0x63da  ldc.i4.4
0x63db  ldstr    aProcessingCsom// "Processing CSOM queries"
0x63e0  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x63e5  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x63ea  call     bool Microsoft.SharePoint.Client.Utility::ShouldForceAuthentication(class [System.Web]System.Web.HttpContext httpContext)
0x63ef  brfalse  loc_649E
0x63f4  ldloc.0
0x63f5  ldc.i4   0x215785
0x63fa  ldc.i4.2
0x63fb  ldstr    aTheUserIsNotAu// "The user is not authenticated, send acc"...
0x6400  ldc.i4.3
0x6401  newarr   [mscorlib]System.Object
0x6406  stloc.s  0xD
0x6408  ldloc.s  0xD
0x640a  ldc.i4.0
0x640b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6410  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x6415  ldnull
0x6416  ceq
0x6418  box      [mscorlib]System.Boolean
0x641d  stelem.ref
0x641e  ldloc.s  0xD
0x6420  ldc.i4.1
0x6421  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6426  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x642b  brfalse.s loc_6441
0x642d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6432  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x6437  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x643c  ldnull
0x643d  ceq
0x643f  br.s     loc_6442
0x6441  ldc.i4.0
0x6442  box      [mscorlib]System.Boolean
0x6447  stelem.ref
0x6448  ldloc.s  0xD
0x644a  ldc.i4.2
0x644b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6450  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x6455  brfalse.s loc_647E
0x6457  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x645c  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x6461  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x6466  brfalse.s loc_647E
0x6468  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x646d  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x6472  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x6477  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x647c  br.s     loc_647F
0x647e  ldc.i4.0
0x647f  box      [mscorlib]System.Boolean
0x6484  stelem.ref
0x6485  ldloc.s  0xD
0x6487  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x648c  ldloc.0
0x648d  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendAccessDeniedHeader()
0x6492  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x6497  stloc.s  0xB
0x6499  leave    loc_66A1
0x649e  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x64a3  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.IncomingWebRequestContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_IncomingRequest()
0x64a8  callvirt instance string [System.ServiceModel.Web]System.ServiceModel.Web.IncomingWebRequestContext::get_ContentType()
0x64ad  stloc.1
0x64ae  ldloc.1
0x64af  call     string Microsoft.SharePoint.Utilities.Mime.MimeUtility::GetBoundary(string contentType)
0x64b4  stloc.2
0x64b5  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x64ba  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x64bf  ldstr    aApplicationJso// "application/json; charset=utf-8"
0x64c4  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_ContentType(string)
0x64c9  ldarg.1
0x64ca  brtrue.s loc_64D8
0x64cc  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x64d1  stloc.s  0xB
0x64d3  leave    loc_66A1
0x64d8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x64dd  call     void Microsoft.SharePoint.Client.Utility::SetIsClientQuery(class [System.Web]System.Web.HttpContext context)
0x64e2  ldnull
0x64e3  stloc.3
0x64e4  ldloc.0
0x64e5  callvirt instance bool Microsoft.SharePoint.Client.ClientServiceHost::OnBeginRequest()
0x64ea  brtrue.s loc_6509
0x64ec  ldloc.0
0x64ed  ldc.i4   0x215786
0x64f2  ldc.i4.2
0x64f3  ldstr    aOnbeginrequest// "OnBeginRequest returns false, do not ne"...
0x64f8  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x64fd  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x6502  stloc.s  0xB
0x6504  leave    loc_66A1
0x6509  ldloc.0
0x650a  call     valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Client.Utility::GetWebOperationContextIncomingRequestContentLength(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x650f  stloc.s  4
0x6511  ldloca.s 4
0x6513  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x6518  brfalse  loc_659F
0x651d  ldloca.s 4
0x651f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x6524  ldloc.0
0x6525  callvirt instance class Microsoft.SharePoint.Client.ClientRequestServiceSettings Microsoft.SharePoint.Client.ClientServiceHost::get_ClientRequestServiceSettings()
0x652a  callvirt instance int32 Microsoft.SharePoint.Client.ClientRequestServiceSettings::get_MaxReceivedMessageSizeOrDefault()
0x652f  conv.i8
0x6530  ble.s    loc_659F
0x6532  ldloc.0
0x6533  ldc.i4   0x215787
0x6538  ldc.i4.1
0x6539  ldstr    aTheContentLeng// "The content length {0} is large than ma"...
0x653e  ldc.i4.2
0x653f  newarr   [mscorlib]System.Object
0x6544  stloc.s  0xE
0x6546  ldloc.s  0xE
0x6548  ldc.i4.0
0x6549  ldloca.s 4
0x654b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x6550  box      [mscorlib]System.Int64
0x6555  stelem.ref
0x6556  ldloc.s  0xE
0x6558  ldc.i4.1
0x6559  ldloc.0
0x655a  callvirt instance class Microsoft.SharePoint.Client.ClientRequestServiceSettings Microsoft.SharePoint.Client.ClientServiceHost::get_ClientRequestServiceSettings()
0x655f  callvirt instance int32 Microsoft.SharePoint.Client.ClientRequestServiceSettings::get_MaxReceivedMessageSizeOrDefault()
0x6564  box      [mscorlib]System.Int32
0x6569  stelem.ref
0x656a  ldloc.s  0xE
0x656c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6571  ldstr    aRequestmessage// "RequestMessageSizeTooBig"
0x6576  ldc.i4.1
0x6577  newarr   [mscorlib]System.Object
0x657c  stloc.s  0xF
0x657e  ldloc.s  0xF
0x6580  ldc.i4.0
0x6581  ldloc.0
0x6582  callvirt instance class Microsoft.SharePoint.Client.ClientRequestServiceSettings Microsoft.SharePoint.Client.ClientServiceHost::get_ClientRequestServiceSettings()
0x6587  callvirt instance int32 Microsoft.SharePoint.Client.ClientRequestServiceSettings::get_MaxReceivedMessageSizeOrDefault()
0x658c  box      [mscorlib]System.Int32
0x6591  stelem.ref
0x6592  ldloc.s  0xF
0x6594  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x6599  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x659e  throw
0x659f  ldarg.1
0x65a0  ldloc.0
0x65a1  ldloc.2
0x65a2  ldarg.2
0x65a3  newobj   instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::.ctor(class [mscorlib]System.IO.Stream batchRequest, class Microsoft.SharePoint.Client.ClientServiceHost host, string boundary, class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.IDisposable> pendingDisposableQueue)
0x65a8  stloc.s  5
0x65aa  call     class Microsoft.SharePoint.Client.ClientServiceOperationContext Microsoft.SharePoint.Client.ClientServiceOperationContext::get_Current()
0x65af  ldloc.s  5
0x65b1  callvirt instance void Microsoft.SharePoint.Client.ClientServiceOperationContext::set_ClientMethodsProcessor(class Microsoft.SharePoint.Client.ClientMethodsProcessor value)
0x65b6  ldloc.s  5
0x65b8  callvirt instance class Microsoft.SharePoint.Client.ClientMethodsProcessorResult Microsoft.SharePoint.Client.ClientMethodsProcessor::Process()
0x65bd  stloc.s  6
0x65bf  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x65c4  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x65c9  ldloc.s  6
0x65cb  callvirt instance string Microsoft.SharePoint.Client.ClientMethodsProcessorResult::get_ContentType()
0x65d0  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_ContentType(string)
0x65d5  ldloc.s  6
0x65d7  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.ClientMethodsProcessorResult::get_OutputStream()
0x65dc  stloc.3
0x65dd  leave.s  loc_65EB
0x65df  ldloc.s  5
0x65e1  brfalse.s loc_65EA
0x65e3  ldloc.s  5
0x65e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65ea  endfinally
0x65eb  leave.s  loc_65F4
0x65ed  ldloc.0
0x65ee  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::OnEndRequest()
0x65f3  endfinally
0x65f4  leave.s  loc_6662
0x65f6  stloc.s  7
0x65f8  ldloc.0
0x65f9  brfalse.s loc_660E
0x65fb  ldloc.0
0x65fc  ldc.i4   0x15755B
0x6601  ldc.i4.1
0x6602  ldloc.s  7
0x6604  callvirt instance string [mscorlib]System.Object::ToString()
0x6609  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x660e  ldloc.s  7
0x6610  call     bool Microsoft.SharePoint.Client.Utility::FIsFatalException(class [mscorlib]System.Exception e)
0x6615  brfalse.s loc_6619
0x6617  rethrow
0x6619  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x661e  stloc.s  8
0x6620  ldloc.s  8
0x6622  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6627  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x662c  newobj   instance void Microsoft.SharePoint.Client.JsonWriter::.ctor(class [mscorlib]System.IO.TextWriter writer)
0x6631  stloc.s  9
0x6633  ldloc.s  9
0x6635  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x663a  ldloc.s  9
0x663c  ldloc.s  7
0x663e  ldloc.0
0x663f  call     void Microsoft.SharePoint.Client.ClientMethodsProcessor::WriteResponseHeader(class Microsoft.SharePoint.Client.JsonWriter writer, class [mscorlib]System.Exception ex, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x6644  ldloc.s  9
0x6646  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x664b  ldloc.s  9
0x664d  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::Flush()
0x6652  ldarg.0
0x6653  ldloc.s  8
0x6655  callvirt instance string [mscorlib]System.Object::ToString()
0x665a  call     instance class [mscorlib]System.IO.MemoryStream Microsoft.SharePoint.Client.ClientRequestServiceImpl::CreateUTF8Stream(string str)
0x665f  stloc.3
0x6660  leave.s  loc_6662
0x6662  leave.s  loc_6687
0x6664  ldarg.1
0x6665  brfalse.s loc_6686
0x6667  ldarg.1
0x6668  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x666d  leave.s  loc_6686
0x666f  stloc.s  0xA
0x6671  ldloc.0
0x6672  ldc.i4   0x15755C
0x6677  ldc.i4.1
0x6678  ldloc.s  0xA
0x667a  callvirt instance string [mscorlib]System.Object::ToString()
0x667f  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x6684  leave.s  loc_6686
0x6686  endfinally
0x6687  ldloc.3
0x6688  brtrue.s loc_6690
0x668a  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x668f  stloc.3
0x6690  ldloc.3
0x6691  stloc.s  0xB
0x6693  leave.s  loc_66A1
0x6695  ldloc.s  0xC
0x6697  brfalse.s loc_66A0
0x6699  ldloc.s  0xC
0x669b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66a0  endfinally
0x66a1  ldloc.s  0xB
0x66a3  ret
```
