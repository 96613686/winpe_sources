# Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ValidateDefinition

- ea: `0x16f8f0`
- end: `0x16fa32`
- name: `Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ValidateDefinition`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1707d0`

## callees

- `0x16f8f0`
- `0x16fcc0`
- `0x16fce0`
- `0x16fec0`
- `0x16fee0`
- `0x16ff50`
- `0x170130`
- `0x170fc0`

## string_xrefs

- `0x16f8f8`: `Extension`
- `0x16f982`: `ImpersonateUser`
- `0x16f9d1`: `ImpersonateUser`

## pseudocode

```c

```

## disassembly

```asm
0x16f8f0  ldarg.0
0x16f8f1  call     instance string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Extension()
0x16f8f6  brtrue.s loc_16F903
0x16f8f8  ldstr    aExtension_0// "Extension"
0x16f8fd  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x16f902  throw
0x16f903  ldarg.0
0x16f904  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16f909  ldc.i4.2
0x16f90a  beq.s    loc_16F91C
0x16f90c  ldarg.0
0x16f90d  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16f912  ldc.i4.1
0x16f913  beq.s    loc_16F91C
0x16f915  ldarg.0
0x16f916  ldc.i4.0
0x16f917  call     instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_WindowsCredentials(bool value)
0x16f91c  ldarg.0
0x16f91d  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16f922  ldc.i4.2
0x16f923  beq.s    loc_16F955
0x16f925  ldarg.0
0x16f926  ldfld    unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_userNameEncrypted
0x16f92b  brfalse.s loc_16F93D
0x16f92d  ldstr    aUsername// "UserName"
0x16f932  ldstr    aCredentialretr// "CredentialRetrieval"
0x16f937  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x16f93c  throw
0x16f93d  ldarg.0
0x16f93e  ldfld    unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_passwordEncrypted
0x16f943  brfalse.s loc_16F968
0x16f945  ldstr    aPassword// "Password"
0x16f94a  ldstr    aCredentialretr// "CredentialRetrieval"
0x16f94f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x16f954  throw
0x16f955  ldarg.0
0x16f956  ldfld    unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_userNameEncrypted
0x16f95b  brtrue.s loc_16F968
0x16f95d  ldstr    aUsername// "UserName"
0x16f962  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x16f967  throw
0x16f968  ldarg.0
0x16f969  call     instance bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ImpersonateUser()
0x16f96e  brfalse.s loc_16F992
0x16f970  ldarg.0
0x16f971  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16f976  ldc.i4.2
0x16f977  beq.s    loc_16F992
0x16f979  ldarg.0
0x16f97a  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16f97f  ldc.i4.5
0x16f980  beq.s    loc_16F992
0x16f982  ldstr    aImpersonateuse// "ImpersonateUser"
0x16f987  ldstr    aCredentialretr// "CredentialRetrieval"
0x16f98c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x16f991  throw
0x16f992  ldarg.1
0x16f993  brtrue.s loc_16F9A8
0x16f995  ldarg.0
0x16f996  call     instance unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ConnectionStringEncrypted()
0x16f99b  brtrue.s loc_16F9A8
0x16f99d  ldstr    aConnectstring// "ConnectString"
0x16f9a2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x16f9a7  throw
0x16f9a8  ldarg.0
0x16f9a9  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16f9ae  brtrue.s loc_16F9BB
0x16f9b0  ldstr    aCredentialretr// "CredentialRetrieval"
0x16f9b5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x16f9ba  throw
0x16f9bb  ldarg.0
0x16f9bc  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16f9c1  ldc.i4.5
0x16f9c2  bne.un.s loc_16F9DC
0x16f9c4  ldarg.0
0x16f9c5  call     instance bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ImpersonateUser()
0x16f9ca  brtrue.s loc_16F9DC
0x16f9cc  ldstr    aCredentialretr// "CredentialRetrieval"
0x16f9d1  ldstr    aImpersonateuse// "ImpersonateUser"
0x16f9d6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x16f9db  throw
0x16f9dc  ldarg.0
0x16f9dd  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16f9e2  ldc.i4.6
0x16f9e3  bne.un.s loc_16FA10
0x16f9e5  ldarg.0
0x16f9e6  call     instance class Microsoft.ReportingServices.DataExtensions.SecureStoreLookup Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_SecureStoreLookup()
0x16f9eb  brtrue.s loc_16F9F8
0x16f9ed  ldstr    aSecurestoreloo// "SecureStoreLookup"
0x16f9f2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x16f9f7  throw
0x16f9f8  ldarg.0
0x16f9f9  call     instance class Microsoft.ReportingServices.DataExtensions.SecureStoreLookup Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_SecureStoreLookup()
0x16f9fe  callvirt instance string Microsoft.ReportingServices.DataExtensions.SecureStoreLookup::get_TargetApplicationId()
0x16fa03  brtrue.s loc_16FA10
0x16fa05  ldstr    aTargetapplicat// "TargetApplicationId"
0x16fa0a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x16fa0f  throw
0x16fa10  ldarg.0
0x16fa11  call     instance class Microsoft.ReportingServices.DataExtensions.SecureStoreLookup Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_SecureStoreLookup()
0x16fa16  brfalse.s loc_16FA31
0x16fa18  ldarg.0
0x16fa19  call     instance valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_CredentialsRetrieval()
0x16fa1e  ldc.i4.6
0x16fa1f  beq.s    loc_16FA31
0x16fa21  ldstr    aSecurestoreloo// "SecureStoreLookup"
0x16fa26  ldstr    aCredentialretr// "CredentialRetrieval"
0x16fa2b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x16fa30  throw
0x16fa31  ret
```
