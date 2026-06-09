# Microsoft.SharePoint.Library.SPRequest::CreateWeb

- ea: `0x46b90`
- end: `0x46ff3`
- name: `Microsoft.SharePoint.Library.SPRequest::CreateWeb`
- size: `1123`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x26e900`
- `0x5c7b20`

## callees

- `0x30b0`
- `0x46b90`
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

- `0x46b9c`: `SPRequest.CreateWeb`
- `0x46c02`: `CreateWeb`
- `0x46cbf`: `CreateWeb`
- `0x46d7d`: `CreateWeb`
- `0x46e52`: `CreateWeb`
- `0x46f1c`: `CreateWeb`
- `0x46c42`: `bCreateUniqueWeb`
- `0x46cff`: `bCreateUniqueWeb`
- `0x46dbd`: `bCreateUniqueWeb`
- `0x46e92`: `bCreateUniqueWeb`
- `0x46f5c`: `bCreateUniqueWeb`
- `0x46c5d`: `bCreateSystemCatalogs`
- `0x46d1a`: `bCreateSystemCatalogs`
- `0x46dd8`: `bCreateSystemCatalogs`
- `0x46ead`: `bCreateSystemCatalogs`
- `0x46f77`: `bCreateSystemCatalogs`

## pseudocode

```c

```

## disassembly

```asm
0x46b90  ldc.i4   0x66366C37
0x46b95  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x46b9a  ldc.i4.s 0x64
0x46b9c  ldstr    aSprequestCreat_7// "SPRequest.CreateWeb"
0x46ba1  ldc.i4.1
0x46ba2  ldc.i4.2
0x46ba3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x46ba8  stloc.s  5
0x46baa  ldloc.s  5
0x46bac  ldc.i4.0
0x46bad  ldc.i4   0x96
0x46bb2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x46bb7  stelem.ref
0x46bb8  ldloc.s  5
0x46bba  ldc.i4.1
0x46bbb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x46bc0  stelem.ref
0x46bc1  ldloc.s  5
0x46bc3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x46bc8  stloc.s  6
0x46bca  ldarg.0
0x46bcb  dup
0x46bcc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x46bd1  ldc.i4.1
0x46bd2  add
0x46bd3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x46bd8  ldarg.0
0x46bd9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x46bde  ldarg.0
0x46bdf  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x46be4  ldarg.1
0x46be5  ldarg.2
0x46be6  ldarg.3
0x46be7  ldarg.s  4
0x46be9  ldarg.s  5
0x46beb  ldarg.s  6
0x46bed  ldarg.s  7
0x46bef  ldarg.s  8
0x46bf1  ldarg.s  9
0x46bf3  ldarg.s  0xA
0x46bf5  ldarg.s  0xB
0x46bf7  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::CreateWeb(string, string, string, unsigned int32, bool, valuetype [mscorlib]System.Guid&, string, bool, valuetype [mscorlib]System.Guid&, valuetype [mscorlib]System.Guid&, bool)
0x46bfc  leave    loc_46FD3
0x46c01  stloc.0
0x46c02  ldstr    aCreateweb// "CreateWeb"
0x46c07  ldarg.0
0x46c08  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x46c0d  ldarg.0
0x46c0e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x46c13  ldc.i4.8
0x46c14  newarr   [mscorlib]System.String
0x46c19  stloc.s  7
0x46c1b  ldloc.s  7
0x46c1d  ldc.i4.0
0x46c1e  ldstr    aBstrurl// "bstrUrl"
0x46c23  stelem.ref
0x46c24  ldloc.s  7
0x46c26  ldc.i4.1
0x46c27  ldstr    aBstrtitle// "bstrTitle"
0x46c2c  stelem.ref
0x46c2d  ldloc.s  7
0x46c2f  ldc.i4.2
0x46c30  ldstr    aBstrdescriptio// "bstrDescription"
0x46c35  stelem.ref
0x46c36  ldloc.s  7
0x46c38  ldc.i4.3
0x46c39  ldstr    aNlcid// "nLCID"
0x46c3e  stelem.ref
0x46c3f  ldloc.s  7
0x46c41  ldc.i4.4
0x46c42  ldstr    aBcreateuniquew// "bCreateUniqueWeb"
0x46c47  stelem.ref
0x46c48  ldloc.s  7
0x46c4a  ldc.i4.5
0x46c4b  ldstr    aBstrappwebdoma// "bstrAppWebDomainId"
0x46c50  stelem.ref
0x46c51  ldloc.s  7
0x46c53  ldc.i4.6
0x46c54  ldstr    aBconvertifther// "bConvertIfThere"
0x46c59  stelem.ref
0x46c5a  ldloc.s  7
0x46c5c  ldc.i4.7
0x46c5d  ldstr    aBcreatesystemc// "bCreateSystemCatalogs"
0x46c62  stelem.ref
0x46c63  ldloc.s  7
0x46c65  ldc.i4.8
0x46c66  newarr   [mscorlib]System.Object
0x46c6b  stloc.s  8
0x46c6d  ldloc.s  8
0x46c6f  ldc.i4.0
0x46c70  ldarg.1
0x46c71  stelem.ref
0x46c72  ldloc.s  8
0x46c74  ldc.i4.1
0x46c75  ldarg.2
0x46c76  stelem.ref
0x46c77  ldloc.s  8
0x46c79  ldc.i4.2
0x46c7a  ldarg.3
0x46c7b  stelem.ref
0x46c7c  ldloc.s  8
0x46c7e  ldc.i4.3
0x46c7f  ldarg.s  4
0x46c81  box      [mscorlib]System.UInt32
0x46c86  stelem.ref
0x46c87  ldloc.s  8
0x46c89  ldc.i4.4
0x46c8a  ldarg.s  5
0x46c8c  box      [mscorlib]System.Boolean
0x46c91  stelem.ref
0x46c92  ldloc.s  8
0x46c94  ldc.i4.5
0x46c95  ldarg.s  7
0x46c97  stelem.ref
0x46c98  ldloc.s  8
0x46c9a  ldc.i4.6
0x46c9b  ldarg.s  8
0x46c9d  box      [mscorlib]System.Boolean
0x46ca2  stelem.ref
0x46ca3  ldloc.s  8
0x46ca5  ldc.i4.7
0x46ca6  ldarg.s  0xB
0x46ca8  box      [mscorlib]System.Boolean
0x46cad  stelem.ref
0x46cae  ldloc.s  8
0x46cb0  ldloc.0
0x46cb1  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x46cb6  ldloc.0
0x46cb7  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x46cbc  rethrow
0x46cbe  stloc.1
0x46cbf  ldstr    aCreateweb// "CreateWeb"
0x46cc4  ldarg.0
0x46cc5  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x46cca  ldarg.0
0x46ccb  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x46cd0  ldc.i4.8
0x46cd1  newarr   [mscorlib]System.String
0x46cd6  stloc.s  9
0x46cd8  ldloc.s  9
0x46cda  ldc.i4.0
0x46cdb  ldstr    aBstrurl// "bstrUrl"
0x46ce0  stelem.ref
0x46ce1  ldloc.s  9
0x46ce3  ldc.i4.1
0x46ce4  ldstr    aBstrtitle// "bstrTitle"
0x46ce9  stelem.ref
0x46cea  ldloc.s  9
0x46cec  ldc.i4.2
0x46ced  ldstr    aBstrdescriptio// "bstrDescription"
0x46cf2  stelem.ref
0x46cf3  ldloc.s  9
0x46cf5  ldc.i4.3
0x46cf6  ldstr    aNlcid// "nLCID"
0x46cfb  stelem.ref
0x46cfc  ldloc.s  9
0x46cfe  ldc.i4.4
0x46cff  ldstr    aBcreateuniquew// "bCreateUniqueWeb"
0x46d04  stelem.ref
0x46d05  ldloc.s  9
0x46d07  ldc.i4.5
0x46d08  ldstr    aBstrappwebdoma// "bstrAppWebDomainId"
0x46d0d  stelem.ref
0x46d0e  ldloc.s  9
0x46d10  ldc.i4.6
0x46d11  ldstr    aBconvertifther// "bConvertIfThere"
0x46d16  stelem.ref
0x46d17  ldloc.s  9
0x46d19  ldc.i4.7
0x46d1a  ldstr    aBcreatesystemc// "bCreateSystemCatalogs"
0x46d1f  stelem.ref
0x46d20  ldloc.s  9
0x46d22  ldc.i4.8
0x46d23  newarr   [mscorlib]System.Object
0x46d28  stloc.s  0xA
0x46d2a  ldloc.s  0xA
0x46d2c  ldc.i4.0
0x46d2d  ldarg.1
0x46d2e  stelem.ref
0x46d2f  ldloc.s  0xA
0x46d31  ldc.i4.1
0x46d32  ldarg.2
0x46d33  stelem.ref
0x46d34  ldloc.s  0xA
0x46d36  ldc.i4.2
0x46d37  ldarg.3
0x46d38  stelem.ref
0x46d39  ldloc.s  0xA
0x46d3b  ldc.i4.3
0x46d3c  ldarg.s  4
0x46d3e  box      [mscorlib]System.UInt32
0x46d43  stelem.ref
0x46d44  ldloc.s  0xA
0x46d46  ldc.i4.4
0x46d47  ldarg.s  5
0x46d49  box      [mscorlib]System.Boolean
0x46d4e  stelem.ref
0x46d4f  ldloc.s  0xA
0x46d51  ldc.i4.5
0x46d52  ldarg.s  7
0x46d54  stelem.ref
0x46d55  ldloc.s  0xA
0x46d57  ldc.i4.6
0x46d58  ldarg.s  8
0x46d5a  box      [mscorlib]System.Boolean
0x46d5f  stelem.ref
0x46d60  ldloc.s  0xA
0x46d62  ldc.i4.7
0x46d63  ldarg.s  0xB
0x46d65  box      [mscorlib]System.Boolean
0x46d6a  stelem.ref
0x46d6b  ldloc.s  0xA
0x46d6d  ldloc.1
0x46d6e  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x46d73  ldloc.1
0x46d74  ldc.i4.0
0x46d75  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x46d7a  rethrow
0x46d7c  stloc.2
0x46d7d  ldstr    aCreateweb// "CreateWeb"
0x46d82  ldarg.0
0x46d83  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x46d88  ldarg.0
0x46d89  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x46d8e  ldc.i4.8
0x46d8f  newarr   [mscorlib]System.String
0x46d94  stloc.s  0xB
0x46d96  ldloc.s  0xB
0x46d98  ldc.i4.0
0x46d99  ldstr    aBstrurl// "bstrUrl"
0x46d9e  stelem.ref
0x46d9f  ldloc.s  0xB
0x46da1  ldc.i4.1
0x46da2  ldstr    aBstrtitle// "bstrTitle"
0x46da7  stelem.ref
0x46da8  ldloc.s  0xB
0x46daa  ldc.i4.2
0x46dab  ldstr    aBstrdescriptio// "bstrDescription"
0x46db0  stelem.ref
0x46db1  ldloc.s  0xB
0x46db3  ldc.i4.3
0x46db4  ldstr    aNlcid// "nLCID"
0x46db9  stelem.ref
0x46dba  ldloc.s  0xB
0x46dbc  ldc.i4.4
0x46dbd  ldstr    aBcreateuniquew// "bCreateUniqueWeb"
0x46dc2  stelem.ref
0x46dc3  ldloc.s  0xB
0x46dc5  ldc.i4.5
0x46dc6  ldstr    aBstrappwebdoma// "bstrAppWebDomainId"
0x46dcb  stelem.ref
0x46dcc  ldloc.s  0xB
0x46dce  ldc.i4.6
0x46dcf  ldstr    aBconvertifther// "bConvertIfThere"
0x46dd4  stelem.ref
0x46dd5  ldloc.s  0xB
0x46dd7  ldc.i4.7
0x46dd8  ldstr    aBcreatesystemc// "bCreateSystemCatalogs"
0x46ddd  stelem.ref
0x46dde  ldloc.s  0xB
0x46de0  ldc.i4.8
0x46de1  newarr   [mscorlib]System.Object
0x46de6  stloc.s  0xC
0x46de8  ldloc.s  0xC
0x46dea  ldc.i4.0
0x46deb  ldarg.1
0x46dec  stelem.ref
0x46ded  ldloc.s  0xC
0x46def  ldc.i4.1
0x46df0  ldarg.2
0x46df1  stelem.ref
0x46df2  ldloc.s  0xC
0x46df4  ldc.i4.2
0x46df5  ldarg.3
0x46df6  stelem.ref
0x46df7  ldloc.s  0xC
0x46df9  ldc.i4.3
0x46dfa  ldarg.s  4
0x46dfc  box      [mscorlib]System.UInt32
0x46e01  stelem.ref
0x46e02  ldloc.s  0xC
0x46e04  ldc.i4.4
0x46e05  ldarg.s  5
0x46e07  box      [mscorlib]System.Boolean
0x46e0c  stelem.ref
0x46e0d  ldloc.s  0xC
0x46e0f  ldc.i4.5
0x46e10  ldarg.s  7
0x46e12  stelem.ref
0x46e13  ldloc.s  0xC
0x46e15  ldc.i4.6
0x46e16  ldarg.s  8
0x46e18  box      [mscorlib]System.Boolean
0x46e1d  stelem.ref
0x46e1e  ldloc.s  0xC
0x46e20  ldc.i4.7
0x46e21  ldarg.s  0xB
0x46e23  box      [mscorlib]System.Boolean
0x46e28  stelem.ref
0x46e29  ldloc.s  0xC
  ... truncated ...
```
