# Microsoft.SharePoint.Library.SPRequest::UpdateWorkflowAssociation

- ea: `0xf490`
- end: `0xfa66`
- name: `Microsoft.SharePoint.Library.SPRequest::UpdateWorkflowAssociation`
- size: `1494`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x8afb90`

## callees

- `0x30b0`
- `0xf490`
- `0x4727e0`
- `0x472800`
- `0x4729d0`
- `0x472c90`
- `0x472d60`
- `0x7b4dd0`
- `0x7c78d0`
- `0x7c89b0`
- `0x957470`

## string_xrefs

- `0xf552`: `pwzTaskListTitle`
- `0xf658`: `pwzTaskListTitle`
- `0xf75f`: `pwzTaskListTitle`
- `0xf87d`: `pwzTaskListTitle`
- `0xf990`: `pwzTaskListTitle`
- `0xf564`: `configuration`
- `0xf66a`: `configuration`
- `0xf771`: `configuration`
- `0xf88f`: `configuration`
- `0xf9a2`: `configuration`
- `0xf49c`: `SPRequest.UpdateWorkflowAssociation`
- `0xf508`: `UpdateWorkflowAssociation`
- `0xf60e`: `UpdateWorkflowAssociation`
- `0xf715`: `UpdateWorkflowAssociation`
- `0xf833`: `UpdateWorkflowAssociation`
- `0xf946`: `UpdateWorkflowAssociation`

## pseudocode

```c

```

## disassembly

```asm
0xf490  ldc.i4   0x66366C37
0xf495  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0xf49a  ldc.i4.s 0x64
0xf49c  ldstr    aSprequestUpdat_2// "SPRequest.UpdateWorkflowAssociation"
0xf4a1  ldc.i4.1
0xf4a2  ldc.i4.2
0xf4a3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0xf4a8  stloc.s  5
0xf4aa  ldloc.s  5
0xf4ac  ldc.i4.0
0xf4ad  ldc.i4   0x96
0xf4b2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0xf4b7  stelem.ref
0xf4b8  ldloc.s  5
0xf4ba  ldc.i4.1
0xf4bb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0xf4c0  stelem.ref
0xf4c1  ldloc.s  5
0xf4c3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0xf4c8  stloc.s  6
0xf4ca  ldarg.0
0xf4cb  dup
0xf4cc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0xf4d1  ldc.i4.1
0xf4d2  add
0xf4d3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0xf4d8  ldarg.0
0xf4d9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0xf4de  ldarg.0
0xf4df  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0xf4e4  ldarg.1
0xf4e5  ldarg.2
0xf4e6  ldarg.3
0xf4e7  ldarg.s  4
0xf4e9  ldarg.s  5
0xf4eb  ldarg.s  6
0xf4ed  ldarg.s  7
0xf4ef  ldarg.s  8
0xf4f1  ldarg.s  9
0xf4f3  ldarg.s  0xA
0xf4f5  ldarg.s  0xB
0xf4f7  ldarg.s  0xC
0xf4f9  ldarg.s  0xD
0xf4fb  ldarg.s  0xE
0xf4fd  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::UpdateWorkflowAssociation(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid&, valuetype [mscorlib]System.Guid&, string, string, int32, int32, unsigned int64, string, int32)
0xf502  leave    loc_FA46
0xf507  stloc.0
0xf508  ldstr    aUpdateworkflow// "UpdateWorkflowAssociation"
0xf50d  ldarg.0
0xf50e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0xf513  ldarg.0
0xf514  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0xf519  ldc.i4.s 0xC
0xf51b  newarr   [mscorlib]System.String
0xf520  stloc.s  7
0xf522  ldloc.s  7
0xf524  ldc.i4.0
0xf525  ldstr    aBstrurl// "bstrUrl"
0xf52a  stelem.ref
0xf52b  ldloc.s  7
0xf52d  ldc.i4.1
0xf52e  ldstr    aAssociationid// "associationId"
0xf533  stelem.ref
0xf534  ldloc.s  7
0xf536  ldc.i4.2
0xf537  ldstr    aPwzname// "pwzName"
0xf53c  stelem.ref
0xf53d  ldloc.s  7
0xf53f  ldc.i4.3
0xf540  ldstr    aPwzdescription// "pwzDescription"
0xf545  stelem.ref
0xf546  ldloc.s  7
0xf548  ldc.i4.4
0xf549  ldstr    aPwzstatusfield// "pwzStatusFieldName"
0xf54e  stelem.ref
0xf54f  ldloc.s  7
0xf551  ldc.i4.5
0xf552  ldstr    aPwztasklisttit// "pwzTaskListTitle"
0xf557  stelem.ref
0xf558  ldloc.s  7
0xf55a  ldc.i4.6
0xf55b  ldstr    aPwzhistorylist// "pwzHistoryListTitle"
0xf560  stelem.ref
0xf561  ldloc.s  7
0xf563  ldc.i4.7
0xf564  ldstr    aConfiguration// "configuration"
0xf569  stelem.ref
0xf56a  ldloc.s  7
0xf56c  ldc.i4.8
0xf56d  ldstr    aAutocleanupday// "autoCleanupDays"
0xf572  stelem.ref
0xf573  ldloc.s  7
0xf575  ldc.i4.s 9
0xf577  ldstr    aIpermissionsma// "iPermissionsManual"
0xf57c  stelem.ref
0xf57d  ldloc.s  7
0xf57f  ldc.i4.s 0xA
0xf581  ldstr    aPwzinstantiati// "pwzInstantiationParams"
0xf586  stelem.ref
0xf587  ldloc.s  7
0xf589  ldc.i4.s 0xB
0xf58b  ldstr    aVersion_0// "version"
0xf590  stelem.ref
0xf591  ldloc.s  7
0xf593  ldc.i4.s 0xC
0xf595  newarr   [mscorlib]System.Object
0xf59a  stloc.s  8
0xf59c  ldloc.s  8
0xf59e  ldc.i4.0
0xf59f  ldarg.1
0xf5a0  stelem.ref
0xf5a1  ldloc.s  8
0xf5a3  ldc.i4.1
0xf5a4  ldarg.2
0xf5a5  box      [mscorlib]System.Guid
0xf5aa  stelem.ref
0xf5ab  ldloc.s  8
0xf5ad  ldc.i4.2
0xf5ae  ldarg.3
0xf5af  stelem.ref
0xf5b0  ldloc.s  8
0xf5b2  ldc.i4.3
0xf5b3  ldarg.s  4
0xf5b5  stelem.ref
0xf5b6  ldloc.s  8
0xf5b8  ldc.i4.4
0xf5b9  ldarg.s  5
0xf5bb  stelem.ref
0xf5bc  ldloc.s  8
0xf5be  ldc.i4.5
0xf5bf  ldarg.s  8
0xf5c1  stelem.ref
0xf5c2  ldloc.s  8
0xf5c4  ldc.i4.6
0xf5c5  ldarg.s  9
0xf5c7  stelem.ref
0xf5c8  ldloc.s  8
0xf5ca  ldc.i4.7
0xf5cb  ldarg.s  0xA
0xf5cd  box      [mscorlib]System.Int32
0xf5d2  stelem.ref
0xf5d3  ldloc.s  8
0xf5d5  ldc.i4.8
0xf5d6  ldarg.s  0xB
0xf5d8  box      [mscorlib]System.Int32
0xf5dd  stelem.ref
0xf5de  ldloc.s  8
0xf5e0  ldc.i4.s 9
0xf5e2  ldarg.s  0xC
0xf5e4  box      [mscorlib]System.UInt64
0xf5e9  stelem.ref
0xf5ea  ldloc.s  8
0xf5ec  ldc.i4.s 0xA
0xf5ee  ldarg.s  0xD
0xf5f0  stelem.ref
0xf5f1  ldloc.s  8
0xf5f3  ldc.i4.s 0xB
0xf5f5  ldarg.s  0xE
0xf5f7  box      [mscorlib]System.Int32
0xf5fc  stelem.ref
0xf5fd  ldloc.s  8
0xf5ff  ldloc.0
0xf600  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0xf605  ldloc.0
0xf606  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0xf60b  rethrow
0xf60d  stloc.1
0xf60e  ldstr    aUpdateworkflow// "UpdateWorkflowAssociation"
0xf613  ldarg.0
0xf614  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0xf619  ldarg.0
0xf61a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0xf61f  ldc.i4.s 0xC
0xf621  newarr   [mscorlib]System.String
0xf626  stloc.s  9
0xf628  ldloc.s  9
0xf62a  ldc.i4.0
0xf62b  ldstr    aBstrurl// "bstrUrl"
0xf630  stelem.ref
0xf631  ldloc.s  9
0xf633  ldc.i4.1
0xf634  ldstr    aAssociationid// "associationId"
0xf639  stelem.ref
0xf63a  ldloc.s  9
0xf63c  ldc.i4.2
0xf63d  ldstr    aPwzname// "pwzName"
0xf642  stelem.ref
0xf643  ldloc.s  9
0xf645  ldc.i4.3
0xf646  ldstr    aPwzdescription// "pwzDescription"
0xf64b  stelem.ref
0xf64c  ldloc.s  9
0xf64e  ldc.i4.4
0xf64f  ldstr    aPwzstatusfield// "pwzStatusFieldName"
0xf654  stelem.ref
0xf655  ldloc.s  9
0xf657  ldc.i4.5
0xf658  ldstr    aPwztasklisttit// "pwzTaskListTitle"
0xf65d  stelem.ref
0xf65e  ldloc.s  9
0xf660  ldc.i4.6
0xf661  ldstr    aPwzhistorylist// "pwzHistoryListTitle"
0xf666  stelem.ref
0xf667  ldloc.s  9
0xf669  ldc.i4.7
0xf66a  ldstr    aConfiguration// "configuration"
0xf66f  stelem.ref
0xf670  ldloc.s  9
0xf672  ldc.i4.8
0xf673  ldstr    aAutocleanupday// "autoCleanupDays"
0xf678  stelem.ref
0xf679  ldloc.s  9
0xf67b  ldc.i4.s 9
0xf67d  ldstr    aIpermissionsma// "iPermissionsManual"
0xf682  stelem.ref
0xf683  ldloc.s  9
0xf685  ldc.i4.s 0xA
0xf687  ldstr    aPwzinstantiati// "pwzInstantiationParams"
0xf68c  stelem.ref
0xf68d  ldloc.s  9
0xf68f  ldc.i4.s 0xB
0xf691  ldstr    aVersion_0// "version"
0xf696  stelem.ref
0xf697  ldloc.s  9
0xf699  ldc.i4.s 0xC
0xf69b  newarr   [mscorlib]System.Object
0xf6a0  stloc.s  0xA
0xf6a2  ldloc.s  0xA
0xf6a4  ldc.i4.0
0xf6a5  ldarg.1
0xf6a6  stelem.ref
0xf6a7  ldloc.s  0xA
0xf6a9  ldc.i4.1
0xf6aa  ldarg.2
0xf6ab  box      [mscorlib]System.Guid
0xf6b0  stelem.ref
0xf6b1  ldloc.s  0xA
0xf6b3  ldc.i4.2
0xf6b4  ldarg.3
0xf6b5  stelem.ref
0xf6b6  ldloc.s  0xA
0xf6b8  ldc.i4.3
0xf6b9  ldarg.s  4
0xf6bb  stelem.ref
0xf6bc  ldloc.s  0xA
0xf6be  ldc.i4.4
0xf6bf  ldarg.s  5
0xf6c1  stelem.ref
0xf6c2  ldloc.s  0xA
0xf6c4  ldc.i4.5
0xf6c5  ldarg.s  8
0xf6c7  stelem.ref
0xf6c8  ldloc.s  0xA
0xf6ca  ldc.i4.6
0xf6cb  ldarg.s  9
0xf6cd  stelem.ref
0xf6ce  ldloc.s  0xA
0xf6d0  ldc.i4.7
0xf6d1  ldarg.s  0xA
0xf6d3  box      [mscorlib]System.Int32
0xf6d8  stelem.ref
0xf6d9  ldloc.s  0xA
0xf6db  ldc.i4.8
0xf6dc  ldarg.s  0xB
0xf6de  box      [mscorlib]System.Int32
0xf6e3  stelem.ref
0xf6e4  ldloc.s  0xA
0xf6e6  ldc.i4.s 9
0xf6e8  ldarg.s  0xC
0xf6ea  box      [mscorlib]System.UInt64
0xf6ef  stelem.ref
0xf6f0  ldloc.s  0xA
0xf6f2  ldc.i4.s 0xA
0xf6f4  ldarg.s  0xD
0xf6f6  stelem.ref
0xf6f7  ldloc.s  0xA
0xf6f9  ldc.i4.s 0xB
0xf6fb  ldarg.s  0xE
0xf6fd  box      [mscorlib]System.Int32
0xf702  stelem.ref
0xf703  ldloc.s  0xA
0xf705  ldloc.1
0xf706  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0xf70b  ldloc.1
0xf70c  ldc.i4.0
0xf70d  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0xf712  rethrow
0xf714  stloc.2
0xf715  ldstr    aUpdateworkflow// "UpdateWorkflowAssociation"
0xf71a  ldarg.0
0xf71b  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0xf720  ldarg.0
0xf721  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0xf726  ldc.i4.s 0xC
0xf728  newarr   [mscorlib]System.String
0xf72d  stloc.s  0xB
0xf72f  ldloc.s  0xB
0xf731  ldc.i4.0
0xf732  ldstr    aBstrurl// "bstrUrl"
0xf737  stelem.ref
  ... truncated ...
```
