# Microsoft.SharePoint.Library.SPRequest::ApplyWebTemplate

- ea: `0x47330`
- end: `0x47691`
- name: `Microsoft.SharePoint.Library.SPRequest::ApplyWebTemplate`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x5c71f0`

## callees

- `0x30b0`
- `0x47330`
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

- `0x4733c`: `SPRequest.ApplyWebTemplate`
- `0x4739a`: `ApplyWebTemplate`
- `0x47425`: `ApplyWebTemplate`
- `0x474b1`: `ApplyWebTemplate`
- `0x47554`: `ApplyWebTemplate`
- `0x475ec`: `ApplyWebTemplate`
- `0x473bf`: `bstrWebTemplateContent`
- `0x4744a`: `bstrWebTemplateContent`
- `0x474d6`: `bstrWebTemplateContent`
- `0x47579`: `bstrWebTemplateContent`
- `0x47611`: `bstrWebTemplateContent`
- `0x473c8`: `fWebTemplateContentFromSubweb`
- `0x47453`: `fWebTemplateContentFromSubweb`
- `0x474df`: `fWebTemplateContentFromSubweb`
- `0x47582`: `fWebTemplateContentFromSubweb`
- `0x4761a`: `fWebTemplateContentFromSubweb`
- `0x473d1`: `fDeleteGlobalListsWithWebTemplateContent`
- `0x4745c`: `fDeleteGlobalListsWithWebTemplateContent`
- `0x474e8`: `fDeleteGlobalListsWithWebTemplateContent`
- `0x4758b`: `fDeleteGlobalListsWithWebTemplateContent`
- `0x47623`: `fDeleteGlobalListsWithWebTemplateContent`

## pseudocode

```c

```

## disassembly

```asm
0x47330  ldc.i4   0x66366C37
0x47335  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4733a  ldc.i4.s 0x64
0x4733c  ldstr    aSprequestApply_0// "SPRequest.ApplyWebTemplate"
0x47341  ldc.i4.1
0x47342  ldc.i4.2
0x47343  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x47348  stloc.s  5
0x4734a  ldloc.s  5
0x4734c  ldc.i4.0
0x4734d  ldc.i4   0x96
0x47352  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x47357  stelem.ref
0x47358  ldloc.s  5
0x4735a  ldc.i4.1
0x4735b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x47360  stelem.ref
0x47361  ldloc.s  5
0x47363  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x47368  stloc.s  6
0x4736a  ldarg.0
0x4736b  dup
0x4736c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x47371  ldc.i4.1
0x47372  add
0x47373  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x47378  ldarg.0
0x47379  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x4737e  ldarg.0
0x4737f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x47384  ldarg.1
0x47385  ldarg.2
0x47386  ldarg.3
0x47387  ldarg.s  4
0x47389  ldarg.s  5
0x4738b  ldarg.s  6
0x4738d  ldarg.s  7
0x4738f  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::ApplyWebTemplate(string, string, int32, int32, int32, string&, int32&)
0x47394  leave    loc_47671
0x47399  stloc.0
0x4739a  ldstr    aApplywebtempla// "ApplyWebTemplate"
0x4739f  ldarg.0
0x473a0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x473a5  ldarg.0
0x473a6  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x473ab  ldc.i4.5
0x473ac  newarr   [mscorlib]System.String
0x473b1  stloc.s  7
0x473b3  ldloc.s  7
0x473b5  ldc.i4.0
0x473b6  ldstr    aBstrurl// "bstrUrl"
0x473bb  stelem.ref
0x473bc  ldloc.s  7
0x473be  ldc.i4.1
0x473bf  ldstr    aBstrwebtemplat// "bstrWebTemplateContent"
0x473c4  stelem.ref
0x473c5  ldloc.s  7
0x473c7  ldc.i4.2
0x473c8  ldstr    aFwebtemplateco// "fWebTemplateContentFromSubweb"
0x473cd  stelem.ref
0x473ce  ldloc.s  7
0x473d0  ldc.i4.3
0x473d1  ldstr    aFdeletegloball// "fDeleteGlobalListsWithWebTemplateConten"...
0x473d6  stelem.ref
0x473d7  ldloc.s  7
0x473d9  ldc.i4.4
0x473da  ldstr    aFignoremissing// "fIgnoreMissingFeatures"
0x473df  stelem.ref
0x473e0  ldloc.s  7
0x473e2  ldc.i4.5
0x473e3  newarr   [mscorlib]System.Object
0x473e8  stloc.s  8
0x473ea  ldloc.s  8
0x473ec  ldc.i4.0
0x473ed  ldarg.1
0x473ee  stelem.ref
0x473ef  ldloc.s  8
0x473f1  ldc.i4.1
0x473f2  ldarg.2
0x473f3  stelem.ref
0x473f4  ldloc.s  8
0x473f6  ldc.i4.2
0x473f7  ldarg.3
0x473f8  box      [mscorlib]System.Int32
0x473fd  stelem.ref
0x473fe  ldloc.s  8
0x47400  ldc.i4.3
0x47401  ldarg.s  4
0x47403  box      [mscorlib]System.Int32
0x47408  stelem.ref
0x47409  ldloc.s  8
0x4740b  ldc.i4.4
0x4740c  ldarg.s  5
0x4740e  box      [mscorlib]System.Int32
0x47413  stelem.ref
0x47414  ldloc.s  8
0x47416  ldloc.0
0x47417  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4741c  ldloc.0
0x4741d  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x47422  rethrow
0x47424  stloc.1
0x47425  ldstr    aApplywebtempla// "ApplyWebTemplate"
0x4742a  ldarg.0
0x4742b  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x47430  ldarg.0
0x47431  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x47436  ldc.i4.5
0x47437  newarr   [mscorlib]System.String
0x4743c  stloc.s  9
0x4743e  ldloc.s  9
0x47440  ldc.i4.0
0x47441  ldstr    aBstrurl// "bstrUrl"
0x47446  stelem.ref
0x47447  ldloc.s  9
0x47449  ldc.i4.1
0x4744a  ldstr    aBstrwebtemplat// "bstrWebTemplateContent"
0x4744f  stelem.ref
0x47450  ldloc.s  9
0x47452  ldc.i4.2
0x47453  ldstr    aFwebtemplateco// "fWebTemplateContentFromSubweb"
0x47458  stelem.ref
0x47459  ldloc.s  9
0x4745b  ldc.i4.3
0x4745c  ldstr    aFdeletegloball// "fDeleteGlobalListsWithWebTemplateConten"...
0x47461  stelem.ref
0x47462  ldloc.s  9
0x47464  ldc.i4.4
0x47465  ldstr    aFignoremissing// "fIgnoreMissingFeatures"
0x4746a  stelem.ref
0x4746b  ldloc.s  9
0x4746d  ldc.i4.5
0x4746e  newarr   [mscorlib]System.Object
0x47473  stloc.s  0xA
0x47475  ldloc.s  0xA
0x47477  ldc.i4.0
0x47478  ldarg.1
0x47479  stelem.ref
0x4747a  ldloc.s  0xA
0x4747c  ldc.i4.1
0x4747d  ldarg.2
0x4747e  stelem.ref
0x4747f  ldloc.s  0xA
0x47481  ldc.i4.2
0x47482  ldarg.3
0x47483  box      [mscorlib]System.Int32
0x47488  stelem.ref
0x47489  ldloc.s  0xA
0x4748b  ldc.i4.3
0x4748c  ldarg.s  4
0x4748e  box      [mscorlib]System.Int32
0x47493  stelem.ref
0x47494  ldloc.s  0xA
0x47496  ldc.i4.4
0x47497  ldarg.s  5
0x47499  box      [mscorlib]System.Int32
0x4749e  stelem.ref
0x4749f  ldloc.s  0xA
0x474a1  ldloc.1
0x474a2  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x474a7  ldloc.1
0x474a8  ldc.i4.0
0x474a9  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x474ae  rethrow
0x474b0  stloc.2
0x474b1  ldstr    aApplywebtempla// "ApplyWebTemplate"
0x474b6  ldarg.0
0x474b7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x474bc  ldarg.0
0x474bd  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x474c2  ldc.i4.5
0x474c3  newarr   [mscorlib]System.String
0x474c8  stloc.s  0xB
0x474ca  ldloc.s  0xB
0x474cc  ldc.i4.0
0x474cd  ldstr    aBstrurl// "bstrUrl"
0x474d2  stelem.ref
0x474d3  ldloc.s  0xB
0x474d5  ldc.i4.1
0x474d6  ldstr    aBstrwebtemplat// "bstrWebTemplateContent"
0x474db  stelem.ref
0x474dc  ldloc.s  0xB
0x474de  ldc.i4.2
0x474df  ldstr    aFwebtemplateco// "fWebTemplateContentFromSubweb"
0x474e4  stelem.ref
0x474e5  ldloc.s  0xB
0x474e7  ldc.i4.3
0x474e8  ldstr    aFdeletegloball// "fDeleteGlobalListsWithWebTemplateConten"...
0x474ed  stelem.ref
0x474ee  ldloc.s  0xB
0x474f0  ldc.i4.4
0x474f1  ldstr    aFignoremissing// "fIgnoreMissingFeatures"
0x474f6  stelem.ref
0x474f7  ldloc.s  0xB
0x474f9  ldc.i4.5
0x474fa  newarr   [mscorlib]System.Object
0x474ff  stloc.s  0xC
0x47501  ldloc.s  0xC
0x47503  ldc.i4.0
0x47504  ldarg.1
0x47505  stelem.ref
0x47506  ldloc.s  0xC
0x47508  ldc.i4.1
0x47509  ldarg.2
0x4750a  stelem.ref
0x4750b  ldloc.s  0xC
0x4750d  ldc.i4.2
0x4750e  ldarg.3
0x4750f  box      [mscorlib]System.Int32
0x47514  stelem.ref
0x47515  ldloc.s  0xC
0x47517  ldc.i4.3
0x47518  ldarg.s  4
0x4751a  box      [mscorlib]System.Int32
0x4751f  stelem.ref
0x47520  ldloc.s  0xC
0x47522  ldc.i4.4
0x47523  ldarg.s  5
0x47525  box      [mscorlib]System.Int32
0x4752a  stelem.ref
0x4752b  ldloc.s  0xC
0x4752d  ldloc.2
0x4752e  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x47533  ldloc.2
0x47534  ldarg.0
0x47535  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x4753a  ldarg.0
0x4753b  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x47540  ldarg.0
0x47541  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x47546  ldarg.0
0x47547  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x4754c  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x47551  rethrow
0x47553  stloc.3
0x47554  ldstr    aApplywebtempla// "ApplyWebTemplate"
0x47559  ldarg.0
0x4755a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4755f  ldarg.0
0x47560  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x47565  ldc.i4.5
0x47566  newarr   [mscorlib]System.String
0x4756b  stloc.s  0xD
0x4756d  ldloc.s  0xD
0x4756f  ldc.i4.0
0x47570  ldstr    aBstrurl// "bstrUrl"
0x47575  stelem.ref
0x47576  ldloc.s  0xD
0x47578  ldc.i4.1
0x47579  ldstr    aBstrwebtemplat// "bstrWebTemplateContent"
0x4757e  stelem.ref
0x4757f  ldloc.s  0xD
0x47581  ldc.i4.2
0x47582  ldstr    aFwebtemplateco// "fWebTemplateContentFromSubweb"
0x47587  stelem.ref
0x47588  ldloc.s  0xD
0x4758a  ldc.i4.3
0x4758b  ldstr    aFdeletegloball// "fDeleteGlobalListsWithWebTemplateConten"...
0x47590  stelem.ref
0x47591  ldloc.s  0xD
0x47593  ldc.i4.4
0x47594  ldstr    aFignoremissing// "fIgnoreMissingFeatures"
0x47599  stelem.ref
0x4759a  ldloc.s  0xD
0x4759c  ldc.i4.5
0x4759d  newarr   [mscorlib]System.Object
0x475a2  stloc.s  0xE
0x475a4  ldloc.s  0xE
0x475a6  ldc.i4.0
0x475a7  ldarg.1
0x475a8  stelem.ref
0x475a9  ldloc.s  0xE
0x475ab  ldc.i4.1
0x475ac  ldarg.2
0x475ad  stelem.ref
0x475ae  ldloc.s  0xE
0x475b0  ldc.i4.2
0x475b1  ldarg.3
0x475b2  box      [mscorlib]System.Int32
0x475b7  stelem.ref
0x475b8  ldloc.s  0xE
0x475ba  ldc.i4.3
0x475bb  ldarg.s  4
0x475bd  box      [mscorlib]System.Int32
0x475c2  stelem.ref
0x475c3  ldloc.s  0xE
0x475c5  ldc.i4.4
0x475c6  ldarg.s  5
0x475c8  box      [mscorlib]System.Int32
0x475cd  stelem.ref
0x475ce  ldloc.s  0xE
0x475d0  ldloc.3
0x475d1  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x475d6  ldloc.3
0x475d7  ldarg.0
0x475d8  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x475dd  ldarg.0
0x475de  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTraceOnRelease
0x475e3  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestNullReferenceException(class [mscorlib]System.NullReferenceException nullEx, string stackTraceOnCreate, string stackTraceOnRelease)
0x475e8  rethrow
  ... truncated ...
```
