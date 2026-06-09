# Microsoft.SharePoint.Library.SPRequest::UpdateFileOrFolderProperties

- ea: `0x3f260`
- end: `0x3f82c`
- name: `Microsoft.SharePoint.Library.SPRequest::UpdateFileOrFolderProperties`
- size: `1484`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x50ed70`
- `0x510ad0`
- `0x5270d0`
- `0x527160`

## callees

- `0x30b0`
- `0x3f260`
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

- `0x3f26c`: `SPRequest.UpdateFileOrFolderProperties`
- `0x3f2d8`: `UpdateFileOrFolderProperties`
- `0x3f3dc`: `UpdateFileOrFolderProperties`
- `0x3f4e1`: `UpdateFileOrFolderProperties`
- `0x3f5fd`: `UpdateFileOrFolderProperties`
- `0x3f70e`: `UpdateFileOrFolderProperties`
- `0x3f322`: `fSystemUpdate`
- `0x3f426`: `fSystemUpdate`
- `0x3f52b`: `fSystemUpdate`
- `0x3f647`: `fSystemUpdate`
- `0x3f758`: `fSystemUpdate`
- `0x3f32b`: `fUseIncomingLastModifiedTime`
- `0x3f42f`: `fUseIncomingLastModifiedTime`
- `0x3f534`: `fUseIncomingLastModifiedTime`
- `0x3f650`: `fUseIncomingLastModifiedTime`
- `0x3f761`: `fUseIncomingLastModifiedTime`
- `0x3f334`: `fUseIncomingCreatedTime`
- `0x3f438`: `fUseIncomingCreatedTime`
- `0x3f53d`: `fUseIncomingCreatedTime`
- `0x3f659`: `fUseIncomingCreatedTime`
- `0x3f76a`: `fUseIncomingCreatedTime`
- `0x3f351`: `fUpdateNoVersion`
- `0x3f455`: `fUpdateNoVersion`
- `0x3f55a`: `fUpdateNoVersion`
- `0x3f676`: `fUpdateNoVersion`
- `0x3f787`: `fUpdateNoVersion`

## pseudocode

```c

```

## disassembly

```asm
0x3f260  ldc.i4   0x66366C37
0x3f265  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x3f26a  ldc.i4.s 0x64
0x3f26c  ldstr    aSprequestUpdat_12// "SPRequest.UpdateFileOrFolderProperties"
0x3f271  ldc.i4.1
0x3f272  ldc.i4.2
0x3f273  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x3f278  stloc.s  5
0x3f27a  ldloc.s  5
0x3f27c  ldc.i4.0
0x3f27d  ldc.i4   0x96
0x3f282  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x3f287  stelem.ref
0x3f288  ldloc.s  5
0x3f28a  ldc.i4.1
0x3f28b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x3f290  stelem.ref
0x3f291  ldloc.s  5
0x3f293  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x3f298  stloc.s  6
0x3f29a  ldarg.0
0x3f29b  dup
0x3f29c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x3f2a1  ldc.i4.1
0x3f2a2  add
0x3f2a3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x3f2a8  ldarg.0
0x3f2a9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x3f2ae  ldarg.0
0x3f2af  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x3f2b4  ldarg.1
0x3f2b5  ldarg.2
0x3f2b6  ldarg.3
0x3f2b7  ldarg.s  4
0x3f2b9  ldarg.s  5
0x3f2bb  ldarg.s  6
0x3f2bd  ldarg.s  7
0x3f2bf  ldarg.s  8
0x3f2c1  ldarg.s  9
0x3f2c3  ldarg.s  0xA
0x3f2c5  ldarg.s  0xB
0x3f2c7  ldarg.s  0xC
0x3f2c9  ldarg.s  0xD
0x3f2cb  ldarg.s  0xE
0x3f2cd  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::UpdateFileOrFolderProperties(valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, string, object, bool, bool, bool, bool, bool, string, valuetype [mscorlib]System.Guid&, bool, string&, unsigned int8&)
0x3f2d2  leave    loc_3F80C
0x3f2d7  stloc.0
0x3f2d8  ldstr    aUpdatefileorfo// "UpdateFileOrFolderProperties"
0x3f2dd  ldarg.0
0x3f2de  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3f2e3  ldarg.0
0x3f2e4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x3f2e9  ldc.i4.s 0xB
0x3f2eb  newarr   [mscorlib]System.String
0x3f2f0  stloc.s  7
0x3f2f2  ldloc.s  7
0x3f2f4  ldc.i4.0
0x3f2f5  ldstr    aWeburl// "webUrl"
0x3f2fa  stelem.ref
0x3f2fb  ldloc.s  7
0x3f2fd  ldc.i4.1
0x3f2fe  ldstr    aWebrelativeurl// "webRelativeUrl"
0x3f303  stelem.ref
0x3f304  ldloc.s  7
0x3f306  ldc.i4.2
0x3f307  ldstr    aBstrchecklocki// "bstrCheckLockId"
0x3f30c  stelem.ref
0x3f30d  ldloc.s  7
0x3f30f  ldc.i4.3
0x3f310  ldstr    aVarproperties// "varProperties"
0x3f315  stelem.ref
0x3f316  ldloc.s  7
0x3f318  ldc.i4.4
0x3f319  ldstr    aFmigrationsema// "fMigrationSemantics"
0x3f31e  stelem.ref
0x3f31f  ldloc.s  7
0x3f321  ldc.i4.5
0x3f322  ldstr    aFsystemupdate// "fSystemUpdate"
0x3f327  stelem.ref
0x3f328  ldloc.s  7
0x3f32a  ldc.i4.6
0x3f32b  ldstr    aFuseincomingla// "fUseIncomingLastModifiedTime"
0x3f330  stelem.ref
0x3f331  ldloc.s  7
0x3f333  ldc.i4.7
0x3f334  ldstr    aFuseincomingcr// "fUseIncomingCreatedTime"
0x3f339  stelem.ref
0x3f33a  ldloc.s  7
0x3f33c  ldc.i4.8
0x3f33d  ldstr    aFincrementitem// "fIncrementItemVersion"
0x3f342  stelem.ref
0x3f343  ldloc.s  7
0x3f345  ldc.i4.s 9
0x3f347  ldstr    aEtagmatch// "etagMatch"
0x3f34c  stelem.ref
0x3f34d  ldloc.s  7
0x3f34f  ldc.i4.s 0xA
0x3f351  ldstr    aFupdatenoversi// "fUpdateNoVersion"
0x3f356  stelem.ref
0x3f357  ldloc.s  7
0x3f359  ldc.i4.s 0xB
0x3f35b  newarr   [mscorlib]System.Object
0x3f360  stloc.s  8
0x3f362  ldloc.s  8
0x3f364  ldc.i4.0
0x3f365  ldarg.1
0x3f366  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x3f36b  stelem.ref
0x3f36c  ldloc.s  8
0x3f36e  ldc.i4.1
0x3f36f  ldarg.2
0x3f370  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x3f375  stelem.ref
0x3f376  ldloc.s  8
0x3f378  ldc.i4.2
0x3f379  ldarg.3
0x3f37a  stelem.ref
0x3f37b  ldloc.s  8
0x3f37d  ldc.i4.3
0x3f37e  ldarg.s  4
0x3f380  stelem.ref
0x3f381  ldloc.s  8
0x3f383  ldc.i4.4
0x3f384  ldarg.s  5
0x3f386  box      [mscorlib]System.Boolean
0x3f38b  stelem.ref
0x3f38c  ldloc.s  8
0x3f38e  ldc.i4.5
0x3f38f  ldarg.s  6
0x3f391  box      [mscorlib]System.Boolean
0x3f396  stelem.ref
0x3f397  ldloc.s  8
0x3f399  ldc.i4.6
0x3f39a  ldarg.s  7
0x3f39c  box      [mscorlib]System.Boolean
0x3f3a1  stelem.ref
0x3f3a2  ldloc.s  8
0x3f3a4  ldc.i4.7
0x3f3a5  ldarg.s  8
0x3f3a7  box      [mscorlib]System.Boolean
0x3f3ac  stelem.ref
0x3f3ad  ldloc.s  8
0x3f3af  ldc.i4.8
0x3f3b0  ldarg.s  9
0x3f3b2  box      [mscorlib]System.Boolean
0x3f3b7  stelem.ref
0x3f3b8  ldloc.s  8
0x3f3ba  ldc.i4.s 9
0x3f3bc  ldarg.s  0xA
0x3f3be  stelem.ref
0x3f3bf  ldloc.s  8
0x3f3c1  ldc.i4.s 0xA
0x3f3c3  ldarg.s  0xC
0x3f3c5  box      [mscorlib]System.Boolean
0x3f3ca  stelem.ref
0x3f3cb  ldloc.s  8
0x3f3cd  ldloc.0
0x3f3ce  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x3f3d3  ldloc.0
0x3f3d4  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x3f3d9  rethrow
0x3f3db  stloc.1
0x3f3dc  ldstr    aUpdatefileorfo// "UpdateFileOrFolderProperties"
0x3f3e1  ldarg.0
0x3f3e2  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3f3e7  ldarg.0
0x3f3e8  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x3f3ed  ldc.i4.s 0xB
0x3f3ef  newarr   [mscorlib]System.String
0x3f3f4  stloc.s  9
0x3f3f6  ldloc.s  9
0x3f3f8  ldc.i4.0
0x3f3f9  ldstr    aWeburl// "webUrl"
0x3f3fe  stelem.ref
0x3f3ff  ldloc.s  9
0x3f401  ldc.i4.1
0x3f402  ldstr    aWebrelativeurl// "webRelativeUrl"
0x3f407  stelem.ref
0x3f408  ldloc.s  9
0x3f40a  ldc.i4.2
0x3f40b  ldstr    aBstrchecklocki// "bstrCheckLockId"
0x3f410  stelem.ref
0x3f411  ldloc.s  9
0x3f413  ldc.i4.3
0x3f414  ldstr    aVarproperties// "varProperties"
0x3f419  stelem.ref
0x3f41a  ldloc.s  9
0x3f41c  ldc.i4.4
0x3f41d  ldstr    aFmigrationsema// "fMigrationSemantics"
0x3f422  stelem.ref
0x3f423  ldloc.s  9
0x3f425  ldc.i4.5
0x3f426  ldstr    aFsystemupdate// "fSystemUpdate"
0x3f42b  stelem.ref
0x3f42c  ldloc.s  9
0x3f42e  ldc.i4.6
0x3f42f  ldstr    aFuseincomingla// "fUseIncomingLastModifiedTime"
0x3f434  stelem.ref
0x3f435  ldloc.s  9
0x3f437  ldc.i4.7
0x3f438  ldstr    aFuseincomingcr// "fUseIncomingCreatedTime"
0x3f43d  stelem.ref
0x3f43e  ldloc.s  9
0x3f440  ldc.i4.8
0x3f441  ldstr    aFincrementitem// "fIncrementItemVersion"
0x3f446  stelem.ref
0x3f447  ldloc.s  9
0x3f449  ldc.i4.s 9
0x3f44b  ldstr    aEtagmatch// "etagMatch"
0x3f450  stelem.ref
0x3f451  ldloc.s  9
0x3f453  ldc.i4.s 0xA
0x3f455  ldstr    aFupdatenoversi// "fUpdateNoVersion"
0x3f45a  stelem.ref
0x3f45b  ldloc.s  9
0x3f45d  ldc.i4.s 0xB
0x3f45f  newarr   [mscorlib]System.Object
0x3f464  stloc.s  0xA
0x3f466  ldloc.s  0xA
0x3f468  ldc.i4.0
0x3f469  ldarg.1
0x3f46a  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x3f46f  stelem.ref
0x3f470  ldloc.s  0xA
0x3f472  ldc.i4.1
0x3f473  ldarg.2
0x3f474  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath
0x3f479  stelem.ref
0x3f47a  ldloc.s  0xA
0x3f47c  ldc.i4.2
0x3f47d  ldarg.3
0x3f47e  stelem.ref
0x3f47f  ldloc.s  0xA
0x3f481  ldc.i4.3
0x3f482  ldarg.s  4
0x3f484  stelem.ref
0x3f485  ldloc.s  0xA
0x3f487  ldc.i4.4
0x3f488  ldarg.s  5
0x3f48a  box      [mscorlib]System.Boolean
0x3f48f  stelem.ref
0x3f490  ldloc.s  0xA
0x3f492  ldc.i4.5
0x3f493  ldarg.s  6
0x3f495  box      [mscorlib]System.Boolean
0x3f49a  stelem.ref
0x3f49b  ldloc.s  0xA
0x3f49d  ldc.i4.6
0x3f49e  ldarg.s  7
0x3f4a0  box      [mscorlib]System.Boolean
0x3f4a5  stelem.ref
0x3f4a6  ldloc.s  0xA
0x3f4a8  ldc.i4.7
0x3f4a9  ldarg.s  8
0x3f4ab  box      [mscorlib]System.Boolean
0x3f4b0  stelem.ref
0x3f4b1  ldloc.s  0xA
0x3f4b3  ldc.i4.8
0x3f4b4  ldarg.s  9
0x3f4b6  box      [mscorlib]System.Boolean
0x3f4bb  stelem.ref
0x3f4bc  ldloc.s  0xA
0x3f4be  ldc.i4.s 9
0x3f4c0  ldarg.s  0xA
0x3f4c2  stelem.ref
0x3f4c3  ldloc.s  0xA
0x3f4c5  ldc.i4.s 0xA
0x3f4c7  ldarg.s  0xC
0x3f4c9  box      [mscorlib]System.Boolean
0x3f4ce  stelem.ref
0x3f4cf  ldloc.s  0xA
0x3f4d1  ldloc.1
0x3f4d2  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x3f4d7  ldloc.1
0x3f4d8  ldc.i4.0
0x3f4d9  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x3f4de  rethrow
0x3f4e0  stloc.2
0x3f4e1  ldstr    aUpdatefileorfo// "UpdateFileOrFolderProperties"
0x3f4e6  ldarg.0
0x3f4e7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3f4ec  ldarg.0
0x3f4ed  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x3f4f2  ldc.i4.s 0xB
0x3f4f4  newarr   [mscorlib]System.String
0x3f4f9  stloc.s  0xB
0x3f4fb  ldloc.s  0xB
0x3f4fd  ldc.i4.0
0x3f4fe  ldstr    aWeburl// "webUrl"
0x3f503  stelem.ref
0x3f504  ldloc.s  0xB
0x3f506  ldc.i4.1
0x3f507  ldstr    aWebrelativeurl// "webRelativeUrl"
0x3f50c  stelem.ref
0x3f50d  ldloc.s  0xB
0x3f50f  ldc.i4.2
0x3f510  ldstr    aBstrchecklocki// "bstrCheckLockId"
0x3f515  stelem.ref
0x3f516  ldloc.s  0xB
0x3f518  ldc.i4.3
  ... truncated ...
```
