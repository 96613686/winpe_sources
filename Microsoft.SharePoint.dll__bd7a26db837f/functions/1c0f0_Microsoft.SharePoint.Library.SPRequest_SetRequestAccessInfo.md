# Microsoft.SharePoint.Library.SPRequest::SetRequestAccessInfo

- ea: `0x1c0f0`
- end: `0x1c434`
- name: `Microsoft.SharePoint.Library.SPRequest::SetRequestAccessInfo`
- size: `836`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x346a00`
- `0x346b40`
- `0x5c33e0`
- `0x5c3750`

## callees

- `0x30b0`
- `0x1c0f0`
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

- `0x1c0fc`: `SPRequest.SetRequestAccessInfo`
- `0x1c156`: `SetRequestAccessInfo`
- `0x1c1dc`: `SetRequestAccessInfo`
- `0x1c263`: `SetRequestAccessInfo`
- `0x1c301`: `SetRequestAccessInfo`
- `0x1c394`: `SetRequestAccessInfo`
- `0x1c18d`: `bGrantRequestAccess`
- `0x1c213`: `bGrantRequestAccess`
- `0x1c29a`: `bGrantRequestAccess`
- `0x1c338`: `bGrantRequestAccess`
- `0x1c3cb`: `bGrantRequestAccess`
- `0x1c196`: `bstrRequestAccessEmail`
- `0x1c21c`: `bstrRequestAccessEmail`
- `0x1c2a3`: `bstrRequestAccessEmail`
- `0x1c341`: `bstrRequestAccessEmail`
- `0x1c3d4`: `bstrRequestAccessEmail`

## pseudocode

```c

```

## disassembly

```asm
0x1c0f0  ldc.i4   0x66366C37
0x1c0f5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x1c0fa  ldc.i4.s 0x64
0x1c0fc  ldstr    aSprequestSetre// "SPRequest.SetRequestAccessInfo"
0x1c101  ldc.i4.1
0x1c102  ldc.i4.2
0x1c103  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x1c108  stloc.s  5
0x1c10a  ldloc.s  5
0x1c10c  ldc.i4.0
0x1c10d  ldc.i4   0x96
0x1c112  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x1c117  stelem.ref
0x1c118  ldloc.s  5
0x1c11a  ldc.i4.1
0x1c11b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x1c120  stelem.ref
0x1c121  ldloc.s  5
0x1c123  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x1c128  stloc.s  6
0x1c12a  ldarg.0
0x1c12b  dup
0x1c12c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x1c131  ldc.i4.1
0x1c132  add
0x1c133  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x1c138  ldarg.0
0x1c139  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x1c13e  ldarg.0
0x1c13f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x1c144  ldarg.1
0x1c145  ldarg.2
0x1c146  ldarg.3
0x1c147  ldarg.s  4
0x1c149  ldarg.s  5
0x1c14b  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::SetRequestAccessInfo(string, string, unsigned int32, bool, string)
0x1c150  leave    loc_1C414
0x1c155  stloc.0
0x1c156  ldstr    aSetrequestacce// "SetRequestAccessInfo"
0x1c15b  ldarg.0
0x1c15c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1c161  ldarg.0
0x1c162  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x1c167  ldc.i4.5
0x1c168  newarr   [mscorlib]System.String
0x1c16d  stloc.s  7
0x1c16f  ldloc.s  7
0x1c171  ldc.i4.0
0x1c172  ldstr    aBstrurl// "bstrUrl"
0x1c177  stelem.ref
0x1c178  ldloc.s  7
0x1c17a  ldc.i4.1
0x1c17b  ldstr    aBstrlistname// "bstrListName"
0x1c180  stelem.ref
0x1c181  ldloc.s  7
0x1c183  ldc.i4.2
0x1c184  ldstr    aDwobjecttype// "dwObjectType"
0x1c189  stelem.ref
0x1c18a  ldloc.s  7
0x1c18c  ldc.i4.3
0x1c18d  ldstr    aBgrantrequesta// "bGrantRequestAccess"
0x1c192  stelem.ref
0x1c193  ldloc.s  7
0x1c195  ldc.i4.4
0x1c196  ldstr    aBstrrequestacc// "bstrRequestAccessEmail"
0x1c19b  stelem.ref
0x1c19c  ldloc.s  7
0x1c19e  ldc.i4.5
0x1c19f  newarr   [mscorlib]System.Object
0x1c1a4  stloc.s  8
0x1c1a6  ldloc.s  8
0x1c1a8  ldc.i4.0
0x1c1a9  ldarg.1
0x1c1aa  stelem.ref
0x1c1ab  ldloc.s  8
0x1c1ad  ldc.i4.1
0x1c1ae  ldarg.2
0x1c1af  stelem.ref
0x1c1b0  ldloc.s  8
0x1c1b2  ldc.i4.2
0x1c1b3  ldarg.3
0x1c1b4  box      [mscorlib]System.UInt32
0x1c1b9  stelem.ref
0x1c1ba  ldloc.s  8
0x1c1bc  ldc.i4.3
0x1c1bd  ldarg.s  4
0x1c1bf  box      [mscorlib]System.Boolean
0x1c1c4  stelem.ref
0x1c1c5  ldloc.s  8
0x1c1c7  ldc.i4.4
0x1c1c8  ldarg.s  5
0x1c1ca  stelem.ref
0x1c1cb  ldloc.s  8
0x1c1cd  ldloc.0
0x1c1ce  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x1c1d3  ldloc.0
0x1c1d4  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x1c1d9  rethrow
0x1c1db  stloc.1
0x1c1dc  ldstr    aSetrequestacce// "SetRequestAccessInfo"
0x1c1e1  ldarg.0
0x1c1e2  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1c1e7  ldarg.0
0x1c1e8  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x1c1ed  ldc.i4.5
0x1c1ee  newarr   [mscorlib]System.String
0x1c1f3  stloc.s  9
0x1c1f5  ldloc.s  9
0x1c1f7  ldc.i4.0
0x1c1f8  ldstr    aBstrurl// "bstrUrl"
0x1c1fd  stelem.ref
0x1c1fe  ldloc.s  9
0x1c200  ldc.i4.1
0x1c201  ldstr    aBstrlistname// "bstrListName"
0x1c206  stelem.ref
0x1c207  ldloc.s  9
0x1c209  ldc.i4.2
0x1c20a  ldstr    aDwobjecttype// "dwObjectType"
0x1c20f  stelem.ref
0x1c210  ldloc.s  9
0x1c212  ldc.i4.3
0x1c213  ldstr    aBgrantrequesta// "bGrantRequestAccess"
0x1c218  stelem.ref
0x1c219  ldloc.s  9
0x1c21b  ldc.i4.4
0x1c21c  ldstr    aBstrrequestacc// "bstrRequestAccessEmail"
0x1c221  stelem.ref
0x1c222  ldloc.s  9
0x1c224  ldc.i4.5
0x1c225  newarr   [mscorlib]System.Object
0x1c22a  stloc.s  0xA
0x1c22c  ldloc.s  0xA
0x1c22e  ldc.i4.0
0x1c22f  ldarg.1
0x1c230  stelem.ref
0x1c231  ldloc.s  0xA
0x1c233  ldc.i4.1
0x1c234  ldarg.2
0x1c235  stelem.ref
0x1c236  ldloc.s  0xA
0x1c238  ldc.i4.2
0x1c239  ldarg.3
0x1c23a  box      [mscorlib]System.UInt32
0x1c23f  stelem.ref
0x1c240  ldloc.s  0xA
0x1c242  ldc.i4.3
0x1c243  ldarg.s  4
0x1c245  box      [mscorlib]System.Boolean
0x1c24a  stelem.ref
0x1c24b  ldloc.s  0xA
0x1c24d  ldc.i4.4
0x1c24e  ldarg.s  5
0x1c250  stelem.ref
0x1c251  ldloc.s  0xA
0x1c253  ldloc.1
0x1c254  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x1c259  ldloc.1
0x1c25a  ldc.i4.0
0x1c25b  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x1c260  rethrow
0x1c262  stloc.2
0x1c263  ldstr    aSetrequestacce// "SetRequestAccessInfo"
0x1c268  ldarg.0
0x1c269  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1c26e  ldarg.0
0x1c26f  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x1c274  ldc.i4.5
0x1c275  newarr   [mscorlib]System.String
0x1c27a  stloc.s  0xB
0x1c27c  ldloc.s  0xB
0x1c27e  ldc.i4.0
0x1c27f  ldstr    aBstrurl// "bstrUrl"
0x1c284  stelem.ref
0x1c285  ldloc.s  0xB
0x1c287  ldc.i4.1
0x1c288  ldstr    aBstrlistname// "bstrListName"
0x1c28d  stelem.ref
0x1c28e  ldloc.s  0xB
0x1c290  ldc.i4.2
0x1c291  ldstr    aDwobjecttype// "dwObjectType"
0x1c296  stelem.ref
0x1c297  ldloc.s  0xB
0x1c299  ldc.i4.3
0x1c29a  ldstr    aBgrantrequesta// "bGrantRequestAccess"
0x1c29f  stelem.ref
0x1c2a0  ldloc.s  0xB
0x1c2a2  ldc.i4.4
0x1c2a3  ldstr    aBstrrequestacc// "bstrRequestAccessEmail"
0x1c2a8  stelem.ref
0x1c2a9  ldloc.s  0xB
0x1c2ab  ldc.i4.5
0x1c2ac  newarr   [mscorlib]System.Object
0x1c2b1  stloc.s  0xC
0x1c2b3  ldloc.s  0xC
0x1c2b5  ldc.i4.0
0x1c2b6  ldarg.1
0x1c2b7  stelem.ref
0x1c2b8  ldloc.s  0xC
0x1c2ba  ldc.i4.1
0x1c2bb  ldarg.2
0x1c2bc  stelem.ref
0x1c2bd  ldloc.s  0xC
0x1c2bf  ldc.i4.2
0x1c2c0  ldarg.3
0x1c2c1  box      [mscorlib]System.UInt32
0x1c2c6  stelem.ref
0x1c2c7  ldloc.s  0xC
0x1c2c9  ldc.i4.3
0x1c2ca  ldarg.s  4
0x1c2cc  box      [mscorlib]System.Boolean
0x1c2d1  stelem.ref
0x1c2d2  ldloc.s  0xC
0x1c2d4  ldc.i4.4
0x1c2d5  ldarg.s  5
0x1c2d7  stelem.ref
0x1c2d8  ldloc.s  0xC
0x1c2da  ldloc.2
0x1c2db  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x1c2e0  ldloc.2
0x1c2e1  ldarg.0
0x1c2e2  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x1c2e7  ldarg.0
0x1c2e8  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x1c2ed  ldarg.0
0x1c2ee  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x1c2f3  ldarg.0
0x1c2f4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x1c2f9  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x1c2fe  rethrow
0x1c300  stloc.3
0x1c301  ldstr    aSetrequestacce// "SetRequestAccessInfo"
0x1c306  ldarg.0
0x1c307  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1c30c  ldarg.0
0x1c30d  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x1c312  ldc.i4.5
0x1c313  newarr   [mscorlib]System.String
0x1c318  stloc.s  0xD
0x1c31a  ldloc.s  0xD
0x1c31c  ldc.i4.0
0x1c31d  ldstr    aBstrurl// "bstrUrl"
0x1c322  stelem.ref
0x1c323  ldloc.s  0xD
0x1c325  ldc.i4.1
0x1c326  ldstr    aBstrlistname// "bstrListName"
0x1c32b  stelem.ref
0x1c32c  ldloc.s  0xD
0x1c32e  ldc.i4.2
0x1c32f  ldstr    aDwobjecttype// "dwObjectType"
0x1c334  stelem.ref
0x1c335  ldloc.s  0xD
0x1c337  ldc.i4.3
0x1c338  ldstr    aBgrantrequesta// "bGrantRequestAccess"
0x1c33d  stelem.ref
0x1c33e  ldloc.s  0xD
0x1c340  ldc.i4.4
0x1c341  ldstr    aBstrrequestacc// "bstrRequestAccessEmail"
0x1c346  stelem.ref
0x1c347  ldloc.s  0xD
0x1c349  ldc.i4.5
0x1c34a  newarr   [mscorlib]System.Object
0x1c34f  stloc.s  0xE
0x1c351  ldloc.s  0xE
0x1c353  ldc.i4.0
0x1c354  ldarg.1
0x1c355  stelem.ref
0x1c356  ldloc.s  0xE
0x1c358  ldc.i4.1
0x1c359  ldarg.2
0x1c35a  stelem.ref
0x1c35b  ldloc.s  0xE
0x1c35d  ldc.i4.2
0x1c35e  ldarg.3
0x1c35f  box      [mscorlib]System.UInt32
0x1c364  stelem.ref
0x1c365  ldloc.s  0xE
0x1c367  ldc.i4.3
0x1c368  ldarg.s  4
0x1c36a  box      [mscorlib]System.Boolean
0x1c36f  stelem.ref
0x1c370  ldloc.s  0xE
0x1c372  ldc.i4.4
0x1c373  ldarg.s  5
0x1c375  stelem.ref
0x1c376  ldloc.s  0xE
0x1c378  ldloc.3
0x1c379  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x1c37e  ldloc.3
0x1c37f  ldarg.0
0x1c380  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x1c385  ldarg.0
0x1c386  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTraceOnRelease
0x1c38b  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestNullReferenceException(class [mscorlib]System.NullReferenceException nullEx, string stackTraceOnCreate, string stackTraceOnRelease)
0x1c390  rethrow
0x1c392  stloc.s  4
0x1c394  ldstr    aSetrequestacce// "SetRequestAccessInfo"
0x1c399  ldarg.0
0x1c39a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1c39f  ldarg.0
0x1c3a0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
  ... truncated ...
```
