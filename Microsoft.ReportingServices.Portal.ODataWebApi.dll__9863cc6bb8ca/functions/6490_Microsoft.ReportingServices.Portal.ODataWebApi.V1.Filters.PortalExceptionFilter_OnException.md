# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::OnException

- ea: `0x6490`
- end: `0x679e`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::OnException`
- size: `782`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1810`

## callees

- `0x670`
- `0x6b0`
- `0x6d0`
- `0x6e0`
- `0x720`
- `0x6470`
- `0x6490`
- `0x67a0`
- `0x6850`
- `0x6bb0`
- `0x6da0`

## pseudocode

```c

```

## disassembly

```asm
0x6490  ldarg.1
0x6491  callvirt instance class [mscorlib]System.Exception [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::get_Exception()
0x6496  stloc.0
0x6497  ldc.i4   0x1F4
0x649c  stloc.1
0x649d  ldnull
0x649e  stloc.2
0x649f  ldloc.0
0x64a0  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.PortalException
0x64a5  brfalse.s loc_64E0
0x64a7  ldloc.0
0x64a8  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.PortalException
0x64ad  stloc.3
0x64ae  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x64b3  dup
0x64b4  ldloc.3
0x64b5  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.PortalException::get_ErrCode()
0x64ba  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x64bf  ldstr    aD// "D"
0x64c4  call     instance string [mscorlib]System.Enum::ToString(string)
0x64c9  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x64ce  dup
0x64cf  ldloc.3
0x64d0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x64d5  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x64da  stloc.2
0x64db  br       loc_6789
0x64e0  ldloc.0
0x64e1  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x64e6  brfalse.s loc_6530
0x64e8  ldloc.0
0x64e9  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x64ee  ldc.i4.0
0x64ef  stloc.s  4
0x64f1  ldsfld   string [mscorlib]System.String::Empty
0x64f6  stloc.s  5
0x64f8  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x64fd  dup
0x64fe  ldloc.s  4
0x6500  ldc.i4   0x3E8
0x6505  add
0x6506  box      [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode
0x650b  ldstr    aD// "D"
0x6510  call     instance string [mscorlib]System.Enum::ToString(string)
0x6515  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x651a  dup
0x651b  ldloc.s  5
0x651d  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x6522  stloc.2
0x6523  ldloc.2
0x6524  ldloca.s 1
0x6526  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::GetRsLibDetailsFromSoapException(class [System.Web.Services]System.Web.Services.Protocols.SoapException soapException, class [Microsoft.OData.Core]Microsoft.OData.ODataError error, valuetype [System]System.Net.HttpStatusCode& statusCode)
0x652b  br       loc_6789
0x6530  ldloc.0
0x6531  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.InvalidDataFormatException
0x6536  brfalse.s loc_656F
0x6538  ldloc.0
0x6539  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.InvalidDataFormatException
0x653e  stloc.s  6
0x6540  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x6545  dup
0x6546  ldc.i4.s 0x6A
0x6548  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x654d  ldstr    aD// "D"
0x6552  call     instance string [mscorlib]System.Enum::ToString(string)
0x6557  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x655c  dup
0x655d  ldloc.s  6
0x655f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6564  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x6569  stloc.2
0x656a  br       loc_6789
0x656f  ldloc.0
0x6570  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageException
0x6575  brfalse.s loc_65B4
0x6577  ldloc.0
0x6578  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageException
0x657d  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x6582  dup
0x6583  ldc.i4   0xC8
0x6588  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x658d  ldstr    aD// "D"
0x6592  call     instance string [mscorlib]System.Enum::ToString(string)
0x6597  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x659c  dup
0x659d  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_SystemResourcePackageException()
0x65a2  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x65a7  stloc.2
0x65a8  ldloca.s 2
0x65aa  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddSystemResourcePackageExceptionErrorDetails(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageException packageException, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x65af  br       loc_6789
0x65b4  ldloc.0
0x65b5  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.SystemResourcePackageException
0x65ba  brfalse.s loc_65EC
0x65bc  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x65c1  dup
0x65c2  ldc.i4   0xC8
0x65c7  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x65cc  ldstr    aD// "D"
0x65d1  call     instance string [mscorlib]System.Enum::ToString(string)
0x65d6  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x65db  dup
0x65dc  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_SystemResourcePackageException()
0x65e1  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x65e6  stloc.2
0x65e7  br       loc_6789
0x65ec  ldloc.0
0x65ed  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.SystemResourceProcessingException
0x65f2  brfalse.s loc_6624
0x65f4  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x65f9  dup
0x65fa  ldc.i4   0xD1
0x65ff  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6604  ldstr    aD// "D"
0x6609  call     instance string [mscorlib]System.Enum::ToString(string)
0x660e  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6613  dup
0x6614  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_SystemResourceProcessingException()
0x6619  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x661e  stloc.2
0x661f  br       loc_6789
0x6624  ldloc.0
0x6625  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSetParameterValueNotSetException
0x662a  brtrue.s loc_6634
0x662c  ldloc.0
0x662d  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.DataSetRenderingSoapException
0x6632  brfalse.s loc_6672
0x6634  ldc.i4   0x1A6
0x6639  stloc.1
0x663a  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x663f  dup
0x6640  ldc.i4   0xDC
0x6645  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x664a  ldstr    aD// "D"
0x664f  call     instance string [mscorlib]System.Enum::ToString(string)
0x6654  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6659  dup
0x665a  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_DataSetProcessingException()
0x665f  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x6664  stloc.2
0x6665  ldloc.0
0x6666  ldloca.s 2
0x6668  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddDataSetProcessingExceptionErrorDetails(class [mscorlib]System.Exception dataSetProcessingException, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x666d  br       loc_6789
0x6672  ldloc.0
0x6673  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x6678  brfalse.s loc_66BC
0x667a  ldloc.0
0x667b  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x6680  stloc.s  7
0x6682  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x6687  dup
0x6688  ldloc.s  7
0x668a  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x668f  ldc.i4   0x3E8
0x6694  add
0x6695  box      [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode
0x669a  ldstr    aD// "D"
0x669f  call     instance string [mscorlib]System.Enum::ToString(string)
0x66a4  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x66a9  dup
0x66aa  ldloc.s  7
0x66ac  callvirt instance string [mscorlib]System.Exception::get_Message()
0x66b1  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x66b6  stloc.2
0x66b7  br       loc_6789
0x66bc  ldloc.0
0x66bd  isinst   [mscorlib]System.NotSupportedException
0x66c2  brfalse.s loc_66F1
0x66c4  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x66c9  dup
0x66ca  ldc.i4.s 0x69
0x66cc  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x66d1  ldstr    aD// "D"
0x66d6  call     instance string [mscorlib]System.Enum::ToString(string)
0x66db  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x66e0  dup
0x66e1  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_NotSupportedException()
0x66e6  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x66eb  stloc.2
0x66ec  br       loc_6789
0x66f1  ldloc.0
0x66f2  isinst   [mscorlib]System.NotImplementedException
0x66f7  brfalse.s loc_6704
0x66f9  ldc.i4   0x195
0x66fe  stloc.1
0x66ff  br       loc_6789
0x6704  ldloc.0
0x6705  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.ExcelWorkbookWopiInvalidUrlException
0x670a  brfalse.s loc_6762
0x670c  ldloc.0
0x670d  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.ExcelWorkbookWopiInvalidUrlException
0x6712  stloc.s  8
0x6714  ldc.i4   0x190
0x6719  stloc.1
0x671a  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x671f  dup
0x6720  ldc.i4   0x1F5
0x6725  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x672a  ldstr    aD// "D"
0x672f  call     instance string [mscorlib]System.Enum::ToString(string)
0x6734  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6739  dup
0x673a  ldloc.s  8
0x673c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6741  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x6746  stloc.2
0x6747  ldloc.0
0x6748  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x674d  brfalse.s loc_6789
0x674f  ldloc.2
0x6750  ldloc.0
0x6751  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x6756  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataInnerError::.ctor(class [mscorlib]System.Exception)
0x675b  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_InnerError(class [Microsoft.OData.Core]Microsoft.OData.ODataInnerError)
0x6760  br.s     loc_6789
0x6762  ldloc.0
0x6763  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.UploadFileCanceledException
0x6768  brfalse.s loc_6789
0x676a  ldc.i4   0x19A
0x676f  stloc.1
0x6770  ldarg.0
0x6771  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::get_Logger()
0x6776  brfalse.s loc_6789
0x6778  ldarg.0
0x6779  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::get_Logger()
0x677e  ldc.i4.4
0x677f  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_UploadFileCanceled()
0x6784  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6789  ldarg.1
0x678a  ldloc.2
0x678b  ldarg.1
0x678c  ldloc.1
0x678d  ldarg.0
0x678e  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::get_Logger()
0x6793  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::CreateErrorResponse(class [Microsoft.OData.Core]Microsoft.OData.ODataError odataError, class [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext context, valuetype [System]System.Net.HttpStatusCode httpStatusCode, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x6798  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::set_Response(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x679d  ret
```
