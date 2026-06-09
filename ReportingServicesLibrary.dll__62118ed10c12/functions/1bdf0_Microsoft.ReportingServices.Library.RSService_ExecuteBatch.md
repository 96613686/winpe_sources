# Microsoft.ReportingServices.Library.RSService::ExecuteBatch

- ea: `0x1bdf0`
- end: `0x1c310`
- name: `Microsoft.ReportingServices.Library.RSService::ExecuteBatch`
- size: `1312`
- prototype: ``
- caller_count: `1`
- callee_count: `59`
- tags: `service_task, broker_com_uri`

## callers

- `0x3ebd0`

## callees

- `0xcda0`
- `0xcf00`
- `0x1a3e0`
- `0x1a400`
- `0x1a440`
- `0x1a6d0`
- `0x1a7b0`
- `0x1a7d0`
- `0x1a7f0`
- `0x1a810`
- `0x1a850`
- `0x1a890`
- `0x1a8d0`
- `0x1a910`
- `0x1a930`
- `0x1a950`
- `0x1a970`
- `0x1a9b0`
- `0x1aa30`
- `0x1aa70`
- `0x1aa90`
- `0x1aab0`
- `0x1aad0`
- `0x1aaf0`
- `0x1abd0`
- `0x1abf0`
- `0x1ac50`
- `0x1ac70`
- `0x1ac90`
- `0x1b130`
- `0x1b170`
- `0x1b190`
- `0x1b1d0`
- `0x1b1f0`
- `0x1bdf0`
- `0x1c380`
- `0x1ca70`
- `0x1cad0`
- `0x1caf0`
- `0x1cb30`
- `0x1cb90`
- `0x1cbb0`
- `0x1cbd0`
- `0x1cc30`
- `0x1cc50`
- `0x1ccd0`
- `0x1ccf0`
- `0x1cdb0`
- `0x1cdf0`
- `0x1ceb0`

## string_xrefs

- `0x1c29a`: `Unknown catalog command in batching`
- `0x1c2d7`: `Call to ExecuteBatch[{0}] completed`

## pseudocode

```c

```

## disassembly

```asm
0x1bdf0  ldarg.0
0x1bdf1  call     instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x1bdf6  ldarg.0
0x1bdf7  ldc.i4.1
0x1bdf8  stfld    bool Microsoft.ReportingServices.Library.RSService::m_useBatchConnectionManager
0x1bdfd  ldarg.0
0x1bdfe  call     instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.RSService::get_Tracer()
0x1be03  ldc.i4.4
0x1be04  ldstr    aCallToExecuteb// "Call to ExecuteBatch( {0} )"
0x1be09  ldc.i4.1
0x1be0a  newarr   [mscorlib]System.Object
0x1be0f  dup
0x1be10  ldc.i4.0
0x1be11  ldarg.1
0x1be12  box      [mscorlib]System.Guid
0x1be17  stelem.ref
0x1be18  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1be1d  ldarg.0
0x1be1e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1be23  pop
0x1be24  ldarg.0
0x1be25  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1be2a  ldarg.1
0x1be2b  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.IDBInterface::GetBatchRecords(valuetype [mscorlib]System.Guid batchId)
0x1be30  dup
0x1be31  brtrue.s loc_1BE46
0x1be33  ldarga.s 1
0x1be35  constrained. [mscorlib]System.Guid
0x1be3b  callvirt instance string [mscorlib]System.Object::ToString()
0x1be40  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.BatchNotFoundException::.ctor(string)
0x1be45  throw
0x1be46  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x1be4b  stloc.0
0x1be4c  br       loc_1C2A5
0x1be51  ldloc.0
0x1be52  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1be57  castclass Microsoft.ReportingServices.Library.CallParameters
0x1be5c  stloc.1
0x1be5d  ldtoken  Microsoft.ReportingServices.Library.CatalogCommand
0x1be62  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1be67  ldloc.1
0x1be68  ldfld    string Microsoft.ReportingServices.Library.CallParameters::Action
0x1be6d  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x1be72  unbox.any Microsoft.ReportingServices.Library.CatalogCommand
0x1be77  stloc.2
0x1be78  ldloc.2
0x1be79  switch   loc_1BF57, loc_1BF63, loc_1BF74, loc_1BF85, loc_1BF96, loc_1BFA7, loc_1BFC9, loc_1BFEB, loc_1BFFC, loc_1C00D, loc_1C01E, loc_1C02F, loc_1C040, loc_1C051, loc_1C062, loc_1C073, loc_1C084, loc_1C095, loc_1C0A6, loc_1C0B7, loc_1C0C8, loc_1C0D9, loc_1C0EA, loc_1C0FB, loc_1C10C, loc_1C11D, loc_1C12E, loc_1C13F, loc_1C150, loc_1C161, loc_1C172, loc_1C183, loc_1C194, loc_1C1A5, loc_1C1B6, loc_1C1C7, loc_1C1D8, loc_1C1E9, loc_1C1FA, loc_1C20B, loc_1C21C, loc_1C0C8, loc_1C0D9, loc_1C22A, loc_1C238, loc_1C270, loc_1C27E, loc_1C262, loc_1C246, loc_1C254, loc_1BFB8, loc_1BFDA, loc_1C28C
0x1bf52  br       loc_1C29A
0x1bf57  ldarg.0
0x1bf58  ldloc.1
0x1bf59  call     instance void Microsoft.ReportingServices.Library.RSService::BatchStart(class Microsoft.ReportingServices.Library.CallParameters parameters)
0x1bf5e  br       loc_1C2A5
0x1bf63  ldarg.0
0x1bf64  call     instance class Microsoft.ReportingServices.Library.DeleteItemAction Microsoft.ReportingServices.Library.RSService::get_DeleteItemAction()
0x1bf69  ldloc.1
0x1bf6a  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.DeleteItemActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bf6f  br       loc_1C2A5
0x1bf74  ldarg.0
0x1bf75  call     instance class Microsoft.ReportingServices.Library.MoveItemAction Microsoft.ReportingServices.Library.RSService::get_MoveItemAction()
0x1bf7a  ldloc.1
0x1bf7b  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.MoveItemActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bf80  br       loc_1C2A5
0x1bf85  ldarg.0
0x1bf86  call     instance class Microsoft.ReportingServices.Library.SetPropertiesAction Microsoft.ReportingServices.Library.RSService::get_SetPropertiesAction()
0x1bf8b  ldloc.1
0x1bf8c  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bf91  br       loc_1C2A5
0x1bf96  ldarg.0
0x1bf97  call     instance class Microsoft.ReportingServices.Library.CreateFolderAction Microsoft.ReportingServices.Library.RSService::get_CreateFolderAction()
0x1bf9c  ldloc.1
0x1bf9d  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateFolderActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bfa2  br       loc_1C2A5
0x1bfa7  ldarg.0
0x1bfa8  call     instance class Microsoft.ReportingServices.Library.CreateReportAction Microsoft.ReportingServices.Library.RSService::get_CreateReportAction()
0x1bfad  ldloc.1
0x1bfae  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateReportActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bfb3  br       loc_1C2A5
0x1bfb8  ldarg.0
0x1bfb9  call     instance class Microsoft.ReportingServices.Library.CreateRdlxReportAction Microsoft.ReportingServices.Library.RSService::get_CreateRdlxReportAction()
0x1bfbe  ldloc.1
0x1bfbf  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateReportActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bfc4  br       loc_1C2A5
0x1bfc9  ldarg.0
0x1bfca  call     instance class Microsoft.ReportingServices.Library.SetReportDefinitionAction Microsoft.ReportingServices.Library.RSService::get_SetReportDefinitionAction()
0x1bfcf  ldloc.1
0x1bfd0  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetReportDefinitionActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bfd5  br       loc_1C2A5
0x1bfda  ldarg.0
0x1bfdb  call     instance class Microsoft.ReportingServices.Library.SetRdlxReportDefinitionAction Microsoft.ReportingServices.Library.RSService::get_SetRdlxReportDefinitionAction()
0x1bfe0  ldloc.1
0x1bfe1  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetReportDefinitionActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bfe6  br       loc_1C2A5
0x1bfeb  ldarg.0
0x1bfec  call     instance class Microsoft.ReportingServices.Library.SetReportParametersAction Microsoft.ReportingServices.Library.RSService::get_SetReportParametersAction()
0x1bff1  ldloc.1
0x1bff2  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetReportParametersActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1bff7  br       loc_1C2A5
0x1bffc  ldarg.0
0x1bffd  call     instance class Microsoft.ReportingServices.Library.CreateLinkedReportAction Microsoft.ReportingServices.Library.RSService::get_CreateLinkedReportAction()
0x1c002  ldloc.1
0x1c003  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateLinkedReportActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c008  br       loc_1C2A5
0x1c00d  ldarg.0
0x1c00e  call     instance class Microsoft.ReportingServices.Library.SetReportLinkAction Microsoft.ReportingServices.Library.RSService::get_SetReportLinkAction()
0x1c013  ldloc.1
0x1c014  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetReportLinkActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c019  br       loc_1C2A5
0x1c01e  ldarg.0
0x1c01f  call     instance class Microsoft.ReportingServices.Library.CreateResourceAction Microsoft.ReportingServices.Library.RSService::get_CreateResourceAction()
0x1c024  ldloc.1
0x1c025  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateResourceActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c02a  br       loc_1C2A5
0x1c02f  ldarg.0
0x1c030  call     instance class Microsoft.ReportingServices.Library.SetResourceContentsAction Microsoft.ReportingServices.Library.RSService::get_SetResourceContentsAction()
0x1c035  ldloc.1
0x1c036  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetResourceContentsActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c03b  br       loc_1C2A5
0x1c040  ldarg.0
0x1c041  call     instance class Microsoft.ReportingServices.Library.CreateSnapshotAction Microsoft.ReportingServices.Library.RSService::get_CreateSnapshotAction()
0x1c046  ldloc.1
0x1c047  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateSnapshotActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c04c  br       loc_1C2A5
0x1c051  ldarg.0
0x1c052  call     instance class Microsoft.ReportingServices.Library.SetSnapshotLimitAction Microsoft.ReportingServices.Library.RSService::get_SetSnapshotLimitAction()
0x1c057  ldloc.1
0x1c058  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSnapshotLimitActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c05d  br       loc_1C2A5
0x1c062  ldarg.0
0x1c063  call     instance class Microsoft.ReportingServices.Library.DeleteSnapshotAction Microsoft.ReportingServices.Library.RSService::get_DeleteSnapshotAction()
0x1c068  ldloc.1
0x1c069  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.DeleteSnapshotActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c06e  br       loc_1C2A5
0x1c073  ldarg.0
0x1c074  call     instance class Microsoft.ReportingServices.Library.CreateScheduleAction Microsoft.ReportingServices.Library.RSService::get_CreateScheduleAction()
0x1c079  ldloc.1
0x1c07a  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateScheduleActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c07f  br       loc_1C2A5
0x1c084  ldarg.0
0x1c085  call     instance class Microsoft.ReportingServices.Library.DeleteScheduleAction Microsoft.ReportingServices.Library.RSService::get_DeleteScheduleAction()
0x1c08a  ldloc.1
0x1c08b  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.DeleteScheduleActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c090  br       loc_1C2A5
0x1c095  ldarg.0
0x1c096  call     instance class Microsoft.ReportingServices.Library.SetSchedulePropertiesAction Microsoft.ReportingServices.Library.RSService::get_SetSchedulePropertiesAction()
0x1c09b  ldloc.1
0x1c09c  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSchedulePropertiesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c0a1  br       loc_1C2A5
0x1c0a6  ldarg.0
0x1c0a7  call     instance class Microsoft.ReportingServices.Library.PauseScheduleAction Microsoft.ReportingServices.Library.RSService::get_PauseScheduleAction()
0x1c0ac  ldloc.1
0x1c0ad  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.PauseScheduleActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c0b2  br       loc_1C2A5
0x1c0b7  ldarg.0
0x1c0b8  call     instance class Microsoft.ReportingServices.Library.ResumeScheduleAction Microsoft.ReportingServices.Library.RSService::get_ResumeScheduleAction()
0x1c0bd  ldloc.1
0x1c0be  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.ResumeScheduleActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c0c3  br       loc_1C2A5
0x1c0c8  ldarg.0
0x1c0c9  call     instance class Microsoft.ReportingServices.Library.CreateSubscriptionAction Microsoft.ReportingServices.Library.RSService::get_CreateSubscriptionAction()
0x1c0ce  ldloc.1
0x1c0cf  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c0d4  br       loc_1C2A5
0x1c0d9  ldarg.0
0x1c0da  call     instance class Microsoft.ReportingServices.Library.SetSubscriptionPropertiesAction Microsoft.ReportingServices.Library.RSService::get_SetSubscriptionPropertiesAction()
0x1c0df  ldloc.1
0x1c0e0  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c0e5  br       loc_1C2A5
0x1c0ea  ldarg.0
0x1c0eb  call     instance class Microsoft.ReportingServices.Library.DisableSubscriptionAction Microsoft.ReportingServices.Library.RSService::get_DisableSubscriptionAction()
0x1c0f0  ldloc.1
0x1c0f1  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.DisableSubscriptionActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c0f6  br       loc_1C2A5
0x1c0fb  ldarg.0
0x1c0fc  call     instance class Microsoft.ReportingServices.Library.EnableSubscriptionAction Microsoft.ReportingServices.Library.RSService::get_EnableSubscriptionAction()
0x1c101  ldloc.1
0x1c102  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.EnableSubscriptionActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c107  br       loc_1C2A5
0x1c10c  ldarg.0
0x1c10d  call     instance class Microsoft.ReportingServices.Library.DeleteSubscriptionAction Microsoft.ReportingServices.Library.RSService::get_DeleteSubscriptionAction()
0x1c112  ldloc.1
0x1c113  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.DeleteSubscriptionActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c118  br       loc_1C2A5
0x1c11d  ldarg.0
0x1c11e  call     instance class Microsoft.ReportingServices.Library.SetExecutionOptionsAction Microsoft.ReportingServices.Library.RSService::get_SetExecutionOptionsAction()
0x1c123  ldloc.1
0x1c124  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c129  br       loc_1C2A5
0x1c12e  ldarg.0
0x1c12f  call     instance class Microsoft.ReportingServices.Library.SetCacheOptionsAction Microsoft.ReportingServices.Library.RSService::get_SetCacheOptionsAction()
0x1c134  ldloc.1
0x1c135  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c13a  br       loc_1C2A5
0x1c13f  ldarg.0
0x1c140  call     instance class Microsoft.ReportingServices.Library.UpdateExecutionSnapshotAction Microsoft.ReportingServices.Library.RSService::get_UpdateExecutionSnapshotAction()
0x1c145  ldloc.1
0x1c146  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateExecutionSnapshotActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c14b  br       loc_1C2A5
0x1c150  ldarg.0
0x1c151  call     instance class Microsoft.ReportingServices.Library.FlushCacheAction Microsoft.ReportingServices.Library.RSService::get_FlushCacheAction()
0x1c156  ldloc.1
0x1c157  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.FlushOptionsActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c15c  br       loc_1C2A5
0x1c161  ldarg.0
0x1c162  call     instance class Microsoft.ReportingServices.Library.SetReportHistoryOptionsAction Microsoft.ReportingServices.Library.RSService::get_SetReportHistoryOptionsAction()
0x1c167  ldloc.1
0x1c168  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.ReportHistoryOptionsActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c16d  br       loc_1C2A5
0x1c172  ldarg.0
0x1c173  call     instance class Microsoft.ReportingServices.Library.FireEventAction Microsoft.ReportingServices.Library.RSService::get_FireEventAction()
0x1c178  ldloc.1
0x1c179  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.FireEventActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c17e  br       loc_1C2A5
0x1c183  ldarg.0
0x1c184  call     instance class Microsoft.ReportingServices.Library.CreateRoleAction Microsoft.ReportingServices.Library.RSService::get_CreateRoleAction()
0x1c189  ldloc.1
0x1c18a  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateRoleActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c18f  br       loc_1C2A5
0x1c194  ldarg.0
0x1c195  call     instance class Microsoft.ReportingServices.Library.DeleteRoleAction Microsoft.ReportingServices.Library.RSService::get_DeleteRoleAction()
0x1c19a  ldloc.1
0x1c19b  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.DeleteRoleActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c1a0  br       loc_1C2A5
0x1c1a5  ldarg.0
0x1c1a6  call     instance class Microsoft.ReportingServices.Library.SetRolePropertiesAction Microsoft.ReportingServices.Library.RSService::get_SetRolePropertiesAction()
0x1c1ab  ldloc.1
0x1c1ac  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetRolePropertiesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c1b1  br       loc_1C2A5
0x1c1b6  ldarg.0
0x1c1b7  call     instance class Microsoft.ReportingServices.Library.SetPoliciesAction Microsoft.ReportingServices.Library.RSService::get_SetPoliciesAction()
0x1c1bc  ldloc.1
0x1c1bd  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetPoliciesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c1c2  br       loc_1C2A5
0x1c1c7  ldarg.0
0x1c1c8  call     instance class Microsoft.ReportingServices.Library.SetSystemPoliciesAction Microsoft.ReportingServices.Library.RSService::get_SetSystemPoliciesAction()
0x1c1cd  ldloc.1
0x1c1ce  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPoliciesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c1d3  br       loc_1C2A5
0x1c1d8  ldarg.0
0x1c1d9  call     instance class Microsoft.ReportingServices.Library.DeletePoliciesAction Microsoft.ReportingServices.Library.RSService::get_DeletePoliciesAction()
0x1c1de  ldloc.1
0x1c1df  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.DeletePoliciesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c1e4  br       loc_1C2A5
0x1c1e9  ldarg.0
0x1c1ea  call     instance class Microsoft.ReportingServices.Library.CreateDataSourceAction Microsoft.ReportingServices.Library.RSService::get_CreateDataSourceAction()
0x1c1ef  ldloc.1
0x1c1f0  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateDataSourceActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c1f5  br       loc_1C2A5
0x1c1fa  ldarg.0
0x1c1fb  call     instance class Microsoft.ReportingServices.Library.SetDataSourceContentsAction Microsoft.ReportingServices.Library.RSService::get_SetDataSourceContentsAction()
0x1c200  ldloc.1
0x1c201  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetDataSourceContentsActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c206  br       loc_1C2A5
0x1c20b  ldarg.0
0x1c20c  call     instance class Microsoft.ReportingServices.Library.ChangeDataSourceStateAction Microsoft.ReportingServices.Library.RSService::get_ChangeDataSourceStateAction()
0x1c211  ldloc.1
0x1c212  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.ChangeDataSourceStateActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c217  br       loc_1C2A5
0x1c21c  ldarg.0
0x1c21d  call     instance class Microsoft.ReportingServices.Library.SetItemDataSourcesAction Microsoft.ReportingServices.Library.RSService::get_SetItemDataSourcesAction()
0x1c222  ldloc.1
0x1c223  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetItemDataSourcesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c228  br.s     loc_1C2A5
0x1c22a  ldarg.0
0x1c22b  call     instance class Microsoft.ReportingServices.Library.CreateModelAction Microsoft.ReportingServices.Library.RSService::get_CreateModelAction()
0x1c230  ldloc.1
0x1c231  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.CreateModelActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c236  br.s     loc_1C2A5
0x1c238  ldarg.0
0x1c239  call     instance class Microsoft.ReportingServices.Library.SetModelDefinitionAction Microsoft.ReportingServices.Library.RSService::get_SetModelDefinitionAction()
0x1c23e  ldloc.1
0x1c23f  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetModelDefinitionActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c244  br.s     loc_1C2A5
0x1c246  ldarg.0
0x1c247  call     instance class Microsoft.ReportingServices.Library.GenerateModelAction Microsoft.ReportingServices.Library.RSService::get_GenerateModelAction()
0x1c24c  ldloc.1
0x1c24d  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.GenerateModelActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c252  br.s     loc_1C2A5
0x1c254  ldarg.0
0x1c255  call     instance class Microsoft.ReportingServices.Library.RegenerateModelAction Microsoft.ReportingServices.Library.RSService::get_RegenerateModelAction()
0x1c25a  ldloc.1
0x1c25b  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.RegenerateModelActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c260  br.s     loc_1C2A5
0x1c262  ldarg.0
0x1c263  call     instance class Microsoft.ReportingServices.Library.SetDrillthroughReportsAction Microsoft.ReportingServices.Library.RSService::get_SetDrillthroughReportsAction()
0x1c268  ldloc.1
0x1c269  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetDrillthroughReportsActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c26e  br.s     loc_1C2A5
0x1c270  ldarg.0
0x1c271  call     instance class Microsoft.ReportingServices.Library.SetModelItemPoliciesAction Microsoft.ReportingServices.Library.RSService::get_SetModelItemPoliciesAction()
0x1c276  ldloc.1
0x1c277  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetModelItemPoliciesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c27c  br.s     loc_1C2A5
0x1c27e  ldarg.0
0x1c27f  call     instance class Microsoft.ReportingServices.Library.RemoveAllModelItemPoliciesAction Microsoft.ReportingServices.Library.RSService::get_RemoveAllModelItemPoliciesAction()
0x1c284  ldloc.1
0x1c285  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.RemoveAllModelItemPoliciesActionParameters>::PerformActionInBatch(class Microsoft.ReportingServices.Library.CallParameters)
0x1c28a  br.s     loc_1C2A5
0x1c28c  ldarg.0
0x1c28d  call     instance class Microsoft.ReportingServices.Library.CreateKpiAction Microsoft.ReportingServices.Library.RSService::get_CreateKpiAction()
0x1c292  ldloc.1
  ... truncated ...
```
