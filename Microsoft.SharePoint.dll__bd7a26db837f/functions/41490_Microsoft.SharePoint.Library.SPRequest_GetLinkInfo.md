# Microsoft.SharePoint.Library.SPRequest::GetLinkInfo

- ea: `0x41490`
- end: `0x41755`
- name: `Microsoft.SharePoint.Library.SPRequest::GetLinkInfo`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x531d40`

## callees

- `0x30b0`
- `0x41490`
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

- `0x4149c`: `SPRequest.GetLinkInfo`
- `0x414f4`: `GetLinkInfo`
- `0x41561`: `GetLinkInfo`
- `0x415cf`: `GetLinkInfo`
- `0x41654`: `GetLinkInfo`
- `0x416ce`: `GetLinkInfo`
- `0x41522`: `pisawForwardLinks`
- `0x4158f`: `pisawForwardLinks`
- `0x415fd`: `pisawForwardLinks`
- `0x41682`: `pisawForwardLinks`
- `0x416fc`: `pisawForwardLinks`
- `0x4152b`: `pisawBackwardLinks`
- `0x41598`: `pisawBackwardLinks`
- `0x41606`: `pisawBackwardLinks`
- `0x4168b`: `pisawBackwardLinks`
- `0x41705`: `pisawBackwardLinks`

## pseudocode

```c

```

## disassembly

```asm
0x41490  ldc.i4   0x66366C37
0x41495  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4149a  ldc.i4.s 0x64
0x4149c  ldstr    aSprequestGetli_7// "SPRequest.GetLinkInfo"
0x414a1  ldc.i4.1
0x414a2  ldc.i4.2
0x414a3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x414a8  stloc.s  5
0x414aa  ldloc.s  5
0x414ac  ldc.i4.0
0x414ad  ldc.i4   0x96
0x414b2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x414b7  stelem.ref
0x414b8  ldloc.s  5
0x414ba  ldc.i4.1
0x414bb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x414c0  stelem.ref
0x414c1  ldloc.s  5
0x414c3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x414c8  stloc.s  6
0x414ca  ldarg.0
0x414cb  dup
0x414cc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x414d1  ldc.i4.1
0x414d2  add
0x414d3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x414d8  ldarg.0
0x414d9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x414de  ldarg.0
0x414df  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x414e4  ldarg.1
0x414e5  ldarg.2
0x414e6  ldarg.3
0x414e7  ldarg.s  4
0x414e9  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::GetLinkInfo(string, string, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISP2DSafeArrayWriter, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISP2DSafeArrayWriter)
0x414ee  leave    loc_41735
0x414f3  stloc.0
0x414f4  ldstr    aGetlinkinfo// "GetLinkInfo"
0x414f9  ldarg.0
0x414fa  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x414ff  ldarg.0
0x41500  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x41505  ldc.i4.4
0x41506  newarr   [mscorlib]System.String
0x4150b  stloc.s  7
0x4150d  ldloc.s  7
0x4150f  ldc.i4.0
0x41510  ldstr    aBstrurl// "bstrUrl"
0x41515  stelem.ref
0x41516  ldloc.s  7
0x41518  ldc.i4.1
0x41519  ldstr    aBstrwebrelfile// "bstrWebRelFileUrl"
0x4151e  stelem.ref
0x4151f  ldloc.s  7
0x41521  ldc.i4.2
0x41522  ldstr    aPisawforwardli// "pisawForwardLinks"
0x41527  stelem.ref
0x41528  ldloc.s  7
0x4152a  ldc.i4.3
0x4152b  ldstr    aPisawbackwardl// "pisawBackwardLinks"
0x41530  stelem.ref
0x41531  ldloc.s  7
0x41533  ldc.i4.4
0x41534  newarr   [mscorlib]System.Object
0x41539  stloc.s  8
0x4153b  ldloc.s  8
0x4153d  ldc.i4.0
0x4153e  ldarg.1
0x4153f  stelem.ref
0x41540  ldloc.s  8
0x41542  ldc.i4.1
0x41543  ldarg.2
0x41544  stelem.ref
0x41545  ldloc.s  8
0x41547  ldc.i4.2
0x41548  ldarg.3
0x41549  stelem.ref
0x4154a  ldloc.s  8
0x4154c  ldc.i4.3
0x4154d  ldarg.s  4
0x4154f  stelem.ref
0x41550  ldloc.s  8
0x41552  ldloc.0
0x41553  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x41558  ldloc.0
0x41559  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x4155e  rethrow
0x41560  stloc.1
0x41561  ldstr    aGetlinkinfo// "GetLinkInfo"
0x41566  ldarg.0
0x41567  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4156c  ldarg.0
0x4156d  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x41572  ldc.i4.4
0x41573  newarr   [mscorlib]System.String
0x41578  stloc.s  9
0x4157a  ldloc.s  9
0x4157c  ldc.i4.0
0x4157d  ldstr    aBstrurl// "bstrUrl"
0x41582  stelem.ref
0x41583  ldloc.s  9
0x41585  ldc.i4.1
0x41586  ldstr    aBstrwebrelfile// "bstrWebRelFileUrl"
0x4158b  stelem.ref
0x4158c  ldloc.s  9
0x4158e  ldc.i4.2
0x4158f  ldstr    aPisawforwardli// "pisawForwardLinks"
0x41594  stelem.ref
0x41595  ldloc.s  9
0x41597  ldc.i4.3
0x41598  ldstr    aPisawbackwardl// "pisawBackwardLinks"
0x4159d  stelem.ref
0x4159e  ldloc.s  9
0x415a0  ldc.i4.4
0x415a1  newarr   [mscorlib]System.Object
0x415a6  stloc.s  0xA
0x415a8  ldloc.s  0xA
0x415aa  ldc.i4.0
0x415ab  ldarg.1
0x415ac  stelem.ref
0x415ad  ldloc.s  0xA
0x415af  ldc.i4.1
0x415b0  ldarg.2
0x415b1  stelem.ref
0x415b2  ldloc.s  0xA
0x415b4  ldc.i4.2
0x415b5  ldarg.3
0x415b6  stelem.ref
0x415b7  ldloc.s  0xA
0x415b9  ldc.i4.3
0x415ba  ldarg.s  4
0x415bc  stelem.ref
0x415bd  ldloc.s  0xA
0x415bf  ldloc.1
0x415c0  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x415c5  ldloc.1
0x415c6  ldc.i4.0
0x415c7  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x415cc  rethrow
0x415ce  stloc.2
0x415cf  ldstr    aGetlinkinfo// "GetLinkInfo"
0x415d4  ldarg.0
0x415d5  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x415da  ldarg.0
0x415db  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x415e0  ldc.i4.4
0x415e1  newarr   [mscorlib]System.String
0x415e6  stloc.s  0xB
0x415e8  ldloc.s  0xB
0x415ea  ldc.i4.0
0x415eb  ldstr    aBstrurl// "bstrUrl"
0x415f0  stelem.ref
0x415f1  ldloc.s  0xB
0x415f3  ldc.i4.1
0x415f4  ldstr    aBstrwebrelfile// "bstrWebRelFileUrl"
0x415f9  stelem.ref
0x415fa  ldloc.s  0xB
0x415fc  ldc.i4.2
0x415fd  ldstr    aPisawforwardli// "pisawForwardLinks"
0x41602  stelem.ref
0x41603  ldloc.s  0xB
0x41605  ldc.i4.3
0x41606  ldstr    aPisawbackwardl// "pisawBackwardLinks"
0x4160b  stelem.ref
0x4160c  ldloc.s  0xB
0x4160e  ldc.i4.4
0x4160f  newarr   [mscorlib]System.Object
0x41614  stloc.s  0xC
0x41616  ldloc.s  0xC
0x41618  ldc.i4.0
0x41619  ldarg.1
0x4161a  stelem.ref
0x4161b  ldloc.s  0xC
0x4161d  ldc.i4.1
0x4161e  ldarg.2
0x4161f  stelem.ref
0x41620  ldloc.s  0xC
0x41622  ldc.i4.2
0x41623  ldarg.3
0x41624  stelem.ref
0x41625  ldloc.s  0xC
0x41627  ldc.i4.3
0x41628  ldarg.s  4
0x4162a  stelem.ref
0x4162b  ldloc.s  0xC
0x4162d  ldloc.2
0x4162e  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x41633  ldloc.2
0x41634  ldarg.0
0x41635  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x4163a  ldarg.0
0x4163b  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x41640  ldarg.0
0x41641  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x41646  ldarg.0
0x41647  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x4164c  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x41651  rethrow
0x41653  stloc.3
0x41654  ldstr    aGetlinkinfo// "GetLinkInfo"
0x41659  ldarg.0
0x4165a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4165f  ldarg.0
0x41660  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x41665  ldc.i4.4
0x41666  newarr   [mscorlib]System.String
0x4166b  stloc.s  0xD
0x4166d  ldloc.s  0xD
0x4166f  ldc.i4.0
0x41670  ldstr    aBstrurl// "bstrUrl"
0x41675  stelem.ref
0x41676  ldloc.s  0xD
0x41678  ldc.i4.1
0x41679  ldstr    aBstrwebrelfile// "bstrWebRelFileUrl"
0x4167e  stelem.ref
0x4167f  ldloc.s  0xD
0x41681  ldc.i4.2
0x41682  ldstr    aPisawforwardli// "pisawForwardLinks"
0x41687  stelem.ref
0x41688  ldloc.s  0xD
0x4168a  ldc.i4.3
0x4168b  ldstr    aPisawbackwardl// "pisawBackwardLinks"
0x41690  stelem.ref
0x41691  ldloc.s  0xD
0x41693  ldc.i4.4
0x41694  newarr   [mscorlib]System.Object
0x41699  stloc.s  0xE
0x4169b  ldloc.s  0xE
0x4169d  ldc.i4.0
0x4169e  ldarg.1
0x4169f  stelem.ref
0x416a0  ldloc.s  0xE
0x416a2  ldc.i4.1
0x416a3  ldarg.2
0x416a4  stelem.ref
0x416a5  ldloc.s  0xE
0x416a7  ldc.i4.2
0x416a8  ldarg.3
0x416a9  stelem.ref
0x416aa  ldloc.s  0xE
0x416ac  ldc.i4.3
0x416ad  ldarg.s  4
0x416af  stelem.ref
0x416b0  ldloc.s  0xE
0x416b2  ldloc.3
0x416b3  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x416b8  ldloc.3
0x416b9  ldarg.0
0x416ba  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x416bf  ldarg.0
0x416c0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTraceOnRelease
0x416c5  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestNullReferenceException(class [mscorlib]System.NullReferenceException nullEx, string stackTraceOnCreate, string stackTraceOnRelease)
0x416ca  rethrow
0x416cc  stloc.s  4
0x416ce  ldstr    aGetlinkinfo// "GetLinkInfo"
0x416d3  ldarg.0
0x416d4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x416d9  ldarg.0
0x416da  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x416df  ldc.i4.4
0x416e0  newarr   [mscorlib]System.String
0x416e5  stloc.s  0xF
0x416e7  ldloc.s  0xF
0x416e9  ldc.i4.0
0x416ea  ldstr    aBstrurl// "bstrUrl"
0x416ef  stelem.ref
0x416f0  ldloc.s  0xF
0x416f2  ldc.i4.1
0x416f3  ldstr    aBstrwebrelfile// "bstrWebRelFileUrl"
0x416f8  stelem.ref
0x416f9  ldloc.s  0xF
0x416fb  ldc.i4.2
0x416fc  ldstr    aPisawforwardli// "pisawForwardLinks"
0x41701  stelem.ref
0x41702  ldloc.s  0xF
0x41704  ldc.i4.3
0x41705  ldstr    aPisawbackwardl// "pisawBackwardLinks"
0x4170a  stelem.ref
0x4170b  ldloc.s  0xF
0x4170d  ldc.i4.4
0x4170e  newarr   [mscorlib]System.Object
0x41713  stloc.s  0x10
0x41715  ldloc.s  0x10
0x41717  ldc.i4.0
0x41718  ldarg.1
0x41719  stelem.ref
0x4171a  ldloc.s  0x10
0x4171c  ldc.i4.1
0x4171d  ldarg.2
0x4171e  stelem.ref
0x4171f  ldloc.s  0x10
0x41721  ldc.i4.2
0x41722  ldarg.3
0x41723  stelem.ref
0x41724  ldloc.s  0x10
0x41726  ldc.i4.3
0x41727  ldarg.s  4
0x41729  stelem.ref
0x4172a  ldloc.s  0x10
0x4172c  ldloc.s  4
  ... truncated ...
```
