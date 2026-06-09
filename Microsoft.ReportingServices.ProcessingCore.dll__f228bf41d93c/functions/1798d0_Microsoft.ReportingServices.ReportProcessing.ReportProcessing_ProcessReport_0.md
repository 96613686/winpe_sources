# Microsoft.ReportingServices.ReportProcessing.ReportProcessing::ProcessReport_0

- ea: `0x1798d0`
- end: `0x179cf4`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportProcessing::ProcessReport_0`
- size: `1060`
- prototype: ``
- caller_count: `2`
- callee_count: `71`
- tags: `service_task, broker_com_uri`

## callers

- `0x177c20`
- `0x179390`

## callees

- `0x175de0`
- `0x176790`
- `0x1793d0`
- `0x1798d0`
- `0x1837a0`
- `0x1837b0`
- `0x1837c0`
- `0x1837e0`
- `0x183840`
- `0x183860`
- `0x183880`
- `0x1838a0`
- `0x1838d0`
- `0x183950`
- `0x184410`
- `0x1901d0`
- `0x1903f0`
- `0x195c20`
- `0x195ca0`
- `0x196090`
- `0x1a8810`
- `0x1a88d0`
- `0x1a8930`
- `0x1a8950`
- `0x1a8a10`
- `0x1a8b20`
- `0x1a8b70`
- `0x1a8bc0`
- `0x1a8c10`
- `0x1a8c60`
- `0x1a8cb0`
- `0x23faa0`
- `0x23fb00`
- `0x23fb30`
- `0x23fb40`
- `0x240590`
- `0x2405c0`
- `0x2405f0`
- `0x240600`
- `0x240610`
- `0x240630`
- `0x240650`
- `0x240670`
- `0x240680`
- `0x2406b0`
- `0x2406d0`
- `0x240710`
- `0x240720`
- `0x240760`
- `0x240770`

## string_xrefs

- `0x179c1c`: `Data source '{0}': Committing transaction.`

## pseudocode

```c

```

## disassembly

```asm
0x1798d0  ldnull
0x1798d1  stloc.0
0x1798d2  ldnull
0x1798d3  stloc.1
0x1798d4  ldarg.0
0x1798d5  ldarg.1
0x1798d6  ldc.i4.0
0x1798d7  ldarg.3
0x1798d8  call     instance bool Microsoft.ReportingServices.ReportProcessing.ReportProcessing::HasUserSortFilter(class Microsoft.ReportingServices.ReportProcessing.Report report, unsigned int32 subreportLevel, class ProcessingContext context)
0x1798dd  stloc.2
0x1798de  ldarg.2
0x1798df  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_InitialUserProfileState()
0x1798e4  ldc.i4.1
0x1798e5  and
0x1798e6  ldc.i4.0
0x1798e7  ble.s    loc_1798FC
0x1798e9  ldarg.3
0x1798ea  ldloc.2
0x1798eb  callvirt instance void ProcessingContext::set_SaveSnapshotData(bool value)
0x1798f0  ldarg.3
0x1798f1  ldloc.2
0x1798f2  ldc.i4.0
0x1798f3  ceq
0x1798f5  callvirt instance void ProcessingContext::set_StopSaveSnapshotDataOnError(bool value)
0x1798fa  br.s     loc_17991E
0x1798fc  ldarg.2
0x1798fd  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_InitialUserProfileState()
0x179902  ldc.i4.2
0x179903  and
0x179904  brtrue.s loc_17991E
0x179906  ldarg.3
0x179907  ldarg.1
0x179908  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.Report::get_ParametersNotUsedInQuery()
0x17990d  ldloc.2
0x17990e  or
0x17990f  callvirt instance void ProcessingContext::set_SaveSnapshotData(bool value)
0x179914  ldarg.3
0x179915  ldloc.2
0x179916  ldc.i4.0
0x179917  ceq
0x179919  callvirt instance void ProcessingContext::set_StopSaveSnapshotDataOnError(bool value)
0x17991e  ldarg.2
0x17991f  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_IsHistorySnapshot()
0x179924  brfalse.s loc_179934
0x179926  ldarg.3
0x179927  ldc.i4.1
0x179928  callvirt instance void ProcessingContext::set_SaveSnapshotData(bool value)
0x17992d  ldarg.3
0x17992e  ldc.i4.0
0x17992f  callvirt instance void ProcessingContext::set_StopSaveSnapshotDataOnError(bool value)
0x179934  ldarg.s  4
0x179936  ldc.i4.0
0x179937  stind.i4
0x179938  ldarg.1
0x179939  ldarg.2
0x17993a  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_ReportContext()
0x17993f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ItemName()
0x179944  ldarg.2
0x179945  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_Parameters()
0x17994a  ldarg.2
0x17994b  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_RequestUserName()
0x179950  ldarg.3
0x179951  callvirt instance valuetype [mscorlib]System.DateTime ProcessingContext::get_ExecutionTime()
0x179956  ldarg.2
0x179957  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_ReportContext()
0x17995c  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_HostRootUri()
0x179961  ldarg.2
0x179962  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_ReportContext()
0x179967  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ParentPath()
0x17996c  ldarg.2
0x17996d  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_UserLanguage()
0x179972  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x179977  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::.ctor(class Microsoft.ReportingServices.ReportProcessing.Report report, string reportName, class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection parameters, string requestUserName, valuetype [mscorlib]System.DateTime executionTime, string reportServerUrl, string reportFolder, string language)
0x17997c  stloc.0
0x17997d  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x179982  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x179987  stloc.1
0x179988  ldarg.1
0x179989  ldarg.3
0x17998a  newobj   instance void Merge::.ctor(class Microsoft.ReportingServices.ReportProcessing.Report report, class ProcessingContext context)
0x17998f  stloc.3
0x179990  ldarg.3
0x179991  callvirt instance bool ProcessingContext::get_SnapshotProcessing()
0x179996  brtrue.s loc_1799BD
0x179998  ldarg.3
0x179999  callvirt instance bool ProcessingContext::get_ProcessWithCachedData()
0x17999e  brtrue.s loc_1799BD
0x1799a0  ldloc.3
0x1799a1  ldarg.2
0x1799a2  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_Parameters()
0x1799a7  ldc.i4.0
0x1799a8  callvirt instance bool Merge::PrefetchData(class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection parameters, bool mergeTran)
0x1799ad  brfalse.s loc_1799BD
0x1799af  ldarg.3
0x1799b0  ldc.i4.1
0x1799b1  callvirt instance void ProcessingContext::set_SnapshotProcessing(bool value)
0x1799b6  ldarg.3
0x1799b7  ldc.i4.1
0x1799b8  callvirt instance void ProcessingContext::set_ResetForSubreportDataPrefetch(bool value)
0x1799bd  ldloc.0
0x1799be  ldloc.3
0x1799bf  ldarg.2
0x1799c0  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_Parameters()
0x1799c5  ldc.i4.0
0x1799c6  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportInstance Merge::Process(class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection parameters, bool mergeTran)
0x1799cb  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_ReportInstance(class Microsoft.ReportingServices.ReportProcessing.ReportInstance value)
0x1799d0  ldarg.s  4
0x1799d2  ldarg.3
0x1799d3  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState ProcessingContext::get_HasUserProfileState()
0x1799d8  stind.i4
0x1799d9  ldarg.3
0x1799da  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportDrillthroughInfo ProcessingContext::get_DrillthroughInfo()
0x1799df  stloc.s  4
0x1799e1  newobj   instance void PageMergeInteractive::.ctor()
0x1799e6  stloc.s  5
0x1799e8  ldarg.s  4
0x1799ea  ldarg.s  4
0x1799ec  ldind.i4
0x1799ed  ldloc.s  5
0x1799ef  ldarg.3
0x1799f0  callvirt instance class PageSectionContext ProcessingContext::get_PageSectionContext()
0x1799f5  callvirt instance class PageTextboxes PageSectionContext::get_PageTextboxes()
0x1799fa  ldloc.0
0x1799fb  ldarg.2
0x1799fc  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_ReportContext()
0x179a01  ldarg.2
0x179a02  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_ReportContext()
0x179a07  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ItemName()
0x179a0c  ldarg.2
0x179a0d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_Parameters()
0x179a12  ldarg.3
0x179a13  callvirt instance class ProcessingChunkManager ProcessingContext::get_ChunkManager()
0x179a18  ldarg.2
0x179a19  callvirt instance class CreateReportChunk Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_CreateReportChunkCallback()
0x179a1e  ldarg.2
0x179a1f  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IGetResource Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_GetResourceCallback()
0x179a24  ldarg.3
0x179a25  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ErrorContext ProcessingContext::get_ErrorContext()
0x179a2a  ldarg.3
0x179a2b  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState ProcessingContext::get_AllowUserProfileState()
0x179a30  ldarg.3
0x179a31  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportRuntimeSetup ProcessingContext::get_ReportRuntimeSetup()
0x179a36  ldarg.3
0x179a37  callvirt instance int32 ProcessingContext::get_UniqueNameCounter()
0x179a3c  ldarg.2
0x179a3d  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection Microsoft.ReportingServices.ReportProcessing.ProcessingContext::get_DataProtection()
0x179a42  ldloca.s 4
0x179a44  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState PageMergeInteractive::Process(class PageTextboxes pageTextboxes, class Microsoft.ReportingServices.ReportProcessing.ReportSnapshot reportSnapshot, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext reportContext, string reportName, class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection parameters, class ProcessingChunkManager pageSectionManager, class CreateReportChunk createChunkCallback, class Microsoft.ReportingServices.ReportProcessing.IGetResource getResourceCallback, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState allowUserProfileState, class Microsoft.ReportingServices.ReportProcessing.ReportRuntimeSetup reportRuntimeSetup, int32 uniqueNameCounter, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection, class Microsoft.ReportingServices.ReportProcessing.ReportDrillthroughInfo& drillthroughInfo)
0x179a49  or
0x179a4a  stind.i4
0x179a4b  ldloc.3
0x179a4c  ldarg.s  4
0x179a4e  ldind.i4
0x179a4f  callvirt instance void Merge::CleanupDataChunk(valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState userProfileState)
0x179a54  ldarg.3
0x179a55  ldloca.s 6
0x179a57  ldloca.s 7
0x179a59  callvirt instance void ProcessingContext::GetSenderAndReceiverInfo([out] class Microsoft.ReportingServices.ReportProcessing.SenderInformationHashtable& senderInfo, [out] class Microsoft.ReportingServices.ReportProcessing.ReceiverInformationHashtable& receiverInfo)
0x179a5e  ldloc.0
0x179a5f  ldloc.s  6
0x179a61  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_ShowHideSenderInfo(class Microsoft.ReportingServices.ReportProcessing.SenderInformationHashtable value)
0x179a66  ldloc.s  6
0x179a68  brtrue.s loc_179A72
0x179a6a  ldarg.3
0x179a6b  callvirt instance bool ProcessingContext::get_HasUserSortFilter()
0x179a70  brfalse.s loc_179A79
0x179a72  ldloc.0
0x179a73  ldc.i4.1
0x179a74  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_HasShowHide(bool value)
0x179a79  ldloc.0
0x179a7a  ldloc.s  7
0x179a7c  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_ShowHideReceiverInfo(class Microsoft.ReportingServices.ReportProcessing.ReceiverInformationHashtable value)
0x179a81  ldarg.3
0x179a82  callvirt instance class Microsoft.ReportingServices.ReportProcessing.QuickFindHashtable ProcessingContext::get_QuickFind()
0x179a87  brfalse.s loc_179AA5
0x179a89  ldarg.3
0x179a8a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.QuickFindHashtable ProcessingContext::get_QuickFind()
0x179a8f  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.HashtableInstanceInfo::get_Count()
0x179a94  ldc.i4.0
0x179a95  ble.s    loc_179AA5
0x179a97  ldloc.0
0x179a98  ldarg.3
0x179a99  callvirt instance class Microsoft.ReportingServices.ReportProcessing.QuickFindHashtable ProcessingContext::get_QuickFind()
0x179a9e  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_QuickFind(class Microsoft.ReportingServices.ReportProcessing.QuickFindHashtable value)
0x179aa3  br.s     loc_179AAC
0x179aa5  ldloc.0
0x179aa6  ldnull
0x179aa7  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_QuickFind(class Microsoft.ReportingServices.ReportProcessing.QuickFindHashtable value)
0x179aac  ldloc.s  4
0x179aae  brfalse.s loc_179AC4
0x179ab0  ldloc.s  4
0x179ab2  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ReportDrillthroughInfo::get_Count()
0x179ab7  ldc.i4.0
0x179ab8  ble.s    loc_179AC4
0x179aba  ldloc.0
0x179abb  ldloc.s  4
0x179abd  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_DrillthroughInfo(class Microsoft.ReportingServices.ReportProcessing.ReportDrillthroughInfo value)
0x179ac2  br.s     loc_179ACB
0x179ac4  ldloc.0
0x179ac5  ldnull
0x179ac6  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_DrillthroughInfo(class Microsoft.ReportingServices.ReportProcessing.ReportDrillthroughInfo value)
0x179acb  ldloc.0
0x179acc  ldarg.3
0x179acd  callvirt instance class NavigationInfo ProcessingContext::get_NavigationInfo()
0x179ad2  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::CreateNavigationActions(class NavigationInfo navigationInfo)
0x179ad7  ldarg.3
0x179ad8  callvirt instance bool ProcessingContext::get_HasImageStreams()
0x179add  brtrue.s loc_179AE7
0x179adf  ldarg.1
0x179ae0  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.Report::get_HasImageStreams()
0x179ae5  brfalse.s loc_179AEE
0x179ae7  ldloc.0
0x179ae8  ldc.i4.1
0x179ae9  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_HasImageStreams(bool value)
0x179aee  ldarg.3
0x179aef  callvirt instance class Microsoft.ReportingServices.ReportProcessing.SortFilterEventInfoHashtable ProcessingContext::get_NewSortFilterEventInfo()
0x179af4  brfalse.s loc_179B12
0x179af6  ldarg.3
0x179af7  callvirt instance class Microsoft.ReportingServices.ReportProcessing.SortFilterEventInfoHashtable ProcessingContext::get_NewSortFilterEventInfo()
0x179afc  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.HashtableInstanceInfo::get_Count()
0x179b01  ldc.i4.0
0x179b02  ble.s    loc_179B12
0x179b04  ldloc.0
0x179b05  ldarg.3
0x179b06  callvirt instance class Microsoft.ReportingServices.ReportProcessing.SortFilterEventInfoHashtable ProcessingContext::get_NewSortFilterEventInfo()
0x179b0b  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_SortFilterEventInfo(class Microsoft.ReportingServices.ReportProcessing.SortFilterEventInfoHashtable value)
0x179b10  br.s     loc_179B19
0x179b12  ldloc.0
0x179b13  ldnull
0x179b14  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_SortFilterEventInfo(class Microsoft.ReportingServices.ReportProcessing.SortFilterEventInfoHashtable value)
0x179b19  ldarg.3
0x179b1a  callvirt instance class ProcessingChunkManager ProcessingContext::get_ChunkManager()
0x179b1f  ldloc.0
0x179b20  callvirt instance void ProcessingChunkManager::PageSectionFlush(class Microsoft.ReportingServices.ReportProcessing.ReportSnapshot reportSnapshot)
0x179b25  ldarg.3
0x179b26  callvirt instance class ProcessingChunkManager ProcessingContext::get_ChunkManager()
0x179b2b  callvirt instance void SnapshotChunkManager::FinalFlush()
0x179b30  ldarg.1
0x179b31  ldarg.3
0x179b32  callvirt instance class ProcessingChunkManager ProcessingContext::get_ChunkManager()
0x179b37  callvirt instance int64 ProcessingChunkManager::get_TotalCount()
0x179b3c  ldc.i4.s 0x32
0x179b3e  conv.i8
0x179b3f  mul
0x179b40  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Report::set_MainChunkSize(int64 value)
0x179b45  ldloc.0
0x179b46  ldarg.3
0x179b47  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ErrorContext ProcessingContext::get_ErrorContext()
0x179b4c  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0x179b51  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportSnapshot::set_Warnings(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList value)
0x179b56  ldloc.0
0x179b57  stloc.s  8
0x179b59  leave    loc_179CF1
0x179b5e  ldloc.1
0x179b5f  brfalse.s loc_179B6C
0x179b61  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x179b66  ldloc.1
0x179b67  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x179b6c  ldarg.3
0x179b6d  callvirt instance class DataSourceInfoHashtable ProcessingContext::get_GlobalDataSourceInfo()
0x179b72  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x179b77  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x179b7c  stloc.s  9
0x179b7e  br       loc_179CA5
0x179b83  ldloc.s  9
0x179b85  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x179b8a  castclass DataSourceInfo
0x179b8f  stloc.s  0xA
0x179b91  ldloc.s  0xA
0x179b93  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x179b98  brfalse  loc_179C69
0x179b9d  ldloc.s  0xA
0x179b9f  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x179ba4  ldfld    bool TransactionInfo::RollbackRequired
0x179ba9  brfalse.s loc_179C0A
0x179bab  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x179bb0  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x179bb5  brfalse.s loc_179BD7
0x179bb7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x179bbc  ldc.i4.3
0x179bbd  ldstr    aDataSource0Rol// "Data source '{0}': Rolling back transac"...
0x179bc2  ldc.i4.1
0x179bc3  newarr   [mscorlib]System.Object
0x179bc8  dup
0x179bc9  ldc.i4.0
0x179bca  ldloc.s  0xA
0x179bcc  callvirt instance string DataSourceInfo::get_DataSourceName()
0x179bd1  stelem.ref
0x179bd2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x179bd7  nop
0x179bd8  ldloc.s  0xA
0x179bda  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x179bdf  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction TransactionInfo::get_Transaction()
0x179be4  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction::Rollback()
0x179be9  leave.s  loc_179C69
0x179beb  stloc.s  0xB
0x179bed  ldc.i4   0xA0
0x179bf2  ldloc.s  0xB
0x179bf4  ldc.i4.1
0x179bf5  newarr   [mscorlib]System.Object
  ... truncated ...
```
