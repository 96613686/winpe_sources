# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddDataSetProcessingExceptionErrorDetails

- ea: `0x6da0`
- end: `0x6e52`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddDataSetProcessingExceptionErrorDetails`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1960`
- `0x6490`

## callees

- `0x6a0`
- `0x6c0`
- `0x6da0`
- `0x6e60`

## pseudocode

```c

```

## disassembly

```asm
0x6da0  ldarg.0
0x6da1  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSetParameterValueNotSetException
0x6da6  brfalse.s loc_6DFF
0x6da8  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6dad  dup
0x6dae  ldc.i4   0xDD
0x6db3  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6db8  ldstr    aD// "D"
0x6dbd  call     instance string [mscorlib]System.Enum::ToString(string)
0x6dc2  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6dc7  dup
0x6dc8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6dcd  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ParameterValueNotSupplied()
0x6dd2  ldarg.0
0x6dd3  castclass [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSetParameterValueNotSetException
0x6dd8  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_AdditionalTraceMessage()
0x6ddd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x6de2  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6de7  dup
0x6de8  ldarg.0
0x6de9  castclass [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSetParameterValueNotSetException
0x6dee  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_AdditionalTraceMessage()
0x6df3  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Target(string)
0x6df8  ldarg.1
0x6df9  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6dfe  ret
0x6dff  ldarg.0
0x6e00  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.DataSetRenderingSoapException
0x6e05  brfalse.s loc_6E51
0x6e07  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6e0c  dup
0x6e0d  ldc.i4   0xDE
0x6e12  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6e17  ldstr    aD// "D"
0x6e1c  call     instance string [mscorlib]System.Enum::ToString(string)
0x6e21  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6e26  dup
0x6e27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6e2c  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_DataSetProcessingSoapException()
0x6e31  ldarg.0
0x6e32  castclass [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.DataSetRenderingSoapException
0x6e37  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x6e3c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6e41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x6e46  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6e4b  ldarg.1
0x6e4c  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6e51  ret
```
