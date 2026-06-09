# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddSystemResourcePackageExceptionErrorDetails

- ea: `0x6bb0`
- end: `0x6d9b`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddSystemResourcePackageExceptionErrorDetails`
- size: `491`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1950`
- `0x6490`

## callees

- `0x6bb0`
- `0x6e60`

## pseudocode

```c

```

## disassembly

```asm
0x6bb0  ldarg.0
0x6bb1  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageMetadataInvalidException
0x6bb6  brfalse.s loc_6BEA
0x6bb8  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6bbd  dup
0x6bbe  ldc.i4   0xCA
0x6bc3  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6bc8  ldstr    aD// "D"
0x6bcd  call     instance string [mscorlib]System.Enum::ToString(string)
0x6bd2  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6bd7  dup
0x6bd8  ldarg.0
0x6bd9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6bde  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6be3  ldarg.1
0x6be4  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6be9  ret
0x6bea  ldarg.0
0x6beb  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageMetadataNotFoundException
0x6bf0  brfalse.s loc_6C24
0x6bf2  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6bf7  dup
0x6bf8  ldc.i4   0xC9
0x6bfd  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6c02  ldstr    aD// "D"
0x6c07  call     instance string [mscorlib]System.Enum::ToString(string)
0x6c0c  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6c11  dup
0x6c12  ldarg.0
0x6c13  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6c18  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6c1d  ldarg.1
0x6c1e  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6c23  ret
0x6c24  ldarg.0
0x6c25  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageReferencedItemMissingException
0x6c2a  brfalse.s loc_6C6F
0x6c2c  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6c31  dup
0x6c32  ldc.i4   0xCB
0x6c37  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6c3c  ldstr    aD// "D"
0x6c41  call     instance string [mscorlib]System.Enum::ToString(string)
0x6c46  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6c4b  dup
0x6c4c  ldarg.0
0x6c4d  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageReferencedItemMissingException
0x6c52  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_AdditionalTraceMessage()
0x6c57  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Target(string)
0x6c5c  dup
0x6c5d  ldarg.0
0x6c5e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6c63  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6c68  ldarg.1
0x6c69  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6c6e  ret
0x6c6f  ldarg.0
0x6c70  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageRequiredItemMissingException
0x6c75  brfalse.s loc_6CBA
0x6c77  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6c7c  dup
0x6c7d  ldc.i4   0xCC
0x6c82  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6c87  ldstr    aD// "D"
0x6c8c  call     instance string [mscorlib]System.Enum::ToString(string)
0x6c91  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6c96  dup
0x6c97  ldarg.0
0x6c98  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageRequiredItemMissingException
0x6c9d  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_AdditionalTraceMessage()
0x6ca2  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Target(string)
0x6ca7  dup
0x6ca8  ldarg.0
0x6ca9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6cae  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6cb3  ldarg.1
0x6cb4  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6cb9  ret
0x6cba  ldarg.0
0x6cbb  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageItemContentTypeMismatchException
0x6cc0  brfalse.s loc_6D05
0x6cc2  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6cc7  dup
0x6cc8  ldc.i4   0xCD
0x6ccd  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6cd2  ldstr    aD// "D"
0x6cd7  call     instance string [mscorlib]System.Enum::ToString(string)
0x6cdc  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6ce1  dup
0x6ce2  ldarg.0
0x6ce3  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageItemContentTypeMismatchException
0x6ce8  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_AdditionalTraceMessage()
0x6ced  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Target(string)
0x6cf2  dup
0x6cf3  ldarg.0
0x6cf4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6cf9  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6cfe  ldarg.1
0x6cff  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6d04  ret
0x6d05  ldarg.0
0x6d06  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageItemExtensionMismatchException
0x6d0b  brfalse.s loc_6D50
0x6d0d  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6d12  dup
0x6d13  ldc.i4   0xCE
0x6d18  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6d1d  ldstr    aD// "D"
0x6d22  call     instance string [mscorlib]System.Enum::ToString(string)
0x6d27  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6d2c  dup
0x6d2d  ldarg.0
0x6d2e  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageItemExtensionMismatchException
0x6d33  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_AdditionalTraceMessage()
0x6d38  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Target(string)
0x6d3d  dup
0x6d3e  ldarg.0
0x6d3f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6d44  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6d49  ldarg.1
0x6d4a  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6d4f  ret
0x6d50  ldarg.0
0x6d51  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageWrongTypeException
0x6d56  brfalse.s loc_6D9A
0x6d58  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::.ctor()
0x6d5d  dup
0x6d5e  ldc.i4   0xD0
0x6d63  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6d68  ldstr    aD// "D"
0x6d6d  call     instance string [mscorlib]System.Enum::ToString(string)
0x6d72  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_ErrorCode(string)
0x6d77  dup
0x6d78  ldarg.0
0x6d79  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageWrongTypeException
0x6d7e  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_AdditionalTraceMessage()
0x6d83  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Target(string)
0x6d88  dup
0x6d89  ldarg.0
0x6d8a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6d8f  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail::set_Message(string)
0x6d94  ldarg.1
0x6d95  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::AddODataErrorDetail(class [Microsoft.OData.Core]Microsoft.OData.ODataErrorDetail odataErrorDetail, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x6d9a  ret
```
