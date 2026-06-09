# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Filters.PortalExceptionFilter::OnException

- ea: `0x1810`
- end: `0x1908`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Filters.PortalExceptionFilter::OnException`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1810`
- `0x6470`
- `0x6490`
- `0x67a0`

## pseudocode

```c

```

## disassembly

```asm
0x1810  ldarg.1
0x1811  callvirt instance class [mscorlib]System.Exception [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::get_Exception()
0x1816  stloc.0
0x1817  ldloc.0
0x1818  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException
0x181d  brfalse.s loc_186A
0x181f  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x1824  dup
0x1825  ldloc.0
0x1826  castclass [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException
0x182b  ldfld    valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException::ErrorCode
0x1830  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x1835  ldstr    aD// "D"
0x183a  call     instance string [mscorlib]System.Enum::ToString(string)
0x183f  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x1844  dup
0x1845  ldloc.0
0x1846  callvirt instance string [mscorlib]System.Exception::get_Message()
0x184b  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x1850  stloc.1
0x1851  ldarg.1
0x1852  ldloc.1
0x1853  ldarg.1
0x1854  ldc.i4   0x1A6
0x1859  ldarg.0
0x185a  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::get_Logger()
0x185f  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::CreateErrorResponse(class [Microsoft.OData.Core]Microsoft.OData.ODataError odataError, class [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext context, valuetype [System]System.Net.HttpStatusCode httpStatusCode, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x1864  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::set_Response(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x1869  ret
0x186a  ldloc.0
0x186b  isinst   [mscorlib]System.Collections.Generic.KeyNotFoundException
0x1870  brfalse.s loc_18B3
0x1872  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x1877  dup
0x1878  ldc.i4.2
0x1879  box      [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Enums.ErrorCode
0x187e  ldstr    aD// "D"
0x1883  call     instance string [mscorlib]System.Enum::ToString(string)
0x1888  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x188d  dup
0x188e  ldloc.0
0x188f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1894  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x1899  stloc.2
0x189a  ldarg.1
0x189b  ldloc.2
0x189c  ldarg.1
0x189d  ldc.i4   0x194
0x18a2  ldarg.0
0x18a3  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::get_Logger()
0x18a8  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::CreateErrorResponse(class [Microsoft.OData.Core]Microsoft.OData.ODataError odataError, class [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext context, valuetype [System]System.Net.HttpStatusCode httpStatusCode, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x18ad  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::set_Response(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x18b2  ret
0x18b3  ldloc.0
0x18b4  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIMigrateInvalidUrlException
0x18b9  brfalse.s loc_1900
0x18bb  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x18c0  dup
0x18c1  ldc.i4   0x1FF
0x18c6  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x18cb  ldstr    aD// "D"
0x18d0  call     instance string [mscorlib]System.Enum::ToString(string)
0x18d5  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x18da  dup
0x18db  ldloc.0
0x18dc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x18e1  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x18e6  stloc.3
0x18e7  ldarg.1
0x18e8  ldloc.3
0x18e9  ldarg.1
0x18ea  ldc.i4   0x190
0x18ef  ldarg.0
0x18f0  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::get_Logger()
0x18f5  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::CreateErrorResponse(class [Microsoft.OData.Core]Microsoft.OData.ODataError odataError, class [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext context, valuetype [System]System.Net.HttpStatusCode httpStatusCode, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x18fa  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::set_Response(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x18ff  ret
0x1900  ldarg.0
0x1901  ldarg.1
0x1902  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::OnException(class [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext context)
0x1907  ret
```
