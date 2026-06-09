# Microsoft.SharePoint.Library.SPRequest::CrossListQuery

- ea: `0x56c40`
- end: `0x56f54`
- name: `Microsoft.SharePoint.Library.SPRequest::CrossListQuery`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5ccb80`

## callees

- `0x30b0`
- `0x56c40`
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

- `0x56ccd`: `bstrXmlWebs`
- `0x56d49`: `bstrXmlWebs`
- `0x56dc6`: `bstrXmlWebs`
- `0x56e5a`: `bstrXmlWebs`
- `0x56ee3`: `bstrXmlWebs`
- `0x56cd6`: `bstrXmlLists`
- `0x56d52`: `bstrXmlLists`
- `0x56dcf`: `bstrXmlLists`
- `0x56e63`: `bstrXmlLists`
- `0x56eec`: `bstrXmlLists`
- `0x56cdf`: `bstrXmlQuery`
- `0x56d5b`: `bstrXmlQuery`
- `0x56dd8`: `bstrXmlQuery`
- `0x56e6c`: `bstrXmlQuery`
- `0x56ef5`: `bstrXmlQuery`

## pseudocode

```c

```

## disassembly

```asm
0x56c40  ldc.i4   0x66366C37
0x56c45  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x56c4a  ldc.i4.s 0x64
0x56c4c  ldstr    aSprequestCross// "SPRequest.CrossListQuery"
0x56c51  ldc.i4.1
0x56c52  ldc.i4.2
0x56c53  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x56c58  stloc.s  5
0x56c5a  ldloc.s  5
0x56c5c  ldc.i4.0
0x56c5d  ldc.i4   0x96
0x56c62  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x56c67  stelem.ref
0x56c68  ldloc.s  5
0x56c6a  ldc.i4.1
0x56c6b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x56c70  stelem.ref
0x56c71  ldloc.s  5
0x56c73  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x56c78  stloc.s  6
0x56c7a  ldarg.0
0x56c7b  dup
0x56c7c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x56c81  ldc.i4.1
0x56c82  add
0x56c83  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x56c88  ldarg.0
0x56c89  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x56c8e  ldarg.0
0x56c8f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x56c94  ldarg.1
0x56c95  ldarg.2
0x56c96  ldarg.3
0x56c97  ldarg.s  4
0x56c99  ldarg.s  5
0x56c9b  ldarg.s  6
0x56c9d  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::CrossListQuery(string, string, string, string, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISP2DSafeArrayWriter, object&)
0x56ca2  leave    loc_56F34
0x56ca7  stloc.0
0x56ca8  ldstr    aCrosslistquery// "CrossListQuery"
0x56cad  ldarg.0
0x56cae  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x56cb3  ldarg.0
0x56cb4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x56cb9  ldc.i4.5
0x56cba  newarr   [mscorlib]System.String
0x56cbf  stloc.s  7
0x56cc1  ldloc.s  7
0x56cc3  ldc.i4.0
0x56cc4  ldstr    aBstrurl// "bstrUrl"
0x56cc9  stelem.ref
0x56cca  ldloc.s  7
0x56ccc  ldc.i4.1
0x56ccd  ldstr    aBstrxmlwebs// "bstrXmlWebs"
0x56cd2  stelem.ref
0x56cd3  ldloc.s  7
0x56cd5  ldc.i4.2
0x56cd6  ldstr    aBstrxmllists// "bstrXmlLists"
0x56cdb  stelem.ref
0x56cdc  ldloc.s  7
0x56cde  ldc.i4.3
0x56cdf  ldstr    aBstrxmlquery// "bstrXmlQuery"
0x56ce4  stelem.ref
0x56ce5  ldloc.s  7
0x56ce7  ldc.i4.4
0x56ce8  ldstr    aPcallback// "pCallback"
0x56ced  stelem.ref
0x56cee  ldloc.s  7
0x56cf0  ldc.i4.5
0x56cf1  newarr   [mscorlib]System.Object
0x56cf6  stloc.s  8
0x56cf8  ldloc.s  8
0x56cfa  ldc.i4.0
0x56cfb  ldarg.1
0x56cfc  stelem.ref
0x56cfd  ldloc.s  8
0x56cff  ldc.i4.1
0x56d00  ldarg.2
0x56d01  stelem.ref
0x56d02  ldloc.s  8
0x56d04  ldc.i4.2
0x56d05  ldarg.3
0x56d06  stelem.ref
0x56d07  ldloc.s  8
0x56d09  ldc.i4.3
0x56d0a  ldarg.s  4
0x56d0c  stelem.ref
0x56d0d  ldloc.s  8
0x56d0f  ldc.i4.4
0x56d10  ldarg.s  5
0x56d12  stelem.ref
0x56d13  ldloc.s  8
0x56d15  ldloc.0
0x56d16  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x56d1b  ldloc.0
0x56d1c  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x56d21  rethrow
0x56d23  stloc.1
0x56d24  ldstr    aCrosslistquery// "CrossListQuery"
0x56d29  ldarg.0
0x56d2a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x56d2f  ldarg.0
0x56d30  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x56d35  ldc.i4.5
0x56d36  newarr   [mscorlib]System.String
0x56d3b  stloc.s  9
0x56d3d  ldloc.s  9
0x56d3f  ldc.i4.0
0x56d40  ldstr    aBstrurl// "bstrUrl"
0x56d45  stelem.ref
0x56d46  ldloc.s  9
0x56d48  ldc.i4.1
0x56d49  ldstr    aBstrxmlwebs// "bstrXmlWebs"
0x56d4e  stelem.ref
0x56d4f  ldloc.s  9
0x56d51  ldc.i4.2
0x56d52  ldstr    aBstrxmllists// "bstrXmlLists"
0x56d57  stelem.ref
0x56d58  ldloc.s  9
0x56d5a  ldc.i4.3
0x56d5b  ldstr    aBstrxmlquery// "bstrXmlQuery"
0x56d60  stelem.ref
0x56d61  ldloc.s  9
0x56d63  ldc.i4.4
0x56d64  ldstr    aPcallback// "pCallback"
0x56d69  stelem.ref
0x56d6a  ldloc.s  9
0x56d6c  ldc.i4.5
0x56d6d  newarr   [mscorlib]System.Object
0x56d72  stloc.s  0xA
0x56d74  ldloc.s  0xA
0x56d76  ldc.i4.0
0x56d77  ldarg.1
0x56d78  stelem.ref
0x56d79  ldloc.s  0xA
0x56d7b  ldc.i4.1
0x56d7c  ldarg.2
0x56d7d  stelem.ref
0x56d7e  ldloc.s  0xA
0x56d80  ldc.i4.2
0x56d81  ldarg.3
0x56d82  stelem.ref
0x56d83  ldloc.s  0xA
0x56d85  ldc.i4.3
0x56d86  ldarg.s  4
0x56d88  stelem.ref
0x56d89  ldloc.s  0xA
0x56d8b  ldc.i4.4
0x56d8c  ldarg.s  5
0x56d8e  stelem.ref
0x56d8f  ldloc.s  0xA
0x56d91  ldloc.1
0x56d92  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x56d97  ldloc.1
0x56d98  ldc.i4.0
0x56d99  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x56d9e  rethrow
0x56da0  stloc.2
0x56da1  ldstr    aCrosslistquery// "CrossListQuery"
0x56da6  ldarg.0
0x56da7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x56dac  ldarg.0
0x56dad  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x56db2  ldc.i4.5
0x56db3  newarr   [mscorlib]System.String
0x56db8  stloc.s  0xB
0x56dba  ldloc.s  0xB
0x56dbc  ldc.i4.0
0x56dbd  ldstr    aBstrurl// "bstrUrl"
0x56dc2  stelem.ref
0x56dc3  ldloc.s  0xB
0x56dc5  ldc.i4.1
0x56dc6  ldstr    aBstrxmlwebs// "bstrXmlWebs"
0x56dcb  stelem.ref
0x56dcc  ldloc.s  0xB
0x56dce  ldc.i4.2
0x56dcf  ldstr    aBstrxmllists// "bstrXmlLists"
0x56dd4  stelem.ref
0x56dd5  ldloc.s  0xB
0x56dd7  ldc.i4.3
0x56dd8  ldstr    aBstrxmlquery// "bstrXmlQuery"
0x56ddd  stelem.ref
0x56dde  ldloc.s  0xB
0x56de0  ldc.i4.4
0x56de1  ldstr    aPcallback// "pCallback"
0x56de6  stelem.ref
0x56de7  ldloc.s  0xB
0x56de9  ldc.i4.5
0x56dea  newarr   [mscorlib]System.Object
0x56def  stloc.s  0xC
0x56df1  ldloc.s  0xC
0x56df3  ldc.i4.0
0x56df4  ldarg.1
0x56df5  stelem.ref
0x56df6  ldloc.s  0xC
0x56df8  ldc.i4.1
0x56df9  ldarg.2
0x56dfa  stelem.ref
0x56dfb  ldloc.s  0xC
0x56dfd  ldc.i4.2
0x56dfe  ldarg.3
0x56dff  stelem.ref
0x56e00  ldloc.s  0xC
0x56e02  ldc.i4.3
0x56e03  ldarg.s  4
0x56e05  stelem.ref
0x56e06  ldloc.s  0xC
0x56e08  ldc.i4.4
0x56e09  ldarg.s  5
0x56e0b  stelem.ref
0x56e0c  ldloc.s  0xC
0x56e0e  ldloc.2
0x56e0f  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x56e14  ldloc.2
0x56e15  ldarg.0
0x56e16  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x56e1b  ldarg.0
0x56e1c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x56e21  ldarg.0
0x56e22  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x56e27  ldarg.0
0x56e28  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x56e2d  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x56e32  rethrow
0x56e34  stloc.3
0x56e35  ldstr    aCrosslistquery// "CrossListQuery"
0x56e3a  ldarg.0
0x56e3b  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x56e40  ldarg.0
0x56e41  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x56e46  ldc.i4.5
0x56e47  newarr   [mscorlib]System.String
0x56e4c  stloc.s  0xD
0x56e4e  ldloc.s  0xD
0x56e50  ldc.i4.0
0x56e51  ldstr    aBstrurl// "bstrUrl"
0x56e56  stelem.ref
0x56e57  ldloc.s  0xD
0x56e59  ldc.i4.1
0x56e5a  ldstr    aBstrxmlwebs// "bstrXmlWebs"
0x56e5f  stelem.ref
0x56e60  ldloc.s  0xD
0x56e62  ldc.i4.2
0x56e63  ldstr    aBstrxmllists// "bstrXmlLists"
0x56e68  stelem.ref
0x56e69  ldloc.s  0xD
0x56e6b  ldc.i4.3
0x56e6c  ldstr    aBstrxmlquery// "bstrXmlQuery"
0x56e71  stelem.ref
0x56e72  ldloc.s  0xD
0x56e74  ldc.i4.4
0x56e75  ldstr    aPcallback// "pCallback"
0x56e7a  stelem.ref
0x56e7b  ldloc.s  0xD
0x56e7d  ldc.i4.5
0x56e7e  newarr   [mscorlib]System.Object
0x56e83  stloc.s  0xE
0x56e85  ldloc.s  0xE
0x56e87  ldc.i4.0
0x56e88  ldarg.1
0x56e89  stelem.ref
0x56e8a  ldloc.s  0xE
0x56e8c  ldc.i4.1
0x56e8d  ldarg.2
0x56e8e  stelem.ref
0x56e8f  ldloc.s  0xE
0x56e91  ldc.i4.2
0x56e92  ldarg.3
0x56e93  stelem.ref
0x56e94  ldloc.s  0xE
0x56e96  ldc.i4.3
0x56e97  ldarg.s  4
0x56e99  stelem.ref
0x56e9a  ldloc.s  0xE
0x56e9c  ldc.i4.4
0x56e9d  ldarg.s  5
0x56e9f  stelem.ref
0x56ea0  ldloc.s  0xE
0x56ea2  ldloc.3
0x56ea3  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x56ea8  ldloc.3
0x56ea9  ldarg.0
0x56eaa  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x56eaf  ldarg.0
0x56eb0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTraceOnRelease
0x56eb5  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestNullReferenceException(class [mscorlib]System.NullReferenceException nullEx, string stackTraceOnCreate, string stackTraceOnRelease)
0x56eba  rethrow
0x56ebc  stloc.s  4
0x56ebe  ldstr    aCrosslistquery// "CrossListQuery"
0x56ec3  ldarg.0
0x56ec4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x56ec9  ldarg.0
0x56eca  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x56ecf  ldc.i4.5
0x56ed0  newarr   [mscorlib]System.String
0x56ed5  stloc.s  0xF
0x56ed7  ldloc.s  0xF
0x56ed9  ldc.i4.0
0x56eda  ldstr    aBstrurl// "bstrUrl"
0x56edf  stelem.ref
  ... truncated ...
```
