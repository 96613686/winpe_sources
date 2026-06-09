# Microsoft.SharePoint.Library.SPRequest::MoveUrl

- ea: `0x40d90`
- end: `0x41157`
- name: `Microsoft.SharePoint.Library.SPRequest::MoveUrl`
- size: `967`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x50f070`
- `0x527520`

## callees

- `0x30b0`
- `0x40d90`
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

- `0x40d9c`: `SPRequest.MoveUrl`
- `0x40dfc`: `MoveUrl`
- `0x40e9b`: `MoveUrl`
- `0x40f3b`: `MoveUrl`
- `0x40ff2`: `MoveUrl`
- `0x4109e`: `MoveUrl`
- `0x40e33`: `moveFlags`
- `0x40ed2`: `moveFlags`
- `0x40f72`: `moveFlags`
- `0x41029`: `moveFlags`
- `0x410d5`: `moveFlags`
- `0x40e45`: `fAllowNoExecuteWebFileUpdate`
- `0x40ee4`: `fAllowNoExecuteWebFileUpdate`
- `0x40f84`: `fAllowNoExecuteWebFileUpdate`
- `0x4103b`: `fAllowNoExecuteWebFileUpdate`
- `0x410e7`: `fAllowNoExecuteWebFileUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x40d90  ldc.i4   0x66366C37
0x40d95  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x40d9a  ldc.i4.s 0x64
0x40d9c  ldstr    aSprequestMoveu// "SPRequest.MoveUrl"
0x40da1  ldc.i4.1
0x40da2  ldc.i4.2
0x40da3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x40da8  stloc.s  5
0x40daa  ldloc.s  5
0x40dac  ldc.i4.0
0x40dad  ldc.i4   0x96
0x40db2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x40db7  stelem.ref
0x40db8  ldloc.s  5
0x40dba  ldc.i4.1
0x40dbb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x40dc0  stelem.ref
0x40dc1  ldloc.s  5
0x40dc3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x40dc8  stloc.s  6
0x40dca  ldarg.0
0x40dcb  dup
0x40dcc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x40dd1  ldc.i4.1
0x40dd2  add
0x40dd3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x40dd8  ldarg.0
0x40dd9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x40dde  ldarg.0
0x40ddf  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x40de4  ldarg.1
0x40de5  ldarg.2
0x40de6  ldarg.3
0x40de7  ldarg.s  4
0x40de9  ldarg.s  5
0x40deb  ldarg.s  6
0x40ded  ldarg.s  7
0x40def  ldarg.s  8
0x40df1  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::MoveUrl(string, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.MoveUrlFlags, string, valuetype [mscorlib]System.Guid&, string&, bool)
0x40df6  leave    loc_41137
0x40dfb  stloc.0
0x40dfc  ldstr    aMoveurl// "MoveUrl"
0x40e01  ldarg.0
0x40e02  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x40e07  ldarg.0
0x40e08  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x40e0d  ldc.i4.6
0x40e0e  newarr   [mscorlib]System.String
0x40e13  stloc.s  7
0x40e15  ldloc.s  7
0x40e17  ldc.i4.0
0x40e18  ldstr    aBstrurl// "bstrUrl"
0x40e1d  stelem.ref
0x40e1e  ldloc.s  7
0x40e20  ldc.i4.1
0x40e21  ldstr    aBstrwebreloldu// "bstrWebRelOldUrl"
0x40e26  stelem.ref
0x40e27  ldloc.s  7
0x40e29  ldc.i4.2
0x40e2a  ldstr    aBstrwebrelnewu// "bstrWebRelNewUrl"
0x40e2f  stelem.ref
0x40e30  ldloc.s  7
0x40e32  ldc.i4.3
0x40e33  ldstr    aMoveflags// "moveFlags"
0x40e38  stelem.ref
0x40e39  ldloc.s  7
0x40e3b  ldc.i4.4
0x40e3c  ldstr    aEtagmatch// "etagMatch"
0x40e41  stelem.ref
0x40e42  ldloc.s  7
0x40e44  ldc.i4.5
0x40e45  ldstr    aFallownoexecut// "fAllowNoExecuteWebFileUpdate"
0x40e4a  stelem.ref
0x40e4b  ldloc.s  7
0x40e4d  ldc.i4.6
0x40e4e  newarr   [mscorlib]System.Object
0x40e53  stloc.s  8
0x40e55  ldloc.s  8
0x40e57  ldc.i4.0
0x40e58  ldarg.1
0x40e59  stelem.ref
0x40e5a  ldloc.s  8
0x40e5c  ldc.i4.1
0x40e5d  ldarg.2
0x40e5e  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x40e63  stelem.ref
0x40e64  ldloc.s  8
0x40e66  ldc.i4.2
0x40e67  ldarg.3
0x40e68  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x40e6d  stelem.ref
0x40e6e  ldloc.s  8
0x40e70  ldc.i4.3
0x40e71  ldarg.s  4
0x40e73  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.MoveUrlFlags
0x40e78  stelem.ref
0x40e79  ldloc.s  8
0x40e7b  ldc.i4.4
0x40e7c  ldarg.s  5
0x40e7e  stelem.ref
0x40e7f  ldloc.s  8
0x40e81  ldc.i4.5
0x40e82  ldarg.s  8
0x40e84  box      [mscorlib]System.Boolean
0x40e89  stelem.ref
0x40e8a  ldloc.s  8
0x40e8c  ldloc.0
0x40e8d  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x40e92  ldloc.0
0x40e93  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x40e98  rethrow
0x40e9a  stloc.1
0x40e9b  ldstr    aMoveurl// "MoveUrl"
0x40ea0  ldarg.0
0x40ea1  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x40ea6  ldarg.0
0x40ea7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x40eac  ldc.i4.6
0x40ead  newarr   [mscorlib]System.String
0x40eb2  stloc.s  9
0x40eb4  ldloc.s  9
0x40eb6  ldc.i4.0
0x40eb7  ldstr    aBstrurl// "bstrUrl"
0x40ebc  stelem.ref
0x40ebd  ldloc.s  9
0x40ebf  ldc.i4.1
0x40ec0  ldstr    aBstrwebreloldu// "bstrWebRelOldUrl"
0x40ec5  stelem.ref
0x40ec6  ldloc.s  9
0x40ec8  ldc.i4.2
0x40ec9  ldstr    aBstrwebrelnewu// "bstrWebRelNewUrl"
0x40ece  stelem.ref
0x40ecf  ldloc.s  9
0x40ed1  ldc.i4.3
0x40ed2  ldstr    aMoveflags// "moveFlags"
0x40ed7  stelem.ref
0x40ed8  ldloc.s  9
0x40eda  ldc.i4.4
0x40edb  ldstr    aEtagmatch// "etagMatch"
0x40ee0  stelem.ref
0x40ee1  ldloc.s  9
0x40ee3  ldc.i4.5
0x40ee4  ldstr    aFallownoexecut// "fAllowNoExecuteWebFileUpdate"
0x40ee9  stelem.ref
0x40eea  ldloc.s  9
0x40eec  ldc.i4.6
0x40eed  newarr   [mscorlib]System.Object
0x40ef2  stloc.s  0xA
0x40ef4  ldloc.s  0xA
0x40ef6  ldc.i4.0
0x40ef7  ldarg.1
0x40ef8  stelem.ref
0x40ef9  ldloc.s  0xA
0x40efb  ldc.i4.1
0x40efc  ldarg.2
0x40efd  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x40f02  stelem.ref
0x40f03  ldloc.s  0xA
0x40f05  ldc.i4.2
0x40f06  ldarg.3
0x40f07  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x40f0c  stelem.ref
0x40f0d  ldloc.s  0xA
0x40f0f  ldc.i4.3
0x40f10  ldarg.s  4
0x40f12  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.MoveUrlFlags
0x40f17  stelem.ref
0x40f18  ldloc.s  0xA
0x40f1a  ldc.i4.4
0x40f1b  ldarg.s  5
0x40f1d  stelem.ref
0x40f1e  ldloc.s  0xA
0x40f20  ldc.i4.5
0x40f21  ldarg.s  8
0x40f23  box      [mscorlib]System.Boolean
0x40f28  stelem.ref
0x40f29  ldloc.s  0xA
0x40f2b  ldloc.1
0x40f2c  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x40f31  ldloc.1
0x40f32  ldc.i4.0
0x40f33  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x40f38  rethrow
0x40f3a  stloc.2
0x40f3b  ldstr    aMoveurl// "MoveUrl"
0x40f40  ldarg.0
0x40f41  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x40f46  ldarg.0
0x40f47  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x40f4c  ldc.i4.6
0x40f4d  newarr   [mscorlib]System.String
0x40f52  stloc.s  0xB
0x40f54  ldloc.s  0xB
0x40f56  ldc.i4.0
0x40f57  ldstr    aBstrurl// "bstrUrl"
0x40f5c  stelem.ref
0x40f5d  ldloc.s  0xB
0x40f5f  ldc.i4.1
0x40f60  ldstr    aBstrwebreloldu// "bstrWebRelOldUrl"
0x40f65  stelem.ref
0x40f66  ldloc.s  0xB
0x40f68  ldc.i4.2
0x40f69  ldstr    aBstrwebrelnewu// "bstrWebRelNewUrl"
0x40f6e  stelem.ref
0x40f6f  ldloc.s  0xB
0x40f71  ldc.i4.3
0x40f72  ldstr    aMoveflags// "moveFlags"
0x40f77  stelem.ref
0x40f78  ldloc.s  0xB
0x40f7a  ldc.i4.4
0x40f7b  ldstr    aEtagmatch// "etagMatch"
0x40f80  stelem.ref
0x40f81  ldloc.s  0xB
0x40f83  ldc.i4.5
0x40f84  ldstr    aFallownoexecut// "fAllowNoExecuteWebFileUpdate"
0x40f89  stelem.ref
0x40f8a  ldloc.s  0xB
0x40f8c  ldc.i4.6
0x40f8d  newarr   [mscorlib]System.Object
0x40f92  stloc.s  0xC
0x40f94  ldloc.s  0xC
0x40f96  ldc.i4.0
0x40f97  ldarg.1
0x40f98  stelem.ref
0x40f99  ldloc.s  0xC
0x40f9b  ldc.i4.1
0x40f9c  ldarg.2
0x40f9d  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x40fa2  stelem.ref
0x40fa3  ldloc.s  0xC
0x40fa5  ldc.i4.2
0x40fa6  ldarg.3
0x40fa7  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x40fac  stelem.ref
0x40fad  ldloc.s  0xC
0x40faf  ldc.i4.3
0x40fb0  ldarg.s  4
0x40fb2  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.MoveUrlFlags
0x40fb7  stelem.ref
0x40fb8  ldloc.s  0xC
0x40fba  ldc.i4.4
0x40fbb  ldarg.s  5
0x40fbd  stelem.ref
0x40fbe  ldloc.s  0xC
0x40fc0  ldc.i4.5
0x40fc1  ldarg.s  8
0x40fc3  box      [mscorlib]System.Boolean
0x40fc8  stelem.ref
0x40fc9  ldloc.s  0xC
0x40fcb  ldloc.2
0x40fcc  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x40fd1  ldloc.2
0x40fd2  ldarg.0
0x40fd3  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x40fd8  ldarg.0
0x40fd9  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x40fde  ldarg.0
0x40fdf  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x40fe4  ldarg.0
0x40fe5  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x40fea  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x40fef  rethrow
0x40ff1  stloc.3
0x40ff2  ldstr    aMoveurl// "MoveUrl"
0x40ff7  ldarg.0
0x40ff8  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x40ffd  ldarg.0
0x40ffe  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x41003  ldc.i4.6
0x41004  newarr   [mscorlib]System.String
0x41009  stloc.s  0xD
0x4100b  ldloc.s  0xD
0x4100d  ldc.i4.0
0x4100e  ldstr    aBstrurl// "bstrUrl"
0x41013  stelem.ref
0x41014  ldloc.s  0xD
0x41016  ldc.i4.1
0x41017  ldstr    aBstrwebreloldu// "bstrWebRelOldUrl"
0x4101c  stelem.ref
0x4101d  ldloc.s  0xD
0x4101f  ldc.i4.2
0x41020  ldstr    aBstrwebrelnewu// "bstrWebRelNewUrl"
0x41025  stelem.ref
0x41026  ldloc.s  0xD
0x41028  ldc.i4.3
0x41029  ldstr    aMoveflags// "moveFlags"
0x4102e  stelem.ref
0x4102f  ldloc.s  0xD
0x41031  ldc.i4.4
0x41032  ldstr    aEtagmatch// "etagMatch"
0x41037  stelem.ref
0x41038  ldloc.s  0xD
0x4103a  ldc.i4.5
0x4103b  ldstr    aFallownoexecut// "fAllowNoExecuteWebFileUpdate"
0x41040  stelem.ref
0x41041  ldloc.s  0xD
0x41043  ldc.i4.6
0x41044  newarr   [mscorlib]System.Object
0x41049  stloc.s  0xE
0x4104b  ldloc.s  0xE
  ... truncated ...
```
