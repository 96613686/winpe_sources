# Microsoft.SharePoint.Library.SPRequest::AddOrUpdateItem

- ea: `0x542d0`
- end: `0x54c2c`
- name: `Microsoft.SharePoint.Library.SPRequest::AddOrUpdateItem`
- size: `2396`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x541970`

## callees

- `0x30b0`
- `0x542d0`
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

- `0x542dc`: `SPRequest.AddOrUpdateItem`
- `0x5435e`: `AddOrUpdateItem`
- `0x54514`: `AddOrUpdateItem`
- `0x546cb`: `AddOrUpdateItem`
- `0x54899`: `AddOrUpdateItem`
- `0x54a5c`: `AddOrUpdateItem`
- `0x54396`: `bSystemUpdate`
- `0x5454c`: `bSystemUpdate`
- `0x54703`: `bSystemUpdate`
- `0x548d1`: `bSystemUpdate`
- `0x54a94`: `bSystemUpdate`
- `0x543b1`: `bUpdateNoVersion`
- `0x54567`: `bUpdateNoVersion`
- `0x5471e`: `bUpdateNoVersion`
- `0x548ec`: `bUpdateNoVersion`
- `0x54aaf`: `bUpdateNoVersion`
- `0x543f5`: `bUnRestrictedUpdateInProgress`
- `0x545ab`: `bUnRestrictedUpdateInProgress`
- `0x54762`: `bUnRestrictedUpdateInProgress`
- `0x54930`: `bUnRestrictedUpdateInProgress`
- `0x54af3`: `bUnRestrictedUpdateInProgress`

## pseudocode

```c

```

## disassembly

```asm
0x542d0  ldc.i4   0x66366C37
0x542d5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x542da  ldc.i4.s 0x64
0x542dc  ldstr    aSprequestAddor_0// "SPRequest.AddOrUpdateItem"
0x542e1  ldc.i4.1
0x542e2  ldc.i4.2
0x542e3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x542e8  stloc.s  5
0x542ea  ldloc.s  5
0x542ec  ldc.i4.0
0x542ed  ldc.i4   0x96
0x542f2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x542f7  stelem.ref
0x542f8  ldloc.s  5
0x542fa  ldc.i4.1
0x542fb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x54300  stelem.ref
0x54301  ldloc.s  5
0x54303  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x54308  stloc.s  6
0x5430a  ldarg.0
0x5430b  dup
0x5430c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x54311  ldc.i4.1
0x54312  add
0x54313  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x54318  ldarg.0
0x54319  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x5431e  ldarg.0
0x5431f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x54324  ldarg.1
0x54325  ldarg.2
0x54326  ldarg.3
0x54327  ldarg.s  4
0x54329  ldarg.s  5
0x5432b  ldarg.s  6
0x5432d  ldarg.s  7
0x5432f  ldarg.s  8
0x54331  ldarg.s  9
0x54333  ldarg.s  0xA
0x54335  ldarg.s  0xB
0x54337  ldarg.s  0xC
0x54339  ldarg.s  0xD
0x5433b  ldarg.s  0xE
0x5433d  ldarg.s  0xF
0x5433f  ldarg.s  0x10
0x54341  ldarg.s  0x11
0x54343  ldarg.s  0x12
0x54345  ldarg.s  0x13
0x54347  ldarg.s  0x14
0x54349  ldarg.s  0x15
0x5434b  ldarg.s  0x16
0x5434d  ldarg.s  0x17
0x5434f  ldarg.s  0x18
0x54351  ldarg.s  0x19
0x54353  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::AddOrUpdateItem(string, string, bool, bool, bool, bool, bool, bool, int32&, string&, valuetype [mscorlib]System.Guid, bool, string, object&, object&, object&, bool, bool, bool, bool, bool, string, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISP2DSafeArrayWriter, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISP2DSafeArrayWriter, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISP2DSafeArrayWriter)
0x54358  leave    loc_54C0C
0x5435d  stloc.0
0x5435e  ldstr    aAddorupdateite// "AddOrUpdateItem"
0x54363  ldarg.0
0x54364  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x54369  ldarg.0
0x5436a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x5436f  ldc.i4.s 0x14
0x54371  newarr   [mscorlib]System.String
0x54376  stloc.s  7
0x54378  ldloc.s  7
0x5437a  ldc.i4.0
0x5437b  ldstr    aBstrurl// "bstrUrl"
0x54380  stelem.ref
0x54381  ldloc.s  7
0x54383  ldc.i4.1
0x54384  ldstr    aBstrlistname// "bstrListName"
0x54389  stelem.ref
0x5438a  ldloc.s  7
0x5438c  ldc.i4.2
0x5438d  ldstr    aBadd// "bAdd"
0x54392  stelem.ref
0x54393  ldloc.s  7
0x54395  ldc.i4.3
0x54396  ldstr    aBsystemupdate// "bSystemUpdate"
0x5439b  stelem.ref
0x5439c  ldloc.s  7
0x5439e  ldc.i4.4
0x5439f  ldstr    aBpreserveitemv// "bPreserveItemVersion"
0x543a4  stelem.ref
0x543a5  ldloc.s  7
0x543a7  ldc.i4.5
0x543a8  ldstr    aBpreserveitemu// "bPreserveItemUIVersion"
0x543ad  stelem.ref
0x543ae  ldloc.s  7
0x543b0  ldc.i4.6
0x543b1  ldstr    aBupdatenoversi// "bUpdateNoVersion"
0x543b6  stelem.ref
0x543b7  ldloc.s  7
0x543b9  ldc.i4.7
0x543ba  ldstr    aBnodemote// "bNoDemote"
0x543bf  stelem.ref
0x543c0  ldloc.s  7
0x543c2  ldc.i4.8
0x543c3  ldstr    aPbstrnewdocid// "pbstrNewDocId"
0x543c8  stelem.ref
0x543c9  ldloc.s  7
0x543cb  ldc.i4.s 9
0x543cd  ldstr    aBhasnewdocid// "bHasNewDocId"
0x543d2  stelem.ref
0x543d3  ldloc.s  7
0x543d5  ldc.i4.s 0xA
0x543d7  ldstr    aBstrversion// "bstrVersion"
0x543dc  stelem.ref
0x543dd  ldloc.s  7
0x543df  ldc.i4.s 0xB
0x543e1  ldstr    aBcheckout// "bCheckOut"
0x543e6  stelem.ref
0x543e7  ldloc.s  7
0x543e9  ldc.i4.s 0xC
0x543eb  ldstr    aBcheckin// "bCheckin"
0x543f0  stelem.ref
0x543f1  ldloc.s  7
0x543f3  ldc.i4.s 0xD
0x543f5  ldstr    aBunrestrictedu// "bUnRestrictedUpdateInProgress"
0x543fa  stelem.ref
0x543fb  ldloc.s  7
0x543fd  ldc.i4.s 0xE
0x543ff  ldstr    aBmigration// "bMigration"
0x54404  stelem.ref
0x54405  ldloc.s  7
0x54407  ldc.i4.s 0xF
0x54409  ldstr    aBpublish// "bPublish"
0x5440e  stelem.ref
0x5440f  ldloc.s  7
0x54411  ldc.i4.s 0x10
0x54413  ldstr    aBstrfilename// "bstrFileName"
0x54418  stelem.ref
0x54419  ldloc.s  7
0x5441b  ldc.i4.s 0x11
0x5441d  ldstr    aPlistdatavalid// "pListDataValidationCallback"
0x54422  stelem.ref
0x54423  ldloc.s  7
0x54425  ldc.i4.s 0x12
0x54427  ldstr    aPrestrictinser// "pRestrictInsertCallback"
0x5442c  stelem.ref
0x5442d  ldloc.s  7
0x5442f  ldc.i4.s 0x13
0x54431  ldstr    aPuniquefieldca// "pUniqueFieldCallback"
0x54436  stelem.ref
0x54437  ldloc.s  7
0x54439  ldc.i4.s 0x14
0x5443b  newarr   [mscorlib]System.Object
0x54440  stloc.s  8
0x54442  ldloc.s  8
0x54444  ldc.i4.0
0x54445  ldarg.1
0x54446  stelem.ref
0x54447  ldloc.s  8
0x54449  ldc.i4.1
0x5444a  ldarg.2
0x5444b  stelem.ref
0x5444c  ldloc.s  8
0x5444e  ldc.i4.2
0x5444f  ldarg.3
0x54450  box      [mscorlib]System.Boolean
0x54455  stelem.ref
0x54456  ldloc.s  8
0x54458  ldc.i4.3
0x54459  ldarg.s  4
0x5445b  box      [mscorlib]System.Boolean
0x54460  stelem.ref
0x54461  ldloc.s  8
0x54463  ldc.i4.4
0x54464  ldarg.s  5
0x54466  box      [mscorlib]System.Boolean
0x5446b  stelem.ref
0x5446c  ldloc.s  8
0x5446e  ldc.i4.5
0x5446f  ldarg.s  6
0x54471  box      [mscorlib]System.Boolean
0x54476  stelem.ref
0x54477  ldloc.s  8
0x54479  ldc.i4.6
0x5447a  ldarg.s  7
0x5447c  box      [mscorlib]System.Boolean
0x54481  stelem.ref
0x54482  ldloc.s  8
0x54484  ldc.i4.7
0x54485  ldarg.s  8
0x54487  box      [mscorlib]System.Boolean
0x5448c  stelem.ref
0x5448d  ldloc.s  8
0x5448f  ldc.i4.8
0x54490  ldarg.s  0xB
0x54492  box      [mscorlib]System.Guid
0x54497  stelem.ref
0x54498  ldloc.s  8
0x5449a  ldc.i4.s 9
0x5449c  ldarg.s  0xC
0x5449e  box      [mscorlib]System.Boolean
0x544a3  stelem.ref
0x544a4  ldloc.s  8
0x544a6  ldc.i4.s 0xA
0x544a8  ldarg.s  0xD
0x544aa  stelem.ref
0x544ab  ldloc.s  8
0x544ad  ldc.i4.s 0xB
0x544af  ldarg.s  0x11
0x544b1  box      [mscorlib]System.Boolean
0x544b6  stelem.ref
0x544b7  ldloc.s  8
0x544b9  ldc.i4.s 0xC
0x544bb  ldarg.s  0x12
0x544bd  box      [mscorlib]System.Boolean
0x544c2  stelem.ref
0x544c3  ldloc.s  8
0x544c5  ldc.i4.s 0xD
0x544c7  ldarg.s  0x13
0x544c9  box      [mscorlib]System.Boolean
0x544ce  stelem.ref
0x544cf  ldloc.s  8
0x544d1  ldc.i4.s 0xE
0x544d3  ldarg.s  0x14
0x544d5  box      [mscorlib]System.Boolean
0x544da  stelem.ref
0x544db  ldloc.s  8
0x544dd  ldc.i4.s 0xF
0x544df  ldarg.s  0x15
0x544e1  box      [mscorlib]System.Boolean
0x544e6  stelem.ref
0x544e7  ldloc.s  8
0x544e9  ldc.i4.s 0x10
0x544eb  ldarg.s  0x16
0x544ed  stelem.ref
0x544ee  ldloc.s  8
0x544f0  ldc.i4.s 0x11
0x544f2  ldarg.s  0x17
0x544f4  stelem.ref
0x544f5  ldloc.s  8
0x544f7  ldc.i4.s 0x12
0x544f9  ldarg.s  0x18
0x544fb  stelem.ref
0x544fc  ldloc.s  8
0x544fe  ldc.i4.s 0x13
0x54500  ldarg.s  0x19
0x54502  stelem.ref
0x54503  ldloc.s  8
0x54505  ldloc.0
0x54506  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x5450b  ldloc.0
0x5450c  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x54511  rethrow
0x54513  stloc.1
0x54514  ldstr    aAddorupdateite// "AddOrUpdateItem"
0x54519  ldarg.0
0x5451a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x5451f  ldarg.0
0x54520  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x54525  ldc.i4.s 0x14
0x54527  newarr   [mscorlib]System.String
0x5452c  stloc.s  9
0x5452e  ldloc.s  9
0x54530  ldc.i4.0
0x54531  ldstr    aBstrurl// "bstrUrl"
0x54536  stelem.ref
0x54537  ldloc.s  9
0x54539  ldc.i4.1
0x5453a  ldstr    aBstrlistname// "bstrListName"
0x5453f  stelem.ref
0x54540  ldloc.s  9
0x54542  ldc.i4.2
0x54543  ldstr    aBadd// "bAdd"
0x54548  stelem.ref
0x54549  ldloc.s  9
0x5454b  ldc.i4.3
0x5454c  ldstr    aBsystemupdate// "bSystemUpdate"
0x54551  stelem.ref
0x54552  ldloc.s  9
0x54554  ldc.i4.4
0x54555  ldstr    aBpreserveitemv// "bPreserveItemVersion"
0x5455a  stelem.ref
0x5455b  ldloc.s  9
0x5455d  ldc.i4.5
0x5455e  ldstr    aBpreserveitemu// "bPreserveItemUIVersion"
0x54563  stelem.ref
0x54564  ldloc.s  9
0x54566  ldc.i4.6
0x54567  ldstr    aBupdatenoversi// "bUpdateNoVersion"
0x5456c  stelem.ref
0x5456d  ldloc.s  9
0x5456f  ldc.i4.7
0x54570  ldstr    aBnodemote// "bNoDemote"
0x54575  stelem.ref
0x54576  ldloc.s  9
0x54578  ldc.i4.8
0x54579  ldstr    aPbstrnewdocid// "pbstrNewDocId"
0x5457e  stelem.ref
0x5457f  ldloc.s  9
0x54581  ldc.i4.s 9
0x54583  ldstr    aBhasnewdocid// "bHasNewDocId"
0x54588  stelem.ref
0x54589  ldloc.s  9
0x5458b  ldc.i4.s 0xA
  ... truncated ...
```
