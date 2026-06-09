# Microsoft.ReportingServices.WmiProvider.WMIProviderException::ErrorCodeToMessage

- ea: `0x86b0`
- end: `0x8969`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderException::ErrorCodeToMessage`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `66`
- tags: `service_task, broker_com_uri`

## callers

- `0x85f0`
- `0x8610`

## callees

- `0x86b0`
- `0x8a20`
- `0x8a30`
- `0x8a40`
- `0x8a50`
- `0x8a60`
- `0x8a70`
- `0x8a80`
- `0x8a90`
- `0x8aa0`
- `0x8ab0`
- `0x8ac0`
- `0x8ad0`
- `0x8ae0`
- `0x8af0`
- `0x8b00`
- `0x8b10`
- `0x8b20`
- `0x8b30`
- `0x8b40`
- `0x8b50`
- `0x8b60`
- `0x8b70`
- `0x8b80`
- `0x8b90`
- `0x8ba0`
- `0x8bb0`
- `0x8bc0`
- `0x8bd0`
- `0x8be0`
- `0x8bf0`
- `0x8c00`
- `0x8c10`
- `0x8c20`
- `0x8c30`
- `0x8c40`
- `0x8c50`
- `0x8c60`
- `0x8c70`
- `0x8c80`
- `0x8c90`
- `0x8ca0`
- `0x8cb0`
- `0x8cc0`
- `0x8cd0`
- `0x8ce0`
- `0x8cf0`
- `0x8d00`
- `0x8d10`
- `0x8d20`

## pseudocode

```c

```

## disassembly

```asm
0x86b0  ldarg.0
0x86b1  brfalse  loc_87E2
0x86b6  ldarg.0
0x86b7  ldc.i4   0x80040201
0x86bc  sub
0x86bd  switch   loc_87E8, loc_87EE, loc_87F4, loc_87FA, loc_8800, loc_8806, loc_880C, loc_8812, loc_8962, loc_8962, loc_8962, loc_8818, loc_881E, loc_8824, loc_882A, loc_8830, loc_8836, loc_883C, loc_8842, loc_8848, loc_884E, loc_8854, loc_885A, loc_8860, loc_8866, loc_886C, loc_8872, loc_8878, loc_887E, loc_8884, loc_888A, loc_8890, loc_8896, loc_889C, loc_88A2, loc_88A8, loc_88AE, loc_88B4, loc_88BA, loc_88C0, loc_88C6, loc_88DE, loc_88D2, loc_88E4, loc_88D8, loc_8962, loc_8962, loc_88EA, loc_88F0, loc_88F6, loc_88FC, loc_8902, loc_8908, loc_890E, loc_8914, loc_891A \
0x87d2  ldarg.0
0x87d3  ldc.i4   0x800706B3
0x87d8  beq      loc_88CC
0x87dd  br       loc_8962
0x87e2  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_Success()
0x87e7  ret
0x87e8  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_CantConnectCatalog()
0x87ed  ret
0x87ee  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ServiceNotActivated()
0x87f3  ret
0x87f4  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ServiceDisabled()
0x87f9  ret
0x87fa  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_UnexpectedDatabaseError()
0x87ff  ret
0x8800  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_UnexpectedDatabaseResult()
0x8805  ret
0x8806  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_AlreadyActivated()
0x880b  ret
0x880c  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_NotAnnounced()
0x8811  ret
0x8812  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_NotAdmin()
0x8817  ret
0x8818  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_VirtualDirectoryAlreadyExists()
0x881d  ret
0x881e  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_VirtualDirectoryInvalid()
0x8823  ret
0x8824  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidIISPath()
0x8829  ret
0x882a  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_IISNotInstalled()
0x882f  ret
0x8830  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ASPNetNotRegistered()
0x8835  ret
0x8836  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidUser()
0x883b  ret
0x883c  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InsufficientPrivilege()
0x8841  ret
0x8842  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_SqlAdminUserInsufficientPrivilege()
0x8847  ret
0x8848  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_GrantLoginToPasswordRequired()
0x884d  ret
0x884e  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsexecRoleDoesNotExist()
0x8853  ret
0x8854  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_WindowsServiceAccountNotSet()
0x8859  ret
0x885a  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_WebServiceAccountNotSet()
0x885f  ret
0x8860  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_SslCertificateNotFound()
0x8865  ret
0x8866  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ConfigurationFileNotFound()
0x886b  ret
0x886c  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidPortNumber()
0x8871  ret
0x8872  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidUrlParameterSet()
0x8877  ret
0x8878  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidSecureConnectionLevel()
0x887d  ret
0x887e  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_IllformedAccountString()
0x8883  ret
0x8884  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadCredentialsType()
0x8889  ret
0x888a  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadApplicationPool()
0x888f  ret
0x8890  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadVerson()
0x8895  ret
0x8896  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidVersionString()
0x889b  ret
0x889c  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadLcid()
0x88a1  ret
0x88a2  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ApplicationPoolAlreadyExists()
0x88a7  ret
0x88a8  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_OperatingSystemNotSupported()
0x88ad  ret
0x88ae  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadWebsiteConfiguration()
0x88b3  ret
0x88b4  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadConfigurationFile()
0x88b9  ret
0x88ba  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_SharePointNotInstalled()
0x88bf  ret
0x88c0  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_MustCreateVirtualDirectory()
0x88c5  ret
0x88c6  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_FailedToLoadResources()
0x88cb  ret
0x88cc  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RPCServerNotListening()
0x88d1  ret
0x88d2  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_FailedToEnumerateInstances()
0x88d7  ret
0x88d8  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadApplicationPoolName()
0x88dd  ret
0x88de  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_LocalServiceIsLocalOnly()
0x88e3  ret
0x88e4  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidParameter()
0x88e9  ret
0x88ea  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_NotSupportedInSharePointMode()
0x88ef  ret
0x88f0  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_NotSupportedInNativeMode()
0x88f5  ret
0x88f6  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsSharePointObjectModelNotInstalled()
0x88fb  ret
0x88fc  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsSharePointError()
0x8901  ret
0x8902  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsServerConfigurationError()
0x8907  ret
0x8908  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsUrlAlreadyReservedDifferentName()
0x890d  ret
0x890e  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsMustDefineApplicationFirst()
0x8913  ret
0x8914  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsIpAddressNotFound()
0x8919  ret
0x891a  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsSSLBindingConflict()
0x891f  ret
0x8920  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsSSLCertificateNotRegistered()
0x8925  ret
0x8926  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsInvalidApplication()
0x892b  ret
0x892c  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsURLAlreadyReserved()
0x8931  ret
0x8932  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsURLNotReserved()
0x8937  ret
0x8938  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsURLMustNotExist()
0x893d  ret
0x893e  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsDeliveryExtensionNotFound()
0x8943  ret
0x8944  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsLocalServiceNotAllowedXP()
0x8949  ret
0x894a  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsInvalidSSLCertificate()
0x894f  ret
0x8950  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsBadExtendedProtectionLevelType()
0x8955  ret
0x8956  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsBadExtendedProtectionScenarioType()
0x895b  ret
0x895c  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsMustDefineAuthenticationFirst()
0x8961  ret
0x8962  ldarg.0
0x8963  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::ErrorCodes_UnknownOrUnmappedException(int32 errorCode)
0x8968  ret
```
