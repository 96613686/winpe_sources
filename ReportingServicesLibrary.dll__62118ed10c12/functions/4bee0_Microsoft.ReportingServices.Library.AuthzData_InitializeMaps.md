# Microsoft.ReportingServices.Library.AuthzData::InitializeMaps

- ea: `0x4bee0`
- end: `0x4ca30`
- name: `Microsoft.ReportingServices.Library.AuthzData::InitializeMaps`
- size: `2896`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x4bdb0`

## callees

- `0x8adc0`
- `0x8adf0`
- `0x8ae10`
- `0x8aff0`
- `0x8b020`
- `0x8b050`

## string_xrefs

- `0x4bef8`: `ConfigureAccessName`
- `0x4befd`: `ConfigureAccessDescription`
- `0x4bf14`: `CreateLinkedReportsName`
- `0x4bf19`: `CreateLinkedReportsDescription`
- `0x4c0c8`: `CommentName`
- `0x4c0cd`: `CommentDescription`
- `0x4c0e6`: `ManageCommentsName`
- `0x4c0eb`: `ManageCommentsDescription`
- `0x4c12a`: `ManageSystemSecurityName`
- `0x4c12f`: `ManageSystemSecurityDescription`
- `0x4c146`: `ViewSystemPropertiesName`
- `0x4c14b`: `ViewSystemPropertiesDescription`
- `0x4c162`: `ManageSystemPropertiesName`
- `0x4c167`: `ManageSystemPropertiesDescription`

## pseudocode

```c

```

## disassembly

```asm
0x4bee0  ldc.i4.s 0x12
0x4bee2  newarr   CatalogItemTask
0x4bee7  stsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4beec  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bef1  ldc.i4.0
0x4bef2  ldc.i4.0
0x4bef3  ldstr    aE96a7928F3a540// "E96A7928-F3A5-409d-A6AA-0808172B28CB"
0x4bef8  ldstr    aConfigureacces// "ConfigureAccessName"
0x4befd  ldstr    aConfigureacces_0// "ConfigureAccessDescription"
0x4bf02  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bf07  stelem.ref
0x4bf08  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bf0d  ldc.i4.1
0x4bf0e  ldc.i4.1
0x4bf0f  ldstr    a3246fdf716fb48// "3246FDF7-16FB-4802-ABFA-76D4F4A8AD62"
0x4bf14  ldstr    aCreatelinkedre_0// "CreateLinkedReportsName"
0x4bf19  ldstr    aCreatelinkedre_1// "CreateLinkedReportsDescription"
0x4bf1e  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bf23  stelem.ref
0x4bf24  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bf29  ldc.i4.2
0x4bf2a  ldc.i4.2
0x4bf2b  ldstr    aE2723f22E29c49// "E2723F22-E29C-496b-B981-1D775F45FC09"
0x4bf30  ldstr    aViewreportsnam// "ViewReportsName"
0x4bf35  ldstr    aViewreportsdes// "ViewReportsDescription"
0x4bf3a  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bf3f  stelem.ref
0x4bf40  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bf45  ldc.i4.3
0x4bf46  ldc.i4.3
0x4bf47  ldstr    a88552a2499ba46// "88552A24-99BA-46ab-90CD-EF66FD3E444D"
0x4bf4c  ldstr    aManagereportsn// "ManageReportsName"
0x4bf51  ldstr    aManagereportsd// "ManageReportsDescription"
0x4bf56  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bf5b  stelem.ref
0x4bf5c  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bf61  ldc.i4.4
0x4bf62  ldc.i4.4
0x4bf63  ldstr    a993c580b3fbf44// "993C580B-3FBF-444b-B85E-A8DA50ADF40F"
0x4bf68  ldstr    aViewresourcesn// "ViewResourcesName"
0x4bf6d  ldstr    aViewresourcesd// "ViewResourcesDescription"
0x4bf72  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bf77  stelem.ref
0x4bf78  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bf7d  ldc.i4.5
0x4bf7e  ldc.i4.5
0x4bf7f  ldstr    a1d574e69B01d42// "1D574E69-B01D-4278-A25A-DEE6B3790F81"
0x4bf84  ldstr    aManageresource// "ManageResourcesName"
0x4bf89  ldstr    aManageresource_0// "ManageResourcesDescription"
0x4bf8e  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bf93  stelem.ref
0x4bf94  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bf99  ldc.i4.6
0x4bf9a  ldc.i4.6
0x4bf9b  ldstr    a2fbf7ae50db646// "2FBF7AE5-0DB6-46f2-B9BB-480794FBC97E"
0x4bfa0  ldstr    aViewfoldersnam// "ViewFoldersName"
0x4bfa5  ldstr    aViewfoldersdes// "ViewFoldersDescription"
0x4bfaa  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bfaf  stelem.ref
0x4bfb0  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bfb5  ldc.i4.7
0x4bfb6  ldc.i4.7
0x4bfb7  ldstr    a683665abEe4b40// "683665AB-EE4B-4026-99AE-68A9899F8B6E"
0x4bfbc  ldstr    aManagefoldersn// "ManageFoldersName"
0x4bfc1  ldstr    aManagefoldersd// "ManageFoldersDescription"
0x4bfc6  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bfcb  stelem.ref
0x4bfcc  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bfd1  ldc.i4.8
0x4bfd2  ldc.i4.8
0x4bfd3  ldstr    a75d856b82fc141// "75D856B8-2FC1-41c9-8DFA-FE0FF6153C20"
0x4bfd8  ldstr    aManagereporthi// "ManageReportHistoryName"
0x4bfdd  ldstr    aManagereporthi_0// "ManageReportHistoryDescription"
0x4bfe2  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4bfe7  stelem.ref
0x4bfe8  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4bfed  ldc.i4.s 9
0x4bfef  ldc.i4.s 9
0x4bff1  ldstr    aF95f31d0834a4c// "F95F31D0-834A-4c0e-B290-E3E4477908CA"
0x4bff6  ldstr    aSubscribename// "SubscribeName"
0x4bffb  ldstr    aSubscribedescr// "SubscribeDescription"
0x4c000  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c005  stelem.ref
0x4c006  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4c00b  ldc.i4.s 0xA
0x4c00d  ldc.i4.s 0xA
0x4c00f  ldstr    a7813c99b3f844d// "7813C99B-3F84-4d02-930F-72FA3B86024A"
0x4c014  ldstr    aManageanysubsc// "ManageAnySubscriptionName"
0x4c019  ldstr    aManageanysubsc_0// "ManageAnySubscriptionDescription"
0x4c01e  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c023  stelem.ref
0x4c024  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4c029  ldc.i4.s 0xB
0x4c02b  ldc.i4.s 0xB
0x4c02d  ldstr    aB96d28bb23d04a// "B96D28BB-23D0-4a32-B57A-7C12EBDD0704"
0x4c032  ldstr    aViewdatasource// "ViewDatasourceName"
0x4c037  ldstr    aViewdatasource_0// "ViewDatasourceDescription"
0x4c03c  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c041  stelem.ref
0x4c042  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4c047  ldc.i4.s 0xC
0x4c049  ldc.i4.s 0xC
0x4c04b  ldstr    aAd4523ad09b646// "AD4523AD-09B6-46ab-A7F0-AD1F52449FE1"
0x4c050  ldstr    aManagedatasour// "ManageDatasourceName"
0x4c055  ldstr    aManagedatasour_0// "ManageDatasourceDescription"
0x4c05a  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c05f  stelem.ref
0x4c060  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4c065  ldc.i4.s 0xD
0x4c067  ldc.i4.s 0xD
0x4c069  ldstr    aA1bdca29F89141// "A1BDCA29-F891-418f-BEAA-43E937F800C4"
0x4c06e  ldstr    aViewmodelsname// "ViewModelsName"
0x4c073  ldstr    aViewmodelsdesc// "ViewModelsDescription"
0x4c078  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c07d  stelem.ref
0x4c07e  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4c083  ldc.i4.s 0xE
0x4c085  ldc.i4.s 0xE
0x4c087  ldstr    aF59546b749a141// "F59546B7-49A1-41de-8E9A-34137F3D677F"
0x4c08c  ldstr    aManagemodelsna// "ManageModelsName"
0x4c091  ldstr    aManagemodelsde// "ManageModelsDescription"
0x4c096  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c09b  stelem.ref
0x4c09c  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4c0a1  ldc.i4.s 0xF
0x4c0a3  ldc.i4.s 0xF
0x4c0a5  ldstr    a4bf862b510d047// "4BF862B5-10D0-4793-B075-802F7775561E"
0x4c0aa  ldstr    aConsumereports// "ConsumeReportsName"
0x4c0af  ldstr    aConsumereports_0// "ConsumeReportsDescription"
0x4c0b4  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c0b9  stelem.ref
0x4c0ba  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4c0bf  ldc.i4.s 0x10
0x4c0c1  ldc.i4.s 0x10
0x4c0c3  ldstr    a938488dbE74243// "938488DB-E742-4362-9837-499B168D8C79"
0x4c0c8  ldstr    aCommentname// "CommentName"
0x4c0cd  ldstr    aCommentdescrip// "CommentDescription"
0x4c0d2  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c0d7  stelem.ref
0x4c0d8  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4c0dd  ldc.i4.s 0x11
0x4c0df  ldc.i4.s 0x11
0x4c0e1  ldstr    a42ad2650A3a947// "42AD2650-A3A9-478F-B6DF-51456A08461E"
0x4c0e6  ldstr    aManagecomments// "ManageCommentsName"
0x4c0eb  ldstr    aManagecomments_0// "ManageCommentsDescription"
0x4c0f0  newobj   instance void CatalogItemTask::.ctor(valuetype CatalogItemTaskEnum task, string id, string name, string description)
0x4c0f5  stelem.ref
0x4c0f6  ldc.i4.s 9
0x4c0f8  newarr   CatalogTask
0x4c0fd  stsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c102  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c107  ldc.i4.0
0x4c108  ldc.i4.0
0x4c109  ldstr    aA7e17983Ffc542// "A7E17983-FFC5-4252-9EBC-DF5C495A4CFA"
0x4c10e  ldstr    aManagerolesnam// "ManageRolesName"
0x4c113  ldstr    aManagerolesdes// "ManageRolesDescription"
0x4c118  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c11d  stelem.ref
0x4c11e  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c123  ldc.i4.1
0x4c124  ldc.i4.1
0x4c125  ldstr    a075be56b589c47// "075BE56B-589C-47ed-B072-5B5EDCF80C66"
0x4c12a  ldstr    aManagesystemse// "ManageSystemSecurityName"
0x4c12f  ldstr    aManagesystemse_0// "ManageSystemSecurityDescription"
0x4c134  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c139  stelem.ref
0x4c13a  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c13f  ldc.i4.2
0x4c140  ldc.i4.2
0x4c141  ldstr    aD07a969d0b114a// "D07A969D-0B11-4a4a-8685-7E0E6DEEBA36"
0x4c146  ldstr    aViewsystemprop// "ViewSystemPropertiesName"
0x4c14b  ldstr    aViewsystemprop_0// "ViewSystemPropertiesDescription"
0x4c150  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c155  stelem.ref
0x4c156  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c15b  ldc.i4.3
0x4c15c  ldc.i4.3
0x4c15d  ldstr    aDed0947bE39c4a// "DED0947B-E39C-4a03-A512-10AF2933772B"
0x4c162  ldstr    aManagesystempr// "ManageSystemPropertiesName"
0x4c167  ldstr    aManagesystempr_0// "ManageSystemPropertiesDescription"
0x4c16c  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c171  stelem.ref
0x4c172  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c177  ldc.i4.4
0x4c178  ldc.i4.4
0x4c179  ldstr    a20278b55A58249// "20278B55-A582-4926-8EB6-5C0D27CED8F9"
0x4c17e  ldstr    aViewsharedsche// "ViewSharedSchedulesName"
0x4c183  ldstr    aViewsharedsche_0// "ViewSharedSchedulesDescription"
0x4c188  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c18d  stelem.ref
0x4c18e  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c193  ldc.i4.5
0x4c194  ldc.i4.5
0x4c195  ldstr    a7663b0350c9948// "7663B035-0C99-488d-942B-7B36345178EB"
0x4c19a  ldstr    aManagesharedsc// "ManageSharedSchedulesName"
0x4c19f  ldstr    aManagesharedsc_0// "ManageSharedSchedulesDescription"
0x4c1a4  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c1a9  stelem.ref
0x4c1aa  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c1af  ldc.i4.6
0x4c1b0  ldc.i4.6
0x4c1b1  ldstr    a79d94b4357b045// "79D94B43-57B0-45fd-8EB3-A8654C347413"
0x4c1b6  ldstr    aGenerateevents// "GenerateEventsName"
0x4c1bb  ldstr    aGenerateevents_0// "GenerateEventsDescription"
0x4c1c0  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c1c5  stelem.ref
0x4c1c6  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c1cb  ldc.i4.7
0x4c1cc  ldc.i4.7
0x4c1cd  ldstr    aEc6ee51b0d9647// "EC6EE51B-0D96-478b-8477-826AA7637B68"
0x4c1d2  ldstr    aManagejobsname// "ManageJobsName"
0x4c1d7  ldstr    aManagejobsdesc// "ManageJobsDescription"
0x4c1dc  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c1e1  stelem.ref
0x4c1e2  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4c1e7  ldc.i4.8
0x4c1e8  ldc.i4.8
0x4c1e9  ldstr    aB83261780d1a40// "B8326178-0D1A-4054-B591-1CE98F492FCF"
0x4c1ee  ldstr    aExecutereportd// "ExecuteReportDefinitionsName"
0x4c1f3  ldstr    aExecutereportd_0// "ExecuteReportDefinitionsDescription"
0x4c1f8  newobj   instance void CatalogTask::.ctor(valuetype CatalogTaskEnum task, string id, string name, string description)
0x4c1fd  stelem.ref
0x4c1fe  ldc.i4.1
0x4c1ff  newarr   ModelItemTask
0x4c204  stsfld   class ModelItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_ModelItemTasks
0x4c209  ldsfld   class ModelItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_ModelItemTasks
0x4c20e  ldc.i4.0
0x4c20f  ldc.i4.0
0x4c210  ldstr    a69383e55A81041// "69383E55-A810-41f4-8A89-69A0D5976F49"
0x4c215  ldstr    aViewmodelitems// "ViewModelItemsName"
0x4c21a  ldstr    aViewmodelitems_0// "ViewModelItemsDescription"
0x4c21f  newobj   instance void ModelItemTask::.ctor(valuetype ModelItemTaskEnum task, string id, string name, string description)
0x4c224  stelem.ref
0x4c225  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x4c22a  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTaskMap
0x4c22f  ldc.i4.2
0x4c230  newarr   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperation
0x4c235  dup
0x4c236  ldc.i4.0
0x4c237  ldc.i4.6
0x4c238  stelem.i4
0x4c239  dup
0x4c23a  ldc.i4.1
0x4c23b  ldc.i4.7
0x4c23c  stelem.i4
0x4c23d  stloc.0
0x4c23e  ldc.i4.2
0x4c23f  newarr   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation
0x4c244  dup
0x4c245  ldc.i4.0
0x4c246  ldc.i4.s 0xC
0x4c248  stelem.i4
0x4c249  dup
0x4c24a  ldc.i4.1
0x4c24b  ldc.i4.s 0xD
0x4c24d  stelem.i4
0x4c24e  stloc.1
0x4c24f  ldc.i4.2
0x4c250  newarr   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ResourceOperation
0x4c255  dup
0x4c256  ldc.i4.0
0x4c257  ldc.i4.5
0x4c258  stelem.i4
0x4c259  dup
0x4c25a  ldc.i4.1
0x4c25b  ldc.i4.6
0x4c25c  stelem.i4
0x4c25d  stloc.2
0x4c25e  ldc.i4.2
0x4c25f  newarr   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.DatasourceOperation
0x4c264  dup
0x4c265  ldc.i4.0
0x4c266  ldc.i4.5
0x4c267  stelem.i4
0x4c268  dup
0x4c269  ldc.i4.1
0x4c26a  ldc.i4.6
0x4c26b  stelem.i4
0x4c26c  stloc.3
0x4c26d  ldc.i4.2
0x4c26e  newarr   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelOperation
0x4c273  dup
0x4c274  ldc.i4.0
0x4c275  ldc.i4.7
0x4c276  stelem.i4
0x4c277  dup
0x4c278  ldc.i4.1
0x4c279  ldc.i4.8
0x4c27a  stelem.i4
0x4c27b  stloc.s  4
0x4c27d  ldc.i4.0
0x4c27e  newobj   instance void TaskOperationMap::.ctor(valuetype CatalogItemTaskEnum task)
0x4c283  stloc.s  5
0x4c285  ldloc.s  5
0x4c287  ldloc.0
0x4c288  stfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperation[] TaskOperationMap::m_FldOper
0x4c28d  ldloc.s  5
0x4c28f  ldloc.1
0x4c290  stfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation[] TaskOperationMap::m_RptOper
0x4c295  ldloc.s  5
  ... truncated ...
```
