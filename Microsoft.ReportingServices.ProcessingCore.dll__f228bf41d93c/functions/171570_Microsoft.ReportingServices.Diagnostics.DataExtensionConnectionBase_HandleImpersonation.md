# Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::HandleImpersonation

- ea: `0x171570`
- end: `0x1718b4`
- name: `Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::HandleImpersonation`
- size: `836`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1718c0`

## callees

- `0x16fc70`
- `0x170150`
- `0x171000`
- `0x171010`
- `0x171570`
- `0x171a10`
- `0x171c20`
- `0x171c40`
- `0x171c60`
- `0x171d20`
- `0x175de0`
- `0x175e50`
- `0x184370`
- `0x184740`
- `0x184780`
- `0x1847a0`
- `0x1847c0`
- `0x184800`
- `0x184850`
- `0x184970`

## string_xrefs

- `0x171593`: `afterImpersonationAction must be non-null`

## pseudocode

```c

```

## disassembly

```asm
0x171570  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x171575  ldarg.1
0x171576  brtrue.s loc_17157E
0x171578  ldarg.2
0x171579  ldnull
0x17157a  cgt.un
0x17157c  br.s     loc_17157F
0x17157e  ldc.i4.1
0x17157f  ldstr    aAtLeastOneOfDa// "At least one of dataSourceObj or dataSo"...
0x171584  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x171589  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x17158e  ldarg.s  5
0x171590  ldnull
0x171591  cgt.un
0x171593  ldstr    aAfterimpersona// "afterImpersonationAction must be non-nu"...
0x171598  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x17159d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x1715a2  ldarg.s  4
0x1715a4  ldnull
0x1715a5  cgt.un
0x1715a7  ldstr    aConnMustBeNonN// "conn must be non-null"
0x1715ac  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1715b1  ldarg.1
0x1715b2  brfalse.s loc_1715BD
0x1715b4  ldarg.1
0x1715b5  callvirt instance string Microsoft.ReportingServices.ReportProcessing.IProcessingDataSource::get_Name()
0x1715ba  stloc.0
0x1715bb  br.s     loc_1715C4
0x1715bd  ldarg.2
0x1715be  callvirt instance string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_Name()
0x1715c3  stloc.0
0x1715c4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1715c9  stloc.1
0x1715ca  ldarg.2
0x1715cb  brfalse.s loc_1715FD
0x1715cd  ldarg.0
0x1715ce  ldfld    valuetype ExecutionType Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::m_execType
0x1715d3  ldc.i4.1
0x1715d4  bne.un.s loc_1715E5
0x1715d6  ldarg.0
0x1715d7  ldarg.2
0x1715d8  callvirt instance bool Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::GoodForExecutionUnderServiceAccount(class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo)
0x1715dd  brtrue.s loc_1715FD
0x1715df  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x1715e4  throw
0x1715e5  ldarg.0
0x1715e6  ldfld    valuetype ExecutionType Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::m_execType
0x1715eb  ldc.i4.2
0x1715ec  bne.un.s loc_1715FD
0x1715ee  ldarg.0
0x1715ef  ldarg.2
0x1715f0  callvirt instance bool Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::GoodForUnattendedSurrogateExecution(class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo)
0x1715f5  brtrue.s loc_1715FD
0x1715f7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x1715fc  throw
0x1715fd  ldarg.2
0x1715fe  brfalse.s loc_171624
0x171600  ldarg.2
0x171601  callvirt instance class Microsoft.ReportingServices.DataExtensions.DataSourceFaultContext Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_DataSourceFaultContext()
0x171606  brfalse.s loc_171624
0x171608  ldarg.2
0x171609  callvirt instance class Microsoft.ReportingServices.DataExtensions.DataSourceFaultContext Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_DataSourceFaultContext()
0x17160e  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode Microsoft.ReportingServices.DataExtensions.DataSourceFaultContext::get_ErrorCode()
0x171613  ldarg.2
0x171614  callvirt instance class Microsoft.ReportingServices.DataExtensions.DataSourceFaultContext Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_DataSourceFaultContext()
0x171619  callvirt instance string Microsoft.ReportingServices.DataExtensions.DataSourceFaultContext::get_ErrorString()
0x17161e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.FaultedDataSourceException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, string)
0x171623  throw
0x171624  ldarg.0
0x171625  ldarg.1
0x171626  ldarg.2
0x171627  ldloca.s 1
0x171629  call     instance class Microsoft.ReportingServices.ReportProcessing.ConnectionContext Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::GetConnectionContext(class Microsoft.ReportingServices.ReportProcessing.IProcessingDataSource dataSourceObj, class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo, [out] valuetype [mscorlib]System.Guid& modelId)
0x17162e  stloc.2
0x17162f  ldarg.s  4
0x171631  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension
0x171636  stloc.3
0x171637  ldarg.s  4
0x171639  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.ITokenDataExtension
0x17163e  stloc.s  4
0x171640  ldc.i4.0
0x171641  stloc.s  5
0x171643  ldarg.s  4
0x171645  isinst   [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.DataExtensions.ConnectionWrapper
0x17164a  stloc.s  6
0x17164c  ldloc.s  6
0x17164e  brfalse.s loc_171659
0x171650  ldloc.s  6
0x171652  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.DataExtensions.ConnectionWrapper::get_WrappedManagedProvider()
0x171657  br.s     loc_17165A
0x171659  ldc.i4.0
0x17165a  stloc.s  7
0x17165c  ldnull
0x17165d  stloc.s  8
0x17165f  ldloc.3
0x171660  brtrue.s loc_1716A8
0x171662  ldloc.s  7
0x171664  brtrue.s loc_171685
0x171666  ldc.i4.3
0x171667  ldloc.2
0x171668  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ConnectionSecurity Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_ConnectionSecurity()
0x17166d  beq.s    loc_171685
0x17166f  ldc.i4   0x9D
0x171674  ldnull
0x171675  ldc.i4.1
0x171676  newarr   [mscorlib]System.Object
0x17167b  dup
0x17167c  ldc.i4.0
0x17167d  ldloc.0
0x17167e  stelem.ref
0x17167f  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x171684  throw
0x171685  ldloc.s  7
0x171687  brfalse.s loc_1716A8
0x171689  ldc.i4.2
0x17168a  ldloc.2
0x17168b  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ConnectionSecurity Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_ConnectionSecurity()
0x171690  bne.un.s loc_1716A8
0x171692  ldc.i4   0x9E
0x171697  ldnull
0x171698  ldc.i4.1
0x171699  newarr   [mscorlib]System.Object
0x17169e  dup
0x17169f  ldc.i4.0
0x1716a0  ldloc.0
0x1716a1  stelem.ref
0x1716a2  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x1716a7  throw
0x1716a8  nop
0x1716a9  ldloc.2
0x1716aa  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ConnectionSecurity Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_ConnectionSecurity()
0x1716af  stloc.s  9
0x1716b1  ldloc.s  9
0x1716b3  switch   loc_171790, loc_1716F4, loc_1716D1, loc_1717D3, loc_17173B
0x1716cc  br       loc_17181C
0x1716d1  ldloc.3
0x1716d2  brfalse  loc_17181C
0x1716d7  ldloc.3
0x1716d8  ldloc.2
0x1716d9  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_UserName()
0x1716de  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_UserName(string)
0x1716e3  ldloc.3
0x1716e4  ldloc.2
0x1716e5  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_DecryptedPassword()
0x1716ea  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_Password(string)
0x1716ef  br       loc_17181C
0x1716f4  nop
0x1716f5  ldloc.2
0x1716f6  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_UserName()
0x1716fb  ldloc.2
0x1716fc  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SecureStringWrapper Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_Password()
0x171701  ldloc.2
0x171702  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_DomainName()
0x171707  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext::.ctor(string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SecureStringWrapper, string)
0x17170c  stloc.s  8
0x17170e  leave.s  loc_171729
0x171710  stloc.s  0xA
0x171712  ldc.i4   0x9A
0x171717  ldloc.s  0xA
0x171719  ldc.i4.1
0x17171a  newarr   [mscorlib]System.Object
0x17171f  dup
0x171720  ldc.i4.0
0x171721  ldloc.0
0x171722  stelem.ref
0x171723  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x171728  throw
0x171729  ldloc.3
0x17172a  brfalse  loc_17181C
0x17172f  ldloc.3
0x171730  ldc.i4.1
0x171731  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_IntegratedSecurity(bool)
0x171736  br       loc_17181C
0x17173b  ldloc.3
0x17173c  brfalse.s loc_171746
0x17173e  ldloc.3
0x17173f  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IConnectionRevertToServiceAccount
0x171744  brtrue.s loc_17175B
0x171746  ldc.i4   0x9C
0x17174b  ldc.i4.1
0x17174c  newarr   [mscorlib]System.Object
0x171751  dup
0x171752  ldc.i4.0
0x171753  ldloc.0
0x171754  stelem.ref
0x171755  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, object[] arguments)
0x17175a  throw
0x17175b  nop
0x17175c  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext::.ctor()
0x171761  stloc.s  8
0x171763  leave.s  loc_17177E
0x171765  stloc.s  0xB
0x171767  ldc.i4   0x9B
0x17176c  ldloc.s  0xB
0x17176e  ldc.i4.1
0x17176f  newarr   [mscorlib]System.Object
0x171774  dup
0x171775  ldc.i4.0
0x171776  ldloc.0
0x171777  stelem.ref
0x171778  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x17177d  throw
0x17177e  ldloc.3
0x17177f  brfalse  loc_17181C
0x171784  ldloc.3
0x171785  ldc.i4.1
0x171786  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_IntegratedSecurity(bool)
0x17178b  br       loc_17181C
0x171790  ldarg.0
0x171791  ldfld    valuetype ExecutionType Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::m_execType
0x171796  brfalse.s loc_17179E
0x171798  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x17179d  throw
0x17179e  nop
0x17179f  ldarg.0
0x1717a0  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::m_threadUser
0x1717a5  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext)
0x1717aa  stloc.s  8
0x1717ac  leave.s  loc_1717C7
0x1717ae  stloc.s  0xC
0x1717b0  ldc.i4   0x9A
0x1717b5  ldloc.s  0xC
0x1717b7  ldc.i4.1
0x1717b8  newarr   [mscorlib]System.Object
0x1717bd  dup
0x1717be  ldc.i4.0
0x1717bf  ldloc.0
0x1717c0  stelem.ref
0x1717c1  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x1717c6  throw
0x1717c7  ldloc.3
0x1717c8  brfalse.s loc_17181C
0x1717ca  ldloc.3
0x1717cb  ldc.i4.1
0x1717cc  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_IntegratedSecurity(bool)
0x1717d1  br.s     loc_17181C
0x1717d3  ldarg.0
0x1717d4  ldloca.s 8
0x1717d6  callvirt instance bool Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::TryCreateImpersonationContextForNoCredentials([out] class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext& impersonationContext)
0x1717db  brtrue.s loc_1717E7
0x1717dd  ldloc.s  5
0x1717df  brtrue.s loc_1717E7
0x1717e1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x1717e6  throw
0x1717e7  ldloc.s  5
0x1717e9  brfalse.s loc_17181C
0x1717eb  ldarg.0
0x1717ec  ldfld    class Microsoft.ReportingServices.ReportProcessing.IAdditionalToken Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::m_additionalToken
0x1717f1  brtrue.s loc_1717F6
0x1717f3  ldnull
0x1717f4  br.s     loc_171801
0x1717f6  ldarg.0
0x1717f7  ldfld    class Microsoft.ReportingServices.ReportProcessing.IAdditionalToken Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::m_additionalToken
0x1717fc  callvirt instance unsigned int8[] Microsoft.ReportingServices.ReportProcessing.IAdditionalToken::GetAdditionalToken()
0x171801  stloc.s  0xD
0x171803  ldloc.s  0xD
0x171805  brfalse.s loc_171812
0x171807  ldloc.s  4
0x171809  ldloc.s  0xD
0x17180b  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.ITokenDataExtension::SetUserToken(unsigned int8[])
0x171810  br.s     loc_17181C
0x171812  ldloc.s  8
0x171814  brtrue.s loc_17181C
0x171816  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialSettingException::.ctor()
0x17181b  throw
0x17181c  ldloc.2
0x17181d  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ConnectionContext::get_ImpersonateUser()
0x171822  brfalse.s loc_17189E
0x171824  ldloc.3
0x171825  brfalse.s loc_17189E
0x171827  ldloc.3
0x171828  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IImpersonationFormat
0x17182d  stloc.s  0xE
0x17182f  ldloc.s  0xE
0x171831  brfalse.s loc_171872
0x171833  ldloc.s  0xE
0x171835  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.ImpersonationFormat [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IImpersonationFormat::GetImpersonationFormat()
0x17183a  ldc.i4.1
0x17183b  bne.un.s loc_171872
0x17183d  ldarg.0
0x17183e  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::m_threadUser
0x171843  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x171848  ldc.i4.1
0x171849  bne.un.s loc_171872
0x17184b  ldarg.0
0x17184c  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Diagnostics.DataExtensionConnectionBase::m_threadUser
0x171851  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ImpersonationContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext)
0x171856  stloc.s  0xF
0x171858  ldloc.3
0x171859  ldc.i4.8
0x17185a  call     string Microsoft.ReportingServices.Diagnostics.UserNameLookup::LookupUsername(valuetype Microsoft.ReportingServices.Diagnostics.ExtendedNameFormat usernameformat)
0x17185f  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnectionExtension::set_Impersonate(string)
0x171864  leave.s  loc_171883
0x171866  ldloc.s  0xF
0x171868  brfalse.s loc_171871
0x17186a  ldloc.s  0xF
0x17186c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x171871  endfinally
0x171872  ldloc.3
0x171873  ldarg.0
  ... truncated ...
```
