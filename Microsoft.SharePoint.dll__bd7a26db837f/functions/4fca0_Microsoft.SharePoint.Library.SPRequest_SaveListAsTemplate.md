# Microsoft.SharePoint.Library.SPRequest::SaveListAsTemplate

- ea: `0x4fca0`
- end: `0x50018`
- name: `Microsoft.SharePoint.Library.SPRequest::SaveListAsTemplate`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x3531d0`

## callees

- `0x30b0`
- `0x4fca0`
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

- `0x4fd36`: `bstrTemplateName`
- `0x4fdc6`: `bstrTemplateName`
- `0x4fe57`: `bstrTemplateName`
- `0x4feff`: `bstrTemplateName`
- `0x4ff9c`: `bstrTemplateName`
- `0x4fd3f`: `bstrTemplateTitle`
- `0x4fdcf`: `bstrTemplateTitle`
- `0x4fe60`: `bstrTemplateTitle`
- `0x4ff08`: `bstrTemplateTitle`
- `0x4ffa5`: `bstrTemplateTitle`
- `0x4fcac`: `SPRequest.SaveListAsTemplate`
- `0x4fd08`: `SaveListAsTemplate`
- `0x4fd98`: `SaveListAsTemplate`
- `0x4fe29`: `SaveListAsTemplate`
- `0x4fed1`: `SaveListAsTemplate`
- `0x4ff6e`: `SaveListAsTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x4fca0  ldc.i4   0x66366C37
0x4fca5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4fcaa  ldc.i4.s 0x64
0x4fcac  ldstr    aSprequestSavel// "SPRequest.SaveListAsTemplate"
0x4fcb1  ldc.i4.1
0x4fcb2  ldc.i4.2
0x4fcb3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x4fcb8  stloc.s  5
0x4fcba  ldloc.s  5
0x4fcbc  ldc.i4.0
0x4fcbd  ldc.i4   0x96
0x4fcc2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x4fcc7  stelem.ref
0x4fcc8  ldloc.s  5
0x4fcca  ldc.i4.1
0x4fccb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x4fcd0  stelem.ref
0x4fcd1  ldloc.s  5
0x4fcd3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x4fcd8  stloc.s  6
0x4fcda  ldarg.0
0x4fcdb  dup
0x4fcdc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4fce1  ldc.i4.1
0x4fce2  add
0x4fce3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4fce8  ldarg.0
0x4fce9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x4fcee  ldarg.0
0x4fcef  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x4fcf4  ldarg.1
0x4fcf5  ldarg.2
0x4fcf6  ldarg.3
0x4fcf7  ldarg.s  4
0x4fcf9  ldarg.s  5
0x4fcfb  ldarg.s  6
0x4fcfd  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::SaveListAsTemplate(string, string, string, string, string, bool)
0x4fd02  leave    loc_4FFF8
0x4fd07  stloc.0
0x4fd08  ldstr    aSavelistastemp// "SaveListAsTemplate"
0x4fd0d  ldarg.0
0x4fd0e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4fd13  ldarg.0
0x4fd14  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4fd19  ldc.i4.6
0x4fd1a  newarr   [mscorlib]System.String
0x4fd1f  stloc.s  7
0x4fd21  ldloc.s  7
0x4fd23  ldc.i4.0
0x4fd24  ldstr    aBstrurl// "bstrUrl"
0x4fd29  stelem.ref
0x4fd2a  ldloc.s  7
0x4fd2c  ldc.i4.1
0x4fd2d  ldstr    aBstrlistname// "bstrListName"
0x4fd32  stelem.ref
0x4fd33  ldloc.s  7
0x4fd35  ldc.i4.2
0x4fd36  ldstr    aBstrtemplatena// "bstrTemplateName"
0x4fd3b  stelem.ref
0x4fd3c  ldloc.s  7
0x4fd3e  ldc.i4.3
0x4fd3f  ldstr    aBstrtemplateti// "bstrTemplateTitle"
0x4fd44  stelem.ref
0x4fd45  ldloc.s  7
0x4fd47  ldc.i4.4
0x4fd48  ldstr    aBstrdescriptio// "bstrDescription"
0x4fd4d  stelem.ref
0x4fd4e  ldloc.s  7
0x4fd50  ldc.i4.5
0x4fd51  ldstr    aBsavedata// "bSaveData"
0x4fd56  stelem.ref
0x4fd57  ldloc.s  7
0x4fd59  ldc.i4.6
0x4fd5a  newarr   [mscorlib]System.Object
0x4fd5f  stloc.s  8
0x4fd61  ldloc.s  8
0x4fd63  ldc.i4.0
0x4fd64  ldarg.1
0x4fd65  stelem.ref
0x4fd66  ldloc.s  8
0x4fd68  ldc.i4.1
0x4fd69  ldarg.2
0x4fd6a  stelem.ref
0x4fd6b  ldloc.s  8
0x4fd6d  ldc.i4.2
0x4fd6e  ldarg.3
0x4fd6f  stelem.ref
0x4fd70  ldloc.s  8
0x4fd72  ldc.i4.3
0x4fd73  ldarg.s  4
0x4fd75  stelem.ref
0x4fd76  ldloc.s  8
0x4fd78  ldc.i4.4
0x4fd79  ldarg.s  5
0x4fd7b  stelem.ref
0x4fd7c  ldloc.s  8
0x4fd7e  ldc.i4.5
0x4fd7f  ldarg.s  6
0x4fd81  box      [mscorlib]System.Boolean
0x4fd86  stelem.ref
0x4fd87  ldloc.s  8
0x4fd89  ldloc.0
0x4fd8a  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4fd8f  ldloc.0
0x4fd90  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x4fd95  rethrow
0x4fd97  stloc.1
0x4fd98  ldstr    aSavelistastemp// "SaveListAsTemplate"
0x4fd9d  ldarg.0
0x4fd9e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4fda3  ldarg.0
0x4fda4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4fda9  ldc.i4.6
0x4fdaa  newarr   [mscorlib]System.String
0x4fdaf  stloc.s  9
0x4fdb1  ldloc.s  9
0x4fdb3  ldc.i4.0
0x4fdb4  ldstr    aBstrurl// "bstrUrl"
0x4fdb9  stelem.ref
0x4fdba  ldloc.s  9
0x4fdbc  ldc.i4.1
0x4fdbd  ldstr    aBstrlistname// "bstrListName"
0x4fdc2  stelem.ref
0x4fdc3  ldloc.s  9
0x4fdc5  ldc.i4.2
0x4fdc6  ldstr    aBstrtemplatena// "bstrTemplateName"
0x4fdcb  stelem.ref
0x4fdcc  ldloc.s  9
0x4fdce  ldc.i4.3
0x4fdcf  ldstr    aBstrtemplateti// "bstrTemplateTitle"
0x4fdd4  stelem.ref
0x4fdd5  ldloc.s  9
0x4fdd7  ldc.i4.4
0x4fdd8  ldstr    aBstrdescriptio// "bstrDescription"
0x4fddd  stelem.ref
0x4fdde  ldloc.s  9
0x4fde0  ldc.i4.5
0x4fde1  ldstr    aBsavedata// "bSaveData"
0x4fde6  stelem.ref
0x4fde7  ldloc.s  9
0x4fde9  ldc.i4.6
0x4fdea  newarr   [mscorlib]System.Object
0x4fdef  stloc.s  0xA
0x4fdf1  ldloc.s  0xA
0x4fdf3  ldc.i4.0
0x4fdf4  ldarg.1
0x4fdf5  stelem.ref
0x4fdf6  ldloc.s  0xA
0x4fdf8  ldc.i4.1
0x4fdf9  ldarg.2
0x4fdfa  stelem.ref
0x4fdfb  ldloc.s  0xA
0x4fdfd  ldc.i4.2
0x4fdfe  ldarg.3
0x4fdff  stelem.ref
0x4fe00  ldloc.s  0xA
0x4fe02  ldc.i4.3
0x4fe03  ldarg.s  4
0x4fe05  stelem.ref
0x4fe06  ldloc.s  0xA
0x4fe08  ldc.i4.4
0x4fe09  ldarg.s  5
0x4fe0b  stelem.ref
0x4fe0c  ldloc.s  0xA
0x4fe0e  ldc.i4.5
0x4fe0f  ldarg.s  6
0x4fe11  box      [mscorlib]System.Boolean
0x4fe16  stelem.ref
0x4fe17  ldloc.s  0xA
0x4fe19  ldloc.1
0x4fe1a  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4fe1f  ldloc.1
0x4fe20  ldc.i4.0
0x4fe21  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x4fe26  rethrow
0x4fe28  stloc.2
0x4fe29  ldstr    aSavelistastemp// "SaveListAsTemplate"
0x4fe2e  ldarg.0
0x4fe2f  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4fe34  ldarg.0
0x4fe35  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4fe3a  ldc.i4.6
0x4fe3b  newarr   [mscorlib]System.String
0x4fe40  stloc.s  0xB
0x4fe42  ldloc.s  0xB
0x4fe44  ldc.i4.0
0x4fe45  ldstr    aBstrurl// "bstrUrl"
0x4fe4a  stelem.ref
0x4fe4b  ldloc.s  0xB
0x4fe4d  ldc.i4.1
0x4fe4e  ldstr    aBstrlistname// "bstrListName"
0x4fe53  stelem.ref
0x4fe54  ldloc.s  0xB
0x4fe56  ldc.i4.2
0x4fe57  ldstr    aBstrtemplatena// "bstrTemplateName"
0x4fe5c  stelem.ref
0x4fe5d  ldloc.s  0xB
0x4fe5f  ldc.i4.3
0x4fe60  ldstr    aBstrtemplateti// "bstrTemplateTitle"
0x4fe65  stelem.ref
0x4fe66  ldloc.s  0xB
0x4fe68  ldc.i4.4
0x4fe69  ldstr    aBstrdescriptio// "bstrDescription"
0x4fe6e  stelem.ref
0x4fe6f  ldloc.s  0xB
0x4fe71  ldc.i4.5
0x4fe72  ldstr    aBsavedata// "bSaveData"
0x4fe77  stelem.ref
0x4fe78  ldloc.s  0xB
0x4fe7a  ldc.i4.6
0x4fe7b  newarr   [mscorlib]System.Object
0x4fe80  stloc.s  0xC
0x4fe82  ldloc.s  0xC
0x4fe84  ldc.i4.0
0x4fe85  ldarg.1
0x4fe86  stelem.ref
0x4fe87  ldloc.s  0xC
0x4fe89  ldc.i4.1
0x4fe8a  ldarg.2
0x4fe8b  stelem.ref
0x4fe8c  ldloc.s  0xC
0x4fe8e  ldc.i4.2
0x4fe8f  ldarg.3
0x4fe90  stelem.ref
0x4fe91  ldloc.s  0xC
0x4fe93  ldc.i4.3
0x4fe94  ldarg.s  4
0x4fe96  stelem.ref
0x4fe97  ldloc.s  0xC
0x4fe99  ldc.i4.4
0x4fe9a  ldarg.s  5
0x4fe9c  stelem.ref
0x4fe9d  ldloc.s  0xC
0x4fe9f  ldc.i4.5
0x4fea0  ldarg.s  6
0x4fea2  box      [mscorlib]System.Boolean
0x4fea7  stelem.ref
0x4fea8  ldloc.s  0xC
0x4feaa  ldloc.2
0x4feab  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4feb0  ldloc.2
0x4feb1  ldarg.0
0x4feb2  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x4feb7  ldarg.0
0x4feb8  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x4febd  ldarg.0
0x4febe  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x4fec3  ldarg.0
0x4fec4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x4fec9  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x4fece  rethrow
0x4fed0  stloc.3
0x4fed1  ldstr    aSavelistastemp// "SaveListAsTemplate"
0x4fed6  ldarg.0
0x4fed7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4fedc  ldarg.0
0x4fedd  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4fee2  ldc.i4.6
0x4fee3  newarr   [mscorlib]System.String
0x4fee8  stloc.s  0xD
0x4feea  ldloc.s  0xD
0x4feec  ldc.i4.0
0x4feed  ldstr    aBstrurl// "bstrUrl"
0x4fef2  stelem.ref
0x4fef3  ldloc.s  0xD
0x4fef5  ldc.i4.1
0x4fef6  ldstr    aBstrlistname// "bstrListName"
0x4fefb  stelem.ref
0x4fefc  ldloc.s  0xD
0x4fefe  ldc.i4.2
0x4feff  ldstr    aBstrtemplatena// "bstrTemplateName"
0x4ff04  stelem.ref
0x4ff05  ldloc.s  0xD
0x4ff07  ldc.i4.3
0x4ff08  ldstr    aBstrtemplateti// "bstrTemplateTitle"
0x4ff0d  stelem.ref
0x4ff0e  ldloc.s  0xD
0x4ff10  ldc.i4.4
0x4ff11  ldstr    aBstrdescriptio// "bstrDescription"
0x4ff16  stelem.ref
0x4ff17  ldloc.s  0xD
0x4ff19  ldc.i4.5
0x4ff1a  ldstr    aBsavedata// "bSaveData"
0x4ff1f  stelem.ref
0x4ff20  ldloc.s  0xD
0x4ff22  ldc.i4.6
0x4ff23  newarr   [mscorlib]System.Object
0x4ff28  stloc.s  0xE
0x4ff2a  ldloc.s  0xE
0x4ff2c  ldc.i4.0
0x4ff2d  ldarg.1
0x4ff2e  stelem.ref
0x4ff2f  ldloc.s  0xE
0x4ff31  ldc.i4.1
0x4ff32  ldarg.2
0x4ff33  stelem.ref
0x4ff34  ldloc.s  0xE
0x4ff36  ldc.i4.2
0x4ff37  ldarg.3
0x4ff38  stelem.ref
  ... truncated ...
```
