# Microsoft.SharePoint.Library.SPRequest::UpdateVirusInfo

- ea: `0x45f30`
- end: `0x4652a`
- name: `Microsoft.SharePoint.Library.SPRequest::UpdateVirusInfo`
- size: `1530`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x50eaf0`

## callees

- `0x30b0`
- `0x45f30`
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

- `0x45f3c`: `SPRequest.UpdateVirusInfo`
- `0x45fa4`: `UpdateVirusInfo`
- `0x460b2`: `UpdateVirusInfo`
- `0x461c1`: `UpdateVirusInfo`
- `0x462e7`: `UpdateVirusInfo`
- `0x46402`: `UpdateVirusInfo`
- `0x45fc1`: `spWebPath`
- `0x460cf`: `spWebPath`
- `0x461de`: `spWebPath`
- `0x46304`: `spWebPath`
- `0x4641f`: `spWebPath`
- `0x4601d`: `spFileServerRelPath`
- `0x4612b`: `spFileServerRelPath`
- `0x4623a`: `spFileServerRelPath`
- `0x46360`: `spFileServerRelPath`
- `0x4647b`: `spFileServerRelPath`

## pseudocode

```c

```

## disassembly

```asm
0x45f30  ldc.i4   0x66366C37
0x45f35  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x45f3a  ldc.i4.s 0x64
0x45f3c  ldstr    aSprequestUpdat_14// "SPRequest.UpdateVirusInfo"
0x45f41  ldc.i4.1
0x45f42  ldc.i4.2
0x45f43  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x45f48  stloc.s  5
0x45f4a  ldloc.s  5
0x45f4c  ldc.i4.0
0x45f4d  ldc.i4   0x96
0x45f52  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x45f57  stelem.ref
0x45f58  ldloc.s  5
0x45f5a  ldc.i4.1
0x45f5b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x45f60  stelem.ref
0x45f61  ldloc.s  5
0x45f63  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x45f68  stloc.s  6
0x45f6a  ldarg.0
0x45f6b  dup
0x45f6c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x45f71  ldc.i4.1
0x45f72  add
0x45f73  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x45f78  ldarg.0
0x45f79  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x45f7e  ldarg.0
0x45f7f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x45f84  ldarg.1
0x45f85  ldarg.2
0x45f86  ldarg.3
0x45f87  ldarg.s  4
0x45f89  ldarg.s  5
0x45f8b  ldarg.s  6
0x45f8d  ldarg.s  7
0x45f8f  ldarg.s  8
0x45f91  ldarg.s  9
0x45f93  ldarg.s  0xA
0x45f95  ldarg.s  0xB
0x45f97  ldarg.s  0xC
0x45f99  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::UpdateVirusInfo(valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, valuetype [mscorlib]System.Guid, unsigned int8, unsigned int32, int64, unsigned int8, string, unsigned int32, unsigned int32, valuetype [mscorlib]System.Guid, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, unsigned int8[]&)
0x45f9e  leave    loc_4650A
0x45fa3  stloc.0
0x45fa4  ldstr    aUpdatevirusinf// "UpdateVirusInfo"
0x45fa9  ldarg.0
0x45faa  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x45faf  ldarg.0
0x45fb0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x45fb5  ldc.i4.s 0xB
0x45fb7  newarr   [mscorlib]System.String
0x45fbc  stloc.s  7
0x45fbe  ldloc.s  7
0x45fc0  ldc.i4.0
0x45fc1  ldstr    aSpwebpath// "spWebPath"
0x45fc6  stelem.ref
0x45fc7  ldloc.s  7
0x45fc9  ldc.i4.1
0x45fca  ldstr    aGdocid// "gDocId"
0x45fcf  stelem.ref
0x45fd0  ldloc.s  7
0x45fd2  ldc.i4.2
0x45fd3  ldstr    aIlevel// "iLevel"
0x45fd8  stelem.ref
0x45fd9  ldloc.s  7
0x45fdb  ldc.i4.3
0x45fdc  ldstr    aDwetagversion// "dwEtagVersion"
0x45fe1  stelem.ref
0x45fe2  ldloc.s  7
0x45fe4  ldc.i4.4
0x45fe5  ldstr    aLlnextbsn// "llNextBsn"
0x45fea  stelem.ref
0x45feb  ldloc.s  7
0x45fed  ldc.i4.5
0x45fee  ldstr    aIvirusstatus// "iVirusStatus"
0x45ff3  stelem.ref
0x45ff4  ldloc.s  7
0x45ff6  ldc.i4.6
0x45ff7  ldstr    aBstrvirusmessa// "bstrVirusMessage"
0x45ffc  stelem.ref
0x45ffd  ldloc.s  7
0x45fff  ldc.i4.7
0x46000  ldstr    aDwvirusvendori// "dwVirusVendorId"
0x46005  stelem.ref
0x46006  ldloc.s  7
0x46008  ldc.i4.8
0x46009  ldstr    aDwuiversion// "dwUIVersion"
0x4600e  stelem.ref
0x4600f  ldloc.s  7
0x46011  ldc.i4.s 9
0x46013  ldstr    aGlistid// "gListId"
0x46018  stelem.ref
0x46019  ldloc.s  7
0x4601b  ldc.i4.s 0xA
0x4601d  ldstr    aSpfileserverre// "spFileServerRelPath"
0x46022  stelem.ref
0x46023  ldloc.s  7
0x46025  ldc.i4.s 0xB
0x46027  newarr   [mscorlib]System.Object
0x4602c  stloc.s  8
0x4602e  ldloc.s  8
0x46030  ldc.i4.0
0x46031  ldarg.1
0x46032  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x46037  stelem.ref
0x46038  ldloc.s  8
0x4603a  ldc.i4.1
0x4603b  ldarg.2
0x4603c  box      [mscorlib]System.Guid
0x46041  stelem.ref
0x46042  ldloc.s  8
0x46044  ldc.i4.2
0x46045  ldarg.3
0x46046  box      [mscorlib]System.Byte
0x4604b  stelem.ref
0x4604c  ldloc.s  8
0x4604e  ldc.i4.3
0x4604f  ldarg.s  4
0x46051  box      [mscorlib]System.UInt32
0x46056  stelem.ref
0x46057  ldloc.s  8
0x46059  ldc.i4.4
0x4605a  ldarg.s  5
0x4605c  box      [mscorlib]System.Int64
0x46061  stelem.ref
0x46062  ldloc.s  8
0x46064  ldc.i4.5
0x46065  ldarg.s  6
0x46067  box      [mscorlib]System.Byte
0x4606c  stelem.ref
0x4606d  ldloc.s  8
0x4606f  ldc.i4.6
0x46070  ldarg.s  7
0x46072  stelem.ref
0x46073  ldloc.s  8
0x46075  ldc.i4.7
0x46076  ldarg.s  8
0x46078  box      [mscorlib]System.UInt32
0x4607d  stelem.ref
0x4607e  ldloc.s  8
0x46080  ldc.i4.8
0x46081  ldarg.s  9
0x46083  box      [mscorlib]System.UInt32
0x46088  stelem.ref
0x46089  ldloc.s  8
0x4608b  ldc.i4.s 9
0x4608d  ldarg.s  0xA
0x4608f  box      [mscorlib]System.Guid
0x46094  stelem.ref
0x46095  ldloc.s  8
0x46097  ldc.i4.s 0xA
0x46099  ldarg.s  0xB
0x4609b  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x460a0  stelem.ref
0x460a1  ldloc.s  8
0x460a3  ldloc.0
0x460a4  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x460a9  ldloc.0
0x460aa  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x460af  rethrow
0x460b1  stloc.1
0x460b2  ldstr    aUpdatevirusinf// "UpdateVirusInfo"
0x460b7  ldarg.0
0x460b8  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x460bd  ldarg.0
0x460be  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x460c3  ldc.i4.s 0xB
0x460c5  newarr   [mscorlib]System.String
0x460ca  stloc.s  9
0x460cc  ldloc.s  9
0x460ce  ldc.i4.0
0x460cf  ldstr    aSpwebpath// "spWebPath"
0x460d4  stelem.ref
0x460d5  ldloc.s  9
0x460d7  ldc.i4.1
0x460d8  ldstr    aGdocid// "gDocId"
0x460dd  stelem.ref
0x460de  ldloc.s  9
0x460e0  ldc.i4.2
0x460e1  ldstr    aIlevel// "iLevel"
0x460e6  stelem.ref
0x460e7  ldloc.s  9
0x460e9  ldc.i4.3
0x460ea  ldstr    aDwetagversion// "dwEtagVersion"
0x460ef  stelem.ref
0x460f0  ldloc.s  9
0x460f2  ldc.i4.4
0x460f3  ldstr    aLlnextbsn// "llNextBsn"
0x460f8  stelem.ref
0x460f9  ldloc.s  9
0x460fb  ldc.i4.5
0x460fc  ldstr    aIvirusstatus// "iVirusStatus"
0x46101  stelem.ref
0x46102  ldloc.s  9
0x46104  ldc.i4.6
0x46105  ldstr    aBstrvirusmessa// "bstrVirusMessage"
0x4610a  stelem.ref
0x4610b  ldloc.s  9
0x4610d  ldc.i4.7
0x4610e  ldstr    aDwvirusvendori// "dwVirusVendorId"
0x46113  stelem.ref
0x46114  ldloc.s  9
0x46116  ldc.i4.8
0x46117  ldstr    aDwuiversion// "dwUIVersion"
0x4611c  stelem.ref
0x4611d  ldloc.s  9
0x4611f  ldc.i4.s 9
0x46121  ldstr    aGlistid// "gListId"
0x46126  stelem.ref
0x46127  ldloc.s  9
0x46129  ldc.i4.s 0xA
0x4612b  ldstr    aSpfileserverre// "spFileServerRelPath"
0x46130  stelem.ref
0x46131  ldloc.s  9
0x46133  ldc.i4.s 0xB
0x46135  newarr   [mscorlib]System.Object
0x4613a  stloc.s  0xA
0x4613c  ldloc.s  0xA
0x4613e  ldc.i4.0
0x4613f  ldarg.1
0x46140  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x46145  stelem.ref
0x46146  ldloc.s  0xA
0x46148  ldc.i4.1
0x46149  ldarg.2
0x4614a  box      [mscorlib]System.Guid
0x4614f  stelem.ref
0x46150  ldloc.s  0xA
0x46152  ldc.i4.2
0x46153  ldarg.3
0x46154  box      [mscorlib]System.Byte
0x46159  stelem.ref
0x4615a  ldloc.s  0xA
0x4615c  ldc.i4.3
0x4615d  ldarg.s  4
0x4615f  box      [mscorlib]System.UInt32
0x46164  stelem.ref
0x46165  ldloc.s  0xA
0x46167  ldc.i4.4
0x46168  ldarg.s  5
0x4616a  box      [mscorlib]System.Int64
0x4616f  stelem.ref
0x46170  ldloc.s  0xA
0x46172  ldc.i4.5
0x46173  ldarg.s  6
0x46175  box      [mscorlib]System.Byte
0x4617a  stelem.ref
0x4617b  ldloc.s  0xA
0x4617d  ldc.i4.6
0x4617e  ldarg.s  7
0x46180  stelem.ref
0x46181  ldloc.s  0xA
0x46183  ldc.i4.7
0x46184  ldarg.s  8
0x46186  box      [mscorlib]System.UInt32
0x4618b  stelem.ref
0x4618c  ldloc.s  0xA
0x4618e  ldc.i4.8
0x4618f  ldarg.s  9
0x46191  box      [mscorlib]System.UInt32
0x46196  stelem.ref
0x46197  ldloc.s  0xA
0x46199  ldc.i4.s 9
0x4619b  ldarg.s  0xA
0x4619d  box      [mscorlib]System.Guid
0x461a2  stelem.ref
0x461a3  ldloc.s  0xA
0x461a5  ldc.i4.s 0xA
0x461a7  ldarg.s  0xB
0x461a9  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x461ae  stelem.ref
0x461af  ldloc.s  0xA
0x461b1  ldloc.1
0x461b2  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x461b7  ldloc.1
0x461b8  ldc.i4.0
0x461b9  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x461be  rethrow
0x461c0  stloc.2
0x461c1  ldstr    aUpdatevirusinf// "UpdateVirusInfo"
0x461c6  ldarg.0
0x461c7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x461cc  ldarg.0
0x461cd  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x461d2  ldc.i4.s 0xB
0x461d4  newarr   [mscorlib]System.String
0x461d9  stloc.s  0xB
0x461db  ldloc.s  0xB
0x461dd  ldc.i4.0
0x461de  ldstr    aSpwebpath// "spWebPath"
0x461e3  stelem.ref
0x461e4  ldloc.s  0xB
0x461e6  ldc.i4.1
0x461e7  ldstr    aGdocid// "gDocId"
0x461ec  stelem.ref
0x461ed  ldloc.s  0xB
0x461ef  ldc.i4.2
0x461f0  ldstr    aIlevel// "iLevel"
0x461f5  stelem.ref
  ... truncated ...
```
