# Microsoft.SharePoint.Library.SPRequest::GetListsWithCallback

- ea: `0x4e640`
- end: `0x4ed58`
- name: `Microsoft.SharePoint.Library.SPRequest::GetListsWithCallback`
- size: `1816`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x354d30`
- `0x552c20`

## callees

- `0x30b0`
- `0x4e640`
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

- `0x4e751`: `p2DWriter`
- `0x4e897`: `p2DWriter`
- `0x4e9de`: `p2DWriter`
- `0x4eb3c`: `p2DWriter`
- `0x4ec8f`: `p2DWriter`
- `0x4e70d`: `dwServerTemplate`
- `0x4e853`: `dwServerTemplate`
- `0x4e99a`: `dwServerTemplate`
- `0x4eaf8`: `dwServerTemplate`
- `0x4ec4b`: `dwServerTemplate`
- `0x4e733`: `bSecurityTrimmed`
- `0x4e879`: `bSecurityTrimmed`
- `0x4e9c0`: `bSecurityTrimmed`
- `0x4eb1e`: `bSecurityTrimmed`
- `0x4ec71`: `bSecurityTrimmed`
- `0x4e73d`: `bGetSecurityData`
- `0x4e883`: `bGetSecurityData`
- `0x4e9ca`: `bGetSecurityData`
- `0x4eb28`: `bGetSecurityData`
- `0x4ec7b`: `bGetSecurityData`

## pseudocode

```c

```

## disassembly

```asm
0x4e640  ldc.i4   0x66366C37
0x4e645  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4e64a  ldc.i4.s 0x64
0x4e64c  ldstr    aSprequestGetli_9// "SPRequest.GetListsWithCallback"
0x4e651  ldc.i4.1
0x4e652  ldc.i4.2
0x4e653  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x4e658  stloc.s  5
0x4e65a  ldloc.s  5
0x4e65c  ldc.i4.0
0x4e65d  ldc.i4   0x96
0x4e662  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x4e667  stelem.ref
0x4e668  ldloc.s  5
0x4e66a  ldc.i4.1
0x4e66b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x4e670  stelem.ref
0x4e671  ldloc.s  5
0x4e673  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x4e678  stloc.s  6
0x4e67a  ldarg.0
0x4e67b  dup
0x4e67c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4e681  ldc.i4.1
0x4e682  add
0x4e683  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4e688  ldarg.0
0x4e689  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x4e68e  ldarg.0
0x4e68f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x4e694  ldarg.1
0x4e695  ldarg.2
0x4e696  ldarg.3
0x4e697  ldarg.s  4
0x4e699  ldarg.s  5
0x4e69b  ldarg.s  6
0x4e69d  ldarg.s  7
0x4e69f  ldarg.s  8
0x4e6a1  ldarg.s  9
0x4e6a3  ldarg.s  0xA
0x4e6a5  ldarg.s  0xB
0x4e6a7  ldarg.s  0xC
0x4e6a9  ldarg.s  0xD
0x4e6ab  ldarg.s  0xE
0x4e6ad  ldarg.s  0xF
0x4e6af  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::GetListsWithCallback(string, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, valuetype [mscorlib]System.Guid, string, int32, int32, int32, unsigned int32, unsigned int32, bool, bool, bool, bool, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISP2DSafeArrayWriter, int32&)
0x4e6b4  leave    loc_4ED38
0x4e6b9  stloc.0
0x4e6ba  ldstr    aGetlistswithca// "GetListsWithCallback"
0x4e6bf  ldarg.0
0x4e6c0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4e6c5  ldarg.0
0x4e6c6  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4e6cb  ldc.i4.s 0xE
0x4e6cd  newarr   [mscorlib]System.String
0x4e6d2  stloc.s  7
0x4e6d4  ldloc.s  7
0x4e6d6  ldc.i4.0
0x4e6d7  ldstr    aBstrurl// "bstrUrl"
0x4e6dc  stelem.ref
0x4e6dd  ldloc.s  7
0x4e6df  ldc.i4.1
0x4e6e0  ldstr    aPath// "path"
0x4e6e5  stelem.ref
0x4e6e6  ldloc.s  7
0x4e6e8  ldc.i4.2
0x4e6e9  ldstr    aForeignwebid// "foreignWebId"
0x4e6ee  stelem.ref
0x4e6ef  ldloc.s  7
0x4e6f1  ldc.i4.3
0x4e6f2  ldstr    aBstrlistintern// "bstrListInternalName"
0x4e6f7  stelem.ref
0x4e6f8  ldloc.s  7
0x4e6fa  ldc.i4.4
0x4e6fb  ldstr    aDwbasetype// "dwBaseType"
0x4e700  stelem.ref
0x4e701  ldloc.s  7
0x4e703  ldc.i4.5
0x4e704  ldstr    aDwbasetypealt// "dwBaseTypeAlt"
0x4e709  stelem.ref
0x4e70a  ldloc.s  7
0x4e70c  ldc.i4.6
0x4e70d  ldstr    aDwservertempla// "dwServerTemplate"
0x4e712  stelem.ref
0x4e713  ldloc.s  7
0x4e715  ldc.i4.7
0x4e716  ldstr    aDwgetlistflags// "dwGetListFlags"
0x4e71b  stelem.ref
0x4e71c  ldloc.s  7
0x4e71e  ldc.i4.8
0x4e71f  ldstr    aDwlistfilterfl// "dwListFilterFlags"
0x4e724  stelem.ref
0x4e725  ldloc.s  7
0x4e727  ldc.i4.s 9
0x4e729  ldstr    aBprefetchmetad// "bPrefetchMetaData"
0x4e72e  stelem.ref
0x4e72f  ldloc.s  7
0x4e731  ldc.i4.s 0xA
0x4e733  ldstr    aBsecuritytrimm// "bSecurityTrimmed"
0x4e738  stelem.ref
0x4e739  ldloc.s  7
0x4e73b  ldc.i4.s 0xB
0x4e73d  ldstr    aBgetsecurityda// "bGetSecurityData"
0x4e742  stelem.ref
0x4e743  ldloc.s  7
0x4e745  ldc.i4.s 0xC
0x4e747  ldstr    aBprefetchrelat// "bPrefetchRelatedFields"
0x4e74c  stelem.ref
0x4e74d  ldloc.s  7
0x4e74f  ldc.i4.s 0xD
0x4e751  ldstr    aP2dwriter// "p2DWriter"
0x4e756  stelem.ref
0x4e757  ldloc.s  7
0x4e759  ldc.i4.s 0xE
0x4e75b  newarr   [mscorlib]System.Object
0x4e760  stloc.s  8
0x4e762  ldloc.s  8
0x4e764  ldc.i4.0
0x4e765  ldarg.1
0x4e766  stelem.ref
0x4e767  ldloc.s  8
0x4e769  ldc.i4.1
0x4e76a  ldarg.2
0x4e76b  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x4e770  stelem.ref
0x4e771  ldloc.s  8
0x4e773  ldc.i4.2
0x4e774  ldarg.3
0x4e775  box      [mscorlib]System.Guid
0x4e77a  stelem.ref
0x4e77b  ldloc.s  8
0x4e77d  ldc.i4.3
0x4e77e  ldarg.s  4
0x4e780  stelem.ref
0x4e781  ldloc.s  8
0x4e783  ldc.i4.4
0x4e784  ldarg.s  5
0x4e786  box      [mscorlib]System.Int32
0x4e78b  stelem.ref
0x4e78c  ldloc.s  8
0x4e78e  ldc.i4.5
0x4e78f  ldarg.s  6
0x4e791  box      [mscorlib]System.Int32
0x4e796  stelem.ref
0x4e797  ldloc.s  8
0x4e799  ldc.i4.6
0x4e79a  ldarg.s  7
0x4e79c  box      [mscorlib]System.Int32
0x4e7a1  stelem.ref
0x4e7a2  ldloc.s  8
0x4e7a4  ldc.i4.7
0x4e7a5  ldarg.s  8
0x4e7a7  box      [mscorlib]System.UInt32
0x4e7ac  stelem.ref
0x4e7ad  ldloc.s  8
0x4e7af  ldc.i4.8
0x4e7b0  ldarg.s  9
0x4e7b2  box      [mscorlib]System.UInt32
0x4e7b7  stelem.ref
0x4e7b8  ldloc.s  8
0x4e7ba  ldc.i4.s 9
0x4e7bc  ldarg.s  0xA
0x4e7be  box      [mscorlib]System.Boolean
0x4e7c3  stelem.ref
0x4e7c4  ldloc.s  8
0x4e7c6  ldc.i4.s 0xA
0x4e7c8  ldarg.s  0xB
0x4e7ca  box      [mscorlib]System.Boolean
0x4e7cf  stelem.ref
0x4e7d0  ldloc.s  8
0x4e7d2  ldc.i4.s 0xB
0x4e7d4  ldarg.s  0xC
0x4e7d6  box      [mscorlib]System.Boolean
0x4e7db  stelem.ref
0x4e7dc  ldloc.s  8
0x4e7de  ldc.i4.s 0xC
0x4e7e0  ldarg.s  0xD
0x4e7e2  box      [mscorlib]System.Boolean
0x4e7e7  stelem.ref
0x4e7e8  ldloc.s  8
0x4e7ea  ldc.i4.s 0xD
0x4e7ec  ldarg.s  0xE
0x4e7ee  stelem.ref
0x4e7ef  ldloc.s  8
0x4e7f1  ldloc.0
0x4e7f2  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4e7f7  ldloc.0
0x4e7f8  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x4e7fd  rethrow
0x4e7ff  stloc.1
0x4e800  ldstr    aGetlistswithca// "GetListsWithCallback"
0x4e805  ldarg.0
0x4e806  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4e80b  ldarg.0
0x4e80c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4e811  ldc.i4.s 0xE
0x4e813  newarr   [mscorlib]System.String
0x4e818  stloc.s  9
0x4e81a  ldloc.s  9
0x4e81c  ldc.i4.0
0x4e81d  ldstr    aBstrurl// "bstrUrl"
0x4e822  stelem.ref
0x4e823  ldloc.s  9
0x4e825  ldc.i4.1
0x4e826  ldstr    aPath// "path"
0x4e82b  stelem.ref
0x4e82c  ldloc.s  9
0x4e82e  ldc.i4.2
0x4e82f  ldstr    aForeignwebid// "foreignWebId"
0x4e834  stelem.ref
0x4e835  ldloc.s  9
0x4e837  ldc.i4.3
0x4e838  ldstr    aBstrlistintern// "bstrListInternalName"
0x4e83d  stelem.ref
0x4e83e  ldloc.s  9
0x4e840  ldc.i4.4
0x4e841  ldstr    aDwbasetype// "dwBaseType"
0x4e846  stelem.ref
0x4e847  ldloc.s  9
0x4e849  ldc.i4.5
0x4e84a  ldstr    aDwbasetypealt// "dwBaseTypeAlt"
0x4e84f  stelem.ref
0x4e850  ldloc.s  9
0x4e852  ldc.i4.6
0x4e853  ldstr    aDwservertempla// "dwServerTemplate"
0x4e858  stelem.ref
0x4e859  ldloc.s  9
0x4e85b  ldc.i4.7
0x4e85c  ldstr    aDwgetlistflags// "dwGetListFlags"
0x4e861  stelem.ref
0x4e862  ldloc.s  9
0x4e864  ldc.i4.8
0x4e865  ldstr    aDwlistfilterfl// "dwListFilterFlags"
0x4e86a  stelem.ref
0x4e86b  ldloc.s  9
0x4e86d  ldc.i4.s 9
0x4e86f  ldstr    aBprefetchmetad// "bPrefetchMetaData"
0x4e874  stelem.ref
0x4e875  ldloc.s  9
0x4e877  ldc.i4.s 0xA
0x4e879  ldstr    aBsecuritytrimm// "bSecurityTrimmed"
0x4e87e  stelem.ref
0x4e87f  ldloc.s  9
0x4e881  ldc.i4.s 0xB
0x4e883  ldstr    aBgetsecurityda// "bGetSecurityData"
0x4e888  stelem.ref
0x4e889  ldloc.s  9
0x4e88b  ldc.i4.s 0xC
0x4e88d  ldstr    aBprefetchrelat// "bPrefetchRelatedFields"
0x4e892  stelem.ref
0x4e893  ldloc.s  9
0x4e895  ldc.i4.s 0xD
0x4e897  ldstr    aP2dwriter// "p2DWriter"
0x4e89c  stelem.ref
0x4e89d  ldloc.s  9
0x4e89f  ldc.i4.s 0xE
0x4e8a1  newarr   [mscorlib]System.Object
0x4e8a6  stloc.s  0xA
0x4e8a8  ldloc.s  0xA
0x4e8aa  ldc.i4.0
0x4e8ab  ldarg.1
0x4e8ac  stelem.ref
0x4e8ad  ldloc.s  0xA
0x4e8af  ldc.i4.1
0x4e8b0  ldarg.2
0x4e8b1  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x4e8b6  stelem.ref
0x4e8b7  ldloc.s  0xA
0x4e8b9  ldc.i4.2
0x4e8ba  ldarg.3
0x4e8bb  box      [mscorlib]System.Guid
0x4e8c0  stelem.ref
0x4e8c1  ldloc.s  0xA
0x4e8c3  ldc.i4.3
0x4e8c4  ldarg.s  4
0x4e8c6  stelem.ref
0x4e8c7  ldloc.s  0xA
0x4e8c9  ldc.i4.4
0x4e8ca  ldarg.s  5
0x4e8cc  box      [mscorlib]System.Int32
0x4e8d1  stelem.ref
0x4e8d2  ldloc.s  0xA
0x4e8d4  ldc.i4.5
0x4e8d5  ldarg.s  6
0x4e8d7  box      [mscorlib]System.Int32
0x4e8dc  stelem.ref
0x4e8dd  ldloc.s  0xA
0x4e8df  ldc.i4.6
0x4e8e0  ldarg.s  7
0x4e8e2  box      [mscorlib]System.Int32
0x4e8e7  stelem.ref
0x4e8e8  ldloc.s  0xA
0x4e8ea  ldc.i4.7
0x4e8eb  ldarg.s  8
0x4e8ed  box      [mscorlib]System.UInt32
0x4e8f2  stelem.ref
0x4e8f3  ldloc.s  0xA
0x4e8f5  ldc.i4.8
0x4e8f6  ldarg.s  9
0x4e8f8  box      [mscorlib]System.UInt32
  ... truncated ...
```
