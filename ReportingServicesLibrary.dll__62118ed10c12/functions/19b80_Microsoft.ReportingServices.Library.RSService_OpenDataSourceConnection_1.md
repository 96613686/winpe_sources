# Microsoft.ReportingServices.Library.RSService::OpenDataSourceConnection_1

- ea: `0x19b80`
- end: `0x19ddc`
- name: `Microsoft.ReportingServices.Library.RSService::OpenDataSourceConnection_1`
- size: `604`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x19b60`
- `0x1b2f0`

## callees

- `0xf360`
- `0x19a50`
- `0x19b80`
- `0x1e570`
- `0x23b80`
- `0x6d360`

## string_xrefs

- `0x19d3d`: `Data extension '{0}' is configured for model generation. However it doesn't implement IDbConnectionWrapper interface.`
- `0x19d67`: `Data extension '{0}' has failed to return IDbConnectionWrapper.Connection for model generation.`

## pseudocode

```c

```

## disassembly

```asm
0x19b80  ldarg.s  6
0x19b82  ldnull
0x19b83  stind.ref
0x19b84  ldarg.1
0x19b85  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x19b8a  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_IsSurrogatePresent()
0x19b8f  call     bool Microsoft.ReportingServices.Library.Global::get_EnableIntegratedSecurity()
0x19b94  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.ServerDataSourceSettings::.ctor(bool, bool)
0x19b99  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ThrowIfNotUsable(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.ServerDataSourceSettings)
0x19b9e  ldarg.3
0x19b9f  brfalse.s loc_19BAF
0x19ba1  ldarg.1
0x19ba2  call     bool Microsoft.ReportingServices.Library.DataSourceCatalogItem::GoodForUnattendedExecution(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSource)
0x19ba7  brtrue.s loc_19BAF
0x19ba9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x19bae  throw
0x19baf  nop
0x19bb0  ldarg.1
0x19bb1  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Extension()
0x19bb6  ldarg.1
0x19bb7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ModelID()
0x19bbc  ldarg.2
0x19bbd  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.ReportDataSource::.ctor(string, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessing/CreateDataExtensionInstance)
0x19bc2  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.ReportDataSource::CreateConnection()
0x19bc7  stloc.0
0x19bc8  ldloc.0
0x19bc9  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension
0x19bce  stloc.1
0x19bcf  ldloc.0
0x19bd0  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.ITokenDataExtension
0x19bd5  stloc.2
0x19bd6  ldloc.0
0x19bd7  ldarg.s  5
0x19bd9  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_ConnectionString()
0x19bde  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection::set_ConnectionString(string)
0x19be3  ldc.i4.0
0x19be4  stloc.3
0x19be5  ldarg.s  5
0x19be7  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionSecurity [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_ConnectionSecurity()
0x19bec  stloc.s  4
0x19bee  ldnull
0x19bef  stloc.s  5
0x19bf1  ldloc.s  4
0x19bf3  switch   loc_19C60, loc_19C32, loc_19C0D, loc_19C82
0x19c08  br       loc_19CF5
0x19c0d  ldloc.1
0x19c0e  brfalse  loc_19CF5
0x19c13  ldloc.1
0x19c14  ldarg.s  5
0x19c16  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_UserName()
0x19c1b  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_UserName(string)
0x19c20  ldloc.1
0x19c21  ldarg.s  5
0x19c23  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_DecryptedPassword()
0x19c28  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_Password(string)
0x19c2d  br       loc_19CF5
0x19c32  ldarg.s  5
0x19c34  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_UserName()
0x19c39  ldarg.s  5
0x19c3b  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SecureStringWrapper [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_Password()
0x19c40  ldarg.s  5
0x19c42  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_DomainName()
0x19c47  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext::.ctor(string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SecureStringWrapper, string)
0x19c4c  stloc.s  5
0x19c4e  ldloc.1
0x19c4f  brfalse  loc_19CF5
0x19c54  ldloc.1
0x19c55  ldc.i4.1
0x19c56  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_IntegratedSecurity(bool)
0x19c5b  br       loc_19CF5
0x19c60  ldarg.3
0x19c61  brfalse.s loc_19C69
0x19c63  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x19c68  throw
0x19c69  ldarg.0
0x19c6a  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x19c6f  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext)
0x19c74  stloc.s  5
0x19c76  ldloc.1
0x19c77  brfalse.s loc_19CF5
0x19c79  ldloc.1
0x19c7a  ldc.i4.1
0x19c7b  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_IntegratedSecurity(bool)
0x19c80  br.s     loc_19CF5
0x19c82  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x19c87  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_IsSurrogatePresent()
0x19c8c  brfalse.s loc_19C97
0x19c8e  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext Microsoft.ReportingServices.Library.SurrogateContextFactory::CreateSurrogateContext()
0x19c93  stloc.s  5
0x19c95  br.s     loc_19CA0
0x19c97  ldloc.3
0x19c98  brtrue.s loc_19CA0
0x19c9a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x19c9f  throw
0x19ca0  ldloc.3
0x19ca1  brfalse.s loc_19CF5
0x19ca3  ldarg.0
0x19ca4  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x19ca9  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AdditionalUserToken()
0x19cae  stloc.s  6
0x19cb0  ldloc.s  6
0x19cb2  brtrue.s loc_19CDD
0x19cb4  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x19cb9  brfalse.s loc_19CDD
0x19cbb  ldarg.0
0x19cbc  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x19cc1  callvirt instance class [System]System.Uri [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext::get_ReportServerVirtualDirectoryUri()
0x19cc6  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x19ccb  call     instance void Microsoft.ReportingServices.Library.RSService::PopulateAdditionalToken(string itemPath)
0x19cd0  ldarg.0
0x19cd1  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x19cd6  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AdditionalUserToken()
0x19cdb  stloc.s  6
0x19cdd  ldloc.s  6
0x19cdf  brfalse.s loc_19CEB
0x19ce1  ldloc.2
0x19ce2  ldloc.s  6
0x19ce4  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.ITokenDataExtension::SetUserToken(unsigned int8[])
0x19ce9  br.s     loc_19CF5
0x19ceb  ldloc.s  5
0x19ced  brtrue.s loc_19CF5
0x19cef  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x19cf4  throw
0x19cf5  ldarg.1
0x19cf6  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_ImpersonateUser()
0x19cfb  brfalse.s loc_19D28
0x19cfd  ldloc.1
0x19cfe  brfalse.s loc_19D28
0x19d00  ldarg.s  5
0x19d02  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_ImpersonateUserName()
0x19d07  brfalse.s loc_19D28
0x19d09  ldloc.1
0x19d0a  ldarg.s  5
0x19d0c  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_ImpersonateUserName()
0x19d11  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_Impersonate(string)
0x19d16  leave.s  loc_19D28
0x19d18  stloc.s  7
0x19d1a  ldarg.1
0x19d1b  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Name()
0x19d20  ldloc.s  7
0x19d22  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSourceOpenException::.ctor(string, class [mscorlib]System.Exception)
0x19d27  throw
0x19d28  ldarg.s  4
0x19d2a  brfalse.s loc_19D98
0x19d2c  ldloc.0
0x19d2d  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionWrapper
0x19d32  stloc.s  8
0x19d34  ldloc.s  8
0x19d36  brtrue.s loc_19D53
0x19d38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19d3d  ldstr    aDataExtension0// "Data extension '{0}' is configured for "...
0x19d42  ldarg.1
0x19d43  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Extension()
0x19d48  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x19d4d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x19d52  throw
0x19d53  ldarg.s  6
0x19d55  ldloc.s  8
0x19d57  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionWrapper::get_Connection()
0x19d5c  stind.ref
0x19d5d  ldarg.s  6
0x19d5f  ldind.ref
0x19d60  brtrue.s loc_19D7D
0x19d62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19d67  ldstr    aDataExtension0_0// "Data extension '{0}' has failed to retu"...
0x19d6c  ldarg.1
0x19d6d  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Extension()
0x19d72  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x19d77  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x19d7c  throw
0x19d7d  nop
0x19d7e  ldarg.s  6
0x19d80  ldind.ref
0x19d81  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x19d86  leave.s  loc_19DB1
0x19d88  stloc.s  9
0x19d8a  ldarg.1
0x19d8b  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Name()
0x19d90  ldloc.s  9
0x19d92  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSourceOpenException::.ctor(string, class [mscorlib]System.Exception)
0x19d97  throw
0x19d98  nop
0x19d99  ldloc.0
0x19d9a  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection::Open()
0x19d9f  leave.s  loc_19DB1
0x19da1  stloc.s  0xA
0x19da3  ldarg.1
0x19da4  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Name()
0x19da9  ldloc.s  0xA
0x19dab  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DataSourceOpenException::.ctor(string, class [mscorlib]System.Exception)
0x19db0  throw
0x19db1  leave.s  loc_19DBF
0x19db3  ldloc.s  5
0x19db5  brfalse.s loc_19DBE
0x19db7  ldloc.s  5
0x19db9  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext::Dispose()
0x19dbe  endfinally
0x19dbf  ldloc.0
0x19dc0  stloc.s  0xB
0x19dc2  leave.s  loc_19DD9
0x19dc4  stloc.s  0xC
0x19dc6  ldloc.s  0xC
0x19dc8  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x19dcd  brtrue.s loc_19DD7
0x19dcf  ldloc.s  0xC
0x19dd1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotPrepareQueryException::.ctor(class [mscorlib]System.Exception)
0x19dd6  throw
0x19dd7  rethrow
0x19dd9  ldloc.s  0xB
0x19ddb  ret
```
