# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::GetTokenHandle

- ea: `0x1b70`
- end: `0x1c14`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::GetTokenHandle`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1270`

## callees

- `0x1b70`
- `0x1c20`
- `0x3760`
- `0x37e0`
- `0x3800`
- `0x3820`
- `0x3d70`
- `0x3db0`
- `0x3dc0`
- `0x3f90`

## pseudocode

```c

```

## disassembly

```asm
0x1b70  ldarg.1
0x1b71  ldnull
0x1b72  stind.ref
0x1b73  ldarg.0
0x1b74  callvirt instance bool Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_UsingDefaultCreds()
0x1b79  brtrue.s loc_1B92
0x1b7b  ldarg.0
0x1b7c  callvirt instance string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_Domain()
0x1b81  stloc.0
0x1b82  ldarg.0
0x1b83  callvirt instance string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_UserName()
0x1b88  stloc.1
0x1b89  ldarg.0
0x1b8a  callvirt instance string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_PassWord()
0x1b8f  stloc.2
0x1b90  br.s     loc_1BCC
0x1b92  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x1b97  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_IsFileShareAccountPresent()
0x1b9c  brfalse.s loc_1BC1
0x1b9e  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x1ba3  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_FileShareDomain()
0x1ba8  stloc.0
0x1ba9  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x1bae  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_FileShareUserName()
0x1bb3  stloc.1
0x1bb4  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x1bb9  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_FileSharePassword()
0x1bbe  stloc.2
0x1bbf  br.s     loc_1BCC
0x1bc1  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoFileShareAccount()
0x1bc6  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x1bcb  throw
0x1bcc  nop
0x1bcd  ldloc.0
0x1bce  ldloc.1
0x1bcf  ldloc.2
0x1bd0  ldarg.1
0x1bd1  call     native int Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::GetDomainTokenHandle(string domain, string userName, string password, [out] class [ReportingServicesNativeClient]Util.SafeToken& domainImpToken)
0x1bd6  stloc.3
0x1bd7  leave.s  loc_1C12
0x1bd9  stloc.s  4
0x1bdb  ldloc.s  4
0x1bdd  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x1be2  ldc.i4   0x8007052E
0x1be7  bne.un.s loc_1BF6
0x1be9  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidUserNamePassword()
0x1bee  ldloc.s  4
0x1bf0  newobj   instance void NetworkErrorException::.ctor(string str, class [mscorlib]System.Exception InnerException)
0x1bf5  throw
0x1bf6  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ErrorImpersonatingUser()
0x1bfb  ldloc.s  4
0x1bfd  newobj   instance void NetworkErrorException::.ctor(string str, class [mscorlib]System.Exception InnerException)
0x1c02  throw
0x1c03  stloc.s  5
0x1c05  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ErrorImpersonatingUser()
0x1c0a  ldloc.s  5
0x1c0c  newobj   instance void NetworkErrorException::.ctor(string str, class [mscorlib]System.Exception InnerException)
0x1c11  throw
0x1c12  ldloc.3
0x1c13  ret
```
