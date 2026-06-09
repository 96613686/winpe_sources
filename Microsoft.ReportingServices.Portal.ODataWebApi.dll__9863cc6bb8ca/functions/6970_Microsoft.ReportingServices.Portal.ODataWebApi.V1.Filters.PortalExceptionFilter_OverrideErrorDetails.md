# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::OverrideErrorDetails

- ea: `0x6970`
- end: `0x6ba1`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::OverrideErrorDetails`
- size: `561`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1940`
- `0x67a0`

## callees

- `0x6970`

## pseudocode

```c

```

## disassembly

```asm
0x6970  ldarg.0
0x6971  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.AccessDeniedException
0x6976  brfalse.s loc_6997
0x6978  ldarg.1
0x6979  ldc.i4   0x193
0x697e  stind.i4
0x697f  ldarg.2
0x6980  ldind.ref
0x6981  ldc.i4.1
0x6982  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6987  ldstr    aD// "D"
0x698c  call     instance string [mscorlib]System.Enum::ToString(string)
0x6991  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6996  ret
0x6997  ldarg.0
0x6998  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException
0x699d  brtrue.s loc_69C7
0x699f  ldarg.0
0x69a0  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSetNotFoundException
0x69a5  brtrue.s loc_69C7
0x69a7  ldarg.0
0x69a8  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException
0x69ad  brtrue.s loc_69C7
0x69af  ldarg.0
0x69b0  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ScheduleNotFoundException
0x69b5  brtrue.s loc_69C7
0x69b7  ldarg.0
0x69b8  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.SubscriptionNotFoundException
0x69bd  brtrue.s loc_69C7
0x69bf  ldarg.0
0x69c0  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownUserNameException
0x69c5  brfalse.s loc_69E6
0x69c7  ldarg.1
0x69c8  ldc.i4   0x194
0x69cd  stind.i4
0x69ce  ldarg.2
0x69cf  ldind.ref
0x69d0  ldc.i4.2
0x69d1  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x69d6  ldstr    aD// "D"
0x69db  call     instance string [mscorlib]System.Enum::ToString(string)
0x69e0  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x69e5  ret
0x69e6  ldarg.0
0x69e7  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemAlreadyExistsException
0x69ec  brtrue.s loc_69F6
0x69ee  ldarg.0
0x69ef  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidPolicyDefinitionException
0x69f4  brfalse.s loc_6A16
0x69f6  ldarg.1
0x69f7  ldc.i4   0x199
0x69fc  stind.i4
0x69fd  ldarg.2
0x69fe  ldind.ref
0x69ff  ldc.i4.s 0x65
0x6a01  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6a06  ldstr    aD// "D"
0x6a0b  call     instance string [mscorlib]System.Enum::ToString(string)
0x6a10  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6a15  ret
0x6a16  ldarg.0
0x6a17  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.WrongItemTypeException
0x6a1c  brfalse.s loc_6A3E
0x6a1e  ldarg.1
0x6a1f  ldc.i4   0x199
0x6a24  stind.i4
0x6a25  ldarg.2
0x6a26  ldind.ref
0x6a27  ldc.i4.s 0x6B
0x6a29  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6a2e  ldstr    aD// "D"
0x6a33  call     instance string [mscorlib]System.Enum::ToString(string)
0x6a38  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6a3d  ret
0x6a3e  ldarg.0
0x6a3f  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CatalogItemContentInvalidException
0x6a44  brtrue.s loc_6A4E
0x6a46  ldarg.0
0x6a47  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ParameterTypeMismatchException
0x6a4c  brfalse.s loc_6A6E
0x6a4e  ldarg.1
0x6a4f  ldc.i4   0x190
0x6a54  stind.i4
0x6a55  ldarg.2
0x6a56  ldind.ref
0x6a57  ldc.i4.s 0x66
0x6a59  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6a5e  ldstr    aD// "D"
0x6a63  call     instance string [mscorlib]System.Enum::ToString(string)
0x6a68  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6a6d  ret
0x6a6e  ldarg.0
0x6a6f  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemNameException
0x6a74  brtrue.s loc_6A7E
0x6a76  ldarg.0
0x6a77  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemPathException
0x6a7c  brfalse.s loc_6A9E
0x6a7e  ldarg.1
0x6a7f  ldc.i4   0x1A6
0x6a84  stind.i4
0x6a85  ldarg.2
0x6a86  ldind.ref
0x6a87  ldc.i4.s 0x67
0x6a89  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6a8e  ldstr    aD// "D"
0x6a93  call     instance string [mscorlib]System.Enum::ToString(string)
0x6a98  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6a9d  ret
0x6a9e  ldarg.0
0x6a9f  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemPathLengthExceededException
0x6aa4  brfalse.s loc_6AC6
0x6aa6  ldarg.1
0x6aa7  ldc.i4   0x1A6
0x6aac  stind.i4
0x6aad  ldarg.2
0x6aae  ldind.ref
0x6aaf  ldc.i4.s 0x68
0x6ab1  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6ab6  ldstr    aD// "D"
0x6abb  call     instance string [mscorlib]System.Enum::ToString(string)
0x6ac0  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6ac5  ret
0x6ac6  ldarg.0
0x6ac7  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerDatabaseLogonFailedException
0x6acc  brtrue.s loc_6ADE
0x6ace  ldarg.0
0x6acf  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.DatabaseUnavailableException
0x6ad4  brtrue.s loc_6ADE
0x6ad6  ldarg.0
0x6ad7  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException
0x6adc  brfalse.s loc_6AE6
0x6ade  ldarg.1
0x6adf  ldc.i4   0x1F7
0x6ae4  stind.i4
0x6ae5  ret
0x6ae6  ldarg.0
0x6ae7  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.FileSizeException
0x6aec  brtrue.s loc_6AF6
0x6aee  ldarg.0
0x6aef  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.FileSizeNotSupportedException
0x6af4  brfalse.s loc_6B16
0x6af6  ldarg.1
0x6af7  ldc.i4   0x1A6
0x6afc  stind.i4
0x6afd  ldarg.2
0x6afe  ldind.ref
0x6aff  ldc.i4.s 0x69
0x6b01  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6b06  ldstr    aD// "D"
0x6b0b  call     instance string [mscorlib]System.Enum::ToString(string)
0x6b10  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6b15  ret
0x6b16  ldarg.0
0x6b17  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ResourceFileFormatNotAllowedException
0x6b1c  brfalse.s loc_6B3E
0x6b1e  ldarg.1
0x6b1f  ldc.i4   0x190
0x6b24  stind.i4
0x6b25  ldarg.2
0x6b26  ldind.ref
0x6b27  ldc.i4.s 0x6C
0x6b29  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6b2e  ldstr    aD// "D"
0x6b33  call     instance string [mscorlib]System.Enum::ToString(string)
0x6b38  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6b3d  ret
0x6b3e  ldarg.0
0x6b3f  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ResourceMimeTypeNotAllowedException
0x6b44  brfalse.s loc_6B66
0x6b46  ldarg.1
0x6b47  ldc.i4   0x190
0x6b4c  stind.i4
0x6b4d  ldarg.2
0x6b4e  ldind.ref
0x6b4f  ldc.i4.s 0x6D
0x6b51  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6b56  ldstr    aD// "D"
0x6b5b  call     instance string [mscorlib]System.Enum::ToString(string)
0x6b60  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6b65  ret
0x6b66  ldarg.0
0x6b67  isinst   [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ExcelFileExtensionChangeNotAllowedException
0x6b6c  brfalse.s loc_6B91
0x6b6e  ldarg.1
0x6b6f  ldc.i4   0x190
0x6b74  stind.i4
0x6b75  ldarg.2
0x6b76  ldind.ref
0x6b77  ldc.i4   0x1F6
0x6b7c  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x6b81  ldstr    aD// "D"
0x6b86  call     instance string [mscorlib]System.Enum::ToString(string)
0x6b8b  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x6b90  ret
0x6b91  ldarg.0
0x6b92  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportCatalogException
0x6b97  brfalse.s loc_6BA0
0x6b99  ldarg.1
0x6b9a  ldc.i4   0x1F4
0x6b9f  stind.i4
0x6ba0  ret
```
