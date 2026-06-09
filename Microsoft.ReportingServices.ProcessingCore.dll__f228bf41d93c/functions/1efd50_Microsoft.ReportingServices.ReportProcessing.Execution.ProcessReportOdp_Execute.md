# Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::Execute

- ea: `0x1efd50`
- end: `0x1effba`
- name: `Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::Execute`
- size: `618`
- prototype: ``
- caller_count: `10`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x1779e0`
- `0x177ed0`
- `0x1786a0`
- `0x1efc20`
- `0x1f1160`
- `0x1f12c0`
- `0x1f13f0`
- `0x1f14a0`
- `0x1f1590`
- `0x1f2150`

## callees

- `0x175de0`
- `0x181ee0`
- `0x1837c0`
- `0x183f30`
- `0x184420`
- `0x1efd50`
- `0x1effc0`
- `0x1effe0`
- `0x1efff0`
- `0x1f0060`
- `0x1f0080`
- `0x1f0100`
- `0x1f0110`
- `0x1f0120`
- `0x1f01b0`
- `0x1fb1d0`
- `0x1fb430`
- `0x1fb440`
- `0x1fb620`
- `0x1fc4a0`
- `0x200300`
- `0x2003d0`
- `0x23faa0`
- `0x23fb00`
- `0x23fb10`
- `0x23fb20`
- `0x23fb30`
- `0x23fb40`

## string_xrefs

- `0x1efefb`: `Data source '{0}': Committing transaction.`

## pseudocode

```c

```

## disassembly

```asm
0x1efd50  ldarg.0
0x1efd51  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IConfiguration Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::m_configuration
0x1efd56  call     void Microsoft.ReportingServices.ReportProcessing.ReportProcessingCompatibilityVersion::TraceCompatibilityVersion(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IConfiguration configuration)
0x1efd5b  ldarg.1
0x1efd5c  ldnull
0x1efd5d  stind.ref
0x1efd5e  ldarg.0
0x1efd5f  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::PrepareMetadata()
0x1efd64  stloc.0
0x1efd65  ldloc.0
0x1efd66  ldarg.0
0x1efd67  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.GlobalIDOwnerCollection Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::m_globalIDOwnerCollection
0x1efd6c  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::set_GlobalIDOwnerCollection(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.GlobalIDOwnerCollection value)
0x1efd71  ldloc.0
0x1efd72  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x1efd77  stloc.1
0x1efd78  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1efd7d  ldloc.1
0x1efd7e  ldnull
0x1efd7f  cgt.un
0x1efd81  ldstr    aReportsnapshot// "ReportSnapshot object must exist"
0x1efd86  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1efd8b  ldc.i4.0
0x1efd8c  stloc.2
0x1efd8d  ldarg.0
0x1efd8e  call     instance class Microsoft.ReportingServices.ReportProcessing.ProcessingContext Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::get_PublicProcessingContext()
0x1efd93  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_Parameters()
0x1efd98  brfalse.s loc_1EFDAD
0x1efd9a  ldloc.2
0x1efd9b  ldarg.0
0x1efd9c  call     instance class Microsoft.ReportingServices.ReportProcessing.ProcessingContext Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::get_PublicProcessingContext()
0x1efda1  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_Parameters()
0x1efda6  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::get_UserProfileState()
0x1efdab  or
0x1efdac  stloc.2
0x1efdad  ldarg.1
0x1efdae  ldarg.0
0x1efdaf  ldloc.0
0x1efdb0  ldloc.1
0x1efdb1  ldloc.2
0x1efdb2  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::CreateOnDemandContext(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata odpMetadata, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot reportSnapshot, valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState initialUserDependency)
0x1efdb7  stind.ref
0x1efdb8  ldarg.0
0x1efdb9  ldarg.1
0x1efdba  ldind.ref
0x1efdbb  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::CompleteOdpContext(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext)
0x1efdc0  ldarg.0
0x1efdc1  ldarg.1
0x1efdc2  ldind.ref
0x1efdc3  ldloc.0
0x1efdc4  ldloc.1
0x1efdc5  ldloca.s 3
0x1efdc7  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportInstance Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::CreateReportInstance(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata odpMetadata, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot reportSnapshot, [out] class Microsoft.ReportingServices.OnDemandProcessing.Merge& odpMerge)
0x1efdcc  stloc.s  4
0x1efdce  ldarg.0
0x1efdcf  ldarg.1
0x1efdd0  ldind.ref
0x1efdd1  ldloc.3
0x1efdd2  ldloc.s  4
0x1efdd4  ldloc.1
0x1efdd5  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::PreProcessSnapshot(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext, class Microsoft.ReportingServices.OnDemandProcessing.Merge odpMerge, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportInstance reportInstance, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot reportSnapshot)
0x1efdda  ldarg.1
0x1efddb  ldind.ref
0x1efddc  ldc.i4.1
0x1efddd  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::set_SnapshotProcessing(bool value)
0x1efde2  ldarg.1
0x1efde3  ldind.ref
0x1efde4  ldc.i4.1
0x1efde5  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::set_IsUnrestrictedRenderFormatReferenceMode(bool value)
0x1efdea  ldarg.0
0x1efdeb  ldarg.1
0x1efdec  ldind.ref
0x1efded  ldloc.s  4
0x1efdef  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::ResetEnvironment(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportInstance reportInstance)
0x1efdf4  ldarg.1
0x1efdf5  ldind.ref
0x1efdf6  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ThreadCulture()
0x1efdfb  brfalse.s loc_1EFE0E
0x1efdfd  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1efe02  ldarg.1
0x1efe03  ldind.ref
0x1efe04  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ThreadCulture()
0x1efe09  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x1efe0e  ldarg.0
0x1efe0f  ldarg.1
0x1efe10  ldind.ref
0x1efe11  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::UpdateUserProfileLocation(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext)
0x1efe16  ldloc.1
0x1efe17  stloc.s  5
0x1efe19  leave    loc_1EFFB7
0x1efe1e  ldarg.0
0x1efe1f  ldarg.1
0x1efe20  ldind.ref
0x1efe21  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Execution.ProcessReportOdp::CleanupAbortHandler(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext)
0x1efe26  ldarg.1
0x1efe27  ldind.ref
0x1efe28  brfalse  loc_1EFFB6
0x1efe2d  ldarg.1
0x1efe2e  ldind.ref
0x1efe2f  callvirt instance class DataSourceInfoHashtable Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_GlobalDataSourceInfo()
0x1efe34  brfalse  loc_1EFFB6
0x1efe39  ldarg.1
0x1efe3a  ldind.ref
0x1efe3b  callvirt instance class DataSourceInfoHashtable Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_GlobalDataSourceInfo()
0x1efe40  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x1efe45  brfalse  loc_1EFFB6
0x1efe4a  ldarg.1
0x1efe4b  ldind.ref
0x1efe4c  callvirt instance class DataSourceInfoHashtable Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_GlobalDataSourceInfo()
0x1efe51  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x1efe56  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1efe5b  stloc.s  6
0x1efe5d  br       loc_1EFF93
0x1efe62  ldloc.s  6
0x1efe64  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1efe69  castclass DataSourceInfo
0x1efe6e  stloc.s  7
0x1efe70  ldloc.s  7
0x1efe72  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x1efe77  brfalse  loc_1EFF48
0x1efe7c  ldloc.s  7
0x1efe7e  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x1efe83  ldfld    bool TransactionInfo::RollbackRequired
0x1efe88  brfalse.s loc_1EFEE9
0x1efe8a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1efe8f  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x1efe94  brfalse.s loc_1EFEB6
0x1efe96  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1efe9b  ldc.i4.3
0x1efe9c  ldstr    aDataSource0Rol// "Data source '{0}': Rolling back transac"...
0x1efea1  ldc.i4.1
0x1efea2  newarr   [mscorlib]System.Object
0x1efea7  dup
0x1efea8  ldc.i4.0
0x1efea9  ldloc.s  7
0x1efeab  callvirt instance string DataSourceInfo::get_DataSourceName()
0x1efeb0  stelem.ref
0x1efeb1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1efeb6  nop
0x1efeb7  ldloc.s  7
0x1efeb9  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x1efebe  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction TransactionInfo::get_Transaction()
0x1efec3  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction::Rollback()
0x1efec8  leave.s  loc_1EFF48
0x1efeca  stloc.s  8
0x1efecc  ldc.i4   0xA0
0x1efed1  ldloc.s  8
0x1efed3  ldc.i4.1
0x1efed4  newarr   [mscorlib]System.Object
0x1efed9  dup
0x1efeda  ldc.i4.0
0x1efedb  ldloc.s  7
0x1efedd  callvirt instance string DataSourceInfo::get_DataSourceName()
0x1efee2  stelem.ref
0x1efee3  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x1efee8  throw
0x1efee9  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1efeee  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1efef3  brfalse.s loc_1EFF15
0x1efef5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1efefa  ldc.i4.4
0x1efefb  ldstr    aDataSource0Com// "Data source '{0}': Committing transacti"...
0x1eff00  ldc.i4.1
0x1eff01  newarr   [mscorlib]System.Object
0x1eff06  dup
0x1eff07  ldc.i4.0
0x1eff08  ldloc.s  7
0x1eff0a  callvirt instance string DataSourceInfo::get_DataSourceName()
0x1eff0f  stelem.ref
0x1eff10  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1eff15  nop
0x1eff16  ldloc.s  7
0x1eff18  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x1eff1d  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction TransactionInfo::get_Transaction()
0x1eff22  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction::Commit()
0x1eff27  leave.s  loc_1EFF48
0x1eff29  stloc.s  9
0x1eff2b  ldc.i4   0xA1
0x1eff30  ldloc.s  9
0x1eff32  ldc.i4.1
0x1eff33  newarr   [mscorlib]System.Object
0x1eff38  dup
0x1eff39  ldc.i4.0
0x1eff3a  ldloc.s  7
0x1eff3c  callvirt instance string DataSourceInfo::get_DataSourceName()
0x1eff41  stelem.ref
0x1eff42  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x1eff47  throw
0x1eff48  ldloc.s  7
0x1eff4a  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection DataSourceInfo::get_Connection()
0x1eff4f  brfalse.s loc_1EFF93
0x1eff51  ldarg.1
0x1eff52  ldind.ref
0x1eff53  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_CreateAndSetupDataExtensionFunction()
0x1eff58  ldloc.s  7
0x1eff5a  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection DataSourceInfo::get_Connection()
0x1eff5f  ldloc.s  7
0x1eff61  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IProcessingDataSource DataSourceInfo::get_ProcDataSourceInfo()
0x1eff66  ldloc.s  7
0x1eff68  callvirt instance class Microsoft.ReportingServices.DataExtensions.DataSourceInfo DataSourceInfo::get_DataExtDataSourceInfo()
0x1eff6d  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection::CloseConnection(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection connection, class Microsoft.ReportingServices.ReportProcessing.IProcessingDataSource dataSource, class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo)
0x1eff72  leave.s  loc_1EFF93
0x1eff74  stloc.s  0xA
0x1eff76  ldc.i4   0x9F
0x1eff7b  ldloc.s  0xA
0x1eff7d  ldc.i4.1
0x1eff7e  newarr   [mscorlib]System.Object
0x1eff83  dup
0x1eff84  ldc.i4.0
0x1eff85  ldloc.s  7
0x1eff87  callvirt instance string DataSourceInfo::get_DataSourceName()
0x1eff8c  stelem.ref
0x1eff8d  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x1eff92  throw
0x1eff93  ldloc.s  6
0x1eff95  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1eff9a  brtrue   loc_1EFE62
0x1eff9f  leave.s  loc_1EFFB6
0x1effa1  ldloc.s  6
0x1effa3  isinst   [mscorlib]System.IDisposable
0x1effa8  stloc.s  0xB
0x1effaa  ldloc.s  0xB
0x1effac  brfalse.s loc_1EFFB5
0x1effae  ldloc.s  0xB
0x1effb0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1effb5  endfinally
0x1effb6  endfinally
0x1effb7  ldloc.s  5
0x1effb9  ret
```
