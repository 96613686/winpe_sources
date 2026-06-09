# Microsoft.SharePoint.Library.SPRequest::LocalizeXml

- ea: `0x1aa10`
- end: `0x1adf5`
- name: `Microsoft.SharePoint.Library.SPRequest::LocalizeXml`
- size: `997`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2eb020`
- `0x301b70`
- `0x5e4920`

## callees

- `0x30b0`
- `0x1aa10`
- `0x4727e0`
- `0x472800`
- `0x4729d0`
- `0x472c90`
- `0x472d60`

## string_xrefs

- `0x1aa44`: `LocalizeXml`
- `0x1aaf7`: `LocalizeXml`
- `0x1abab`: `LocalizeXml`
- `0x1ac76`: `LocalizeXml`
- `0x1ad36`: `LocalizeXml`
- `0x1aa60`: `bstrXmlPath`
- `0x1ab13`: `bstrXmlPath`
- `0x1abc7`: `bstrXmlPath`
- `0x1ac92`: `bstrXmlPath`
- `0x1ad52`: `bstrXmlPath`
- `0x1aa84`: `compatibilityLevel`
- `0x1ab37`: `compatibilityLevel`
- `0x1abeb`: `compatibilityLevel`
- `0x1acb6`: `compatibilityLevel`
- `0x1ad76`: `compatibilityLevel`

## pseudocode

```c

```

## disassembly

```asm
0x1aa10  ldarg.0
0x1aa11  dup
0x1aa12  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x1aa17  ldc.i4.1
0x1aa18  add
0x1aa19  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x1aa1e  ldarg.0
0x1aa1f  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x1aa24  ldarg.0
0x1aa25  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x1aa2a  ldarg.1
0x1aa2b  ldarg.2
0x1aa2c  ldarg.3
0x1aa2d  ldarg.s  4
0x1aa2f  ldarg.s  5
0x1aa31  ldarg.s  6
0x1aa33  ldarg.s  7
0x1aa35  ldarg.s  8
0x1aa37  callvirt instance string [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::LocalizeXml(string, string, string, unsigned int32, int32, string, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISPEnableModuleCallback, string)
0x1aa3c  stloc.s  5
0x1aa3e  leave    loc_1ADF2
0x1aa43  stloc.0
0x1aa44  ldstr    aLocalizexml// "LocalizeXml"
0x1aa49  ldarg.0
0x1aa4a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1aa4f  ldarg.0
0x1aa50  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x1aa55  ldc.i4.8
0x1aa56  newarr   [mscorlib]System.String
0x1aa5b  stloc.s  6
0x1aa5d  ldloc.s  6
0x1aa5f  ldc.i4.0
0x1aa60  ldstr    aBstrxmlpath// "bstrXmlPath"
0x1aa65  stelem.ref
0x1aa66  ldloc.s  6
0x1aa68  ldc.i4.1
0x1aa69  ldstr    aBstrfeaturedef// "bstrFeatureDefinitionId"
0x1aa6e  stelem.ref
0x1aa6f  ldloc.s  6
0x1aa71  ldc.i4.2
0x1aa72  ldstr    aBstrfeatureroo// "bstrFeatureRoot"
0x1aa77  stelem.ref
0x1aa78  ldloc.s  6
0x1aa7a  ldc.i4.3
0x1aa7b  ldstr    aLcid// "lcid"
0x1aa80  stelem.ref
0x1aa81  ldloc.s  6
0x1aa83  ldc.i4.4
0x1aa84  ldstr    aCompatibilityl// "compatibilityLevel"
0x1aa89  stelem.ref
0x1aa8a  ldloc.s  6
0x1aa8c  ldc.i4.5
0x1aa8d  ldstr    aBstrdefaultres// "bstrDefaultResourceFile"
0x1aa92  stelem.ref
0x1aa93  ldloc.s  6
0x1aa95  ldc.i4.6
0x1aa96  ldstr    aPenablemodulec// "pEnableModuleCallback"
0x1aa9b  stelem.ref
0x1aa9c  ldloc.s  6
0x1aa9e  ldc.i4.7
0x1aa9f  ldstr    aBstrsolutionin// "bstrSolutionInfo"
0x1aaa4  stelem.ref
0x1aaa5  ldloc.s  6
0x1aaa7  ldc.i4.8
0x1aaa8  newarr   [mscorlib]System.Object
0x1aaad  stloc.s  7
0x1aaaf  ldloc.s  7
0x1aab1  ldc.i4.0
0x1aab2  ldarg.1
0x1aab3  stelem.ref
0x1aab4  ldloc.s  7
0x1aab6  ldc.i4.1
0x1aab7  ldarg.2
0x1aab8  stelem.ref
0x1aab9  ldloc.s  7
0x1aabb  ldc.i4.2
0x1aabc  ldarg.3
0x1aabd  stelem.ref
0x1aabe  ldloc.s  7
0x1aac0  ldc.i4.3
0x1aac1  ldarg.s  4
0x1aac3  box      [mscorlib]System.UInt32
0x1aac8  stelem.ref
0x1aac9  ldloc.s  7
0x1aacb  ldc.i4.4
0x1aacc  ldarg.s  5
0x1aace  box      [mscorlib]System.Int32
0x1aad3  stelem.ref
0x1aad4  ldloc.s  7
0x1aad6  ldc.i4.5
0x1aad7  ldarg.s  6
0x1aad9  stelem.ref
0x1aada  ldloc.s  7
0x1aadc  ldc.i4.6
0x1aadd  ldarg.s  7
0x1aadf  stelem.ref
0x1aae0  ldloc.s  7
0x1aae2  ldc.i4.7
0x1aae3  ldarg.s  8
0x1aae5  stelem.ref
0x1aae6  ldloc.s  7
0x1aae8  ldloc.0
0x1aae9  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x1aaee  ldloc.0
0x1aaef  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x1aaf4  rethrow
0x1aaf6  stloc.1
0x1aaf7  ldstr    aLocalizexml// "LocalizeXml"
0x1aafc  ldarg.0
0x1aafd  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1ab02  ldarg.0
0x1ab03  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x1ab08  ldc.i4.8
0x1ab09  newarr   [mscorlib]System.String
0x1ab0e  stloc.s  8
0x1ab10  ldloc.s  8
0x1ab12  ldc.i4.0
0x1ab13  ldstr    aBstrxmlpath// "bstrXmlPath"
0x1ab18  stelem.ref
0x1ab19  ldloc.s  8
0x1ab1b  ldc.i4.1
0x1ab1c  ldstr    aBstrfeaturedef// "bstrFeatureDefinitionId"
0x1ab21  stelem.ref
0x1ab22  ldloc.s  8
0x1ab24  ldc.i4.2
0x1ab25  ldstr    aBstrfeatureroo// "bstrFeatureRoot"
0x1ab2a  stelem.ref
0x1ab2b  ldloc.s  8
0x1ab2d  ldc.i4.3
0x1ab2e  ldstr    aLcid// "lcid"
0x1ab33  stelem.ref
0x1ab34  ldloc.s  8
0x1ab36  ldc.i4.4
0x1ab37  ldstr    aCompatibilityl// "compatibilityLevel"
0x1ab3c  stelem.ref
0x1ab3d  ldloc.s  8
0x1ab3f  ldc.i4.5
0x1ab40  ldstr    aBstrdefaultres// "bstrDefaultResourceFile"
0x1ab45  stelem.ref
0x1ab46  ldloc.s  8
0x1ab48  ldc.i4.6
0x1ab49  ldstr    aPenablemodulec// "pEnableModuleCallback"
0x1ab4e  stelem.ref
0x1ab4f  ldloc.s  8
0x1ab51  ldc.i4.7
0x1ab52  ldstr    aBstrsolutionin// "bstrSolutionInfo"
0x1ab57  stelem.ref
0x1ab58  ldloc.s  8
0x1ab5a  ldc.i4.8
0x1ab5b  newarr   [mscorlib]System.Object
0x1ab60  stloc.s  9
0x1ab62  ldloc.s  9
0x1ab64  ldc.i4.0
0x1ab65  ldarg.1
0x1ab66  stelem.ref
0x1ab67  ldloc.s  9
0x1ab69  ldc.i4.1
0x1ab6a  ldarg.2
0x1ab6b  stelem.ref
0x1ab6c  ldloc.s  9
0x1ab6e  ldc.i4.2
0x1ab6f  ldarg.3
0x1ab70  stelem.ref
0x1ab71  ldloc.s  9
0x1ab73  ldc.i4.3
0x1ab74  ldarg.s  4
0x1ab76  box      [mscorlib]System.UInt32
0x1ab7b  stelem.ref
0x1ab7c  ldloc.s  9
0x1ab7e  ldc.i4.4
0x1ab7f  ldarg.s  5
0x1ab81  box      [mscorlib]System.Int32
0x1ab86  stelem.ref
0x1ab87  ldloc.s  9
0x1ab89  ldc.i4.5
0x1ab8a  ldarg.s  6
0x1ab8c  stelem.ref
0x1ab8d  ldloc.s  9
0x1ab8f  ldc.i4.6
0x1ab90  ldarg.s  7
0x1ab92  stelem.ref
0x1ab93  ldloc.s  9
0x1ab95  ldc.i4.7
0x1ab96  ldarg.s  8
0x1ab98  stelem.ref
0x1ab99  ldloc.s  9
0x1ab9b  ldloc.1
0x1ab9c  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x1aba1  ldloc.1
0x1aba2  ldc.i4.0
0x1aba3  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x1aba8  rethrow
0x1abaa  stloc.2
0x1abab  ldstr    aLocalizexml// "LocalizeXml"
0x1abb0  ldarg.0
0x1abb1  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1abb6  ldarg.0
0x1abb7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x1abbc  ldc.i4.8
0x1abbd  newarr   [mscorlib]System.String
0x1abc2  stloc.s  0xA
0x1abc4  ldloc.s  0xA
0x1abc6  ldc.i4.0
0x1abc7  ldstr    aBstrxmlpath// "bstrXmlPath"
0x1abcc  stelem.ref
0x1abcd  ldloc.s  0xA
0x1abcf  ldc.i4.1
0x1abd0  ldstr    aBstrfeaturedef// "bstrFeatureDefinitionId"
0x1abd5  stelem.ref
0x1abd6  ldloc.s  0xA
0x1abd8  ldc.i4.2
0x1abd9  ldstr    aBstrfeatureroo// "bstrFeatureRoot"
0x1abde  stelem.ref
0x1abdf  ldloc.s  0xA
0x1abe1  ldc.i4.3
0x1abe2  ldstr    aLcid// "lcid"
0x1abe7  stelem.ref
0x1abe8  ldloc.s  0xA
0x1abea  ldc.i4.4
0x1abeb  ldstr    aCompatibilityl// "compatibilityLevel"
0x1abf0  stelem.ref
0x1abf1  ldloc.s  0xA
0x1abf3  ldc.i4.5
0x1abf4  ldstr    aBstrdefaultres// "bstrDefaultResourceFile"
0x1abf9  stelem.ref
0x1abfa  ldloc.s  0xA
0x1abfc  ldc.i4.6
0x1abfd  ldstr    aPenablemodulec// "pEnableModuleCallback"
0x1ac02  stelem.ref
0x1ac03  ldloc.s  0xA
0x1ac05  ldc.i4.7
0x1ac06  ldstr    aBstrsolutionin// "bstrSolutionInfo"
0x1ac0b  stelem.ref
0x1ac0c  ldloc.s  0xA
0x1ac0e  ldc.i4.8
0x1ac0f  newarr   [mscorlib]System.Object
0x1ac14  stloc.s  0xB
0x1ac16  ldloc.s  0xB
0x1ac18  ldc.i4.0
0x1ac19  ldarg.1
0x1ac1a  stelem.ref
0x1ac1b  ldloc.s  0xB
0x1ac1d  ldc.i4.1
0x1ac1e  ldarg.2
0x1ac1f  stelem.ref
0x1ac20  ldloc.s  0xB
0x1ac22  ldc.i4.2
0x1ac23  ldarg.3
0x1ac24  stelem.ref
0x1ac25  ldloc.s  0xB
0x1ac27  ldc.i4.3
0x1ac28  ldarg.s  4
0x1ac2a  box      [mscorlib]System.UInt32
0x1ac2f  stelem.ref
0x1ac30  ldloc.s  0xB
0x1ac32  ldc.i4.4
0x1ac33  ldarg.s  5
0x1ac35  box      [mscorlib]System.Int32
0x1ac3a  stelem.ref
0x1ac3b  ldloc.s  0xB
0x1ac3d  ldc.i4.5
0x1ac3e  ldarg.s  6
0x1ac40  stelem.ref
0x1ac41  ldloc.s  0xB
0x1ac43  ldc.i4.6
0x1ac44  ldarg.s  7
0x1ac46  stelem.ref
0x1ac47  ldloc.s  0xB
0x1ac49  ldc.i4.7
0x1ac4a  ldarg.s  8
0x1ac4c  stelem.ref
0x1ac4d  ldloc.s  0xB
0x1ac4f  ldloc.2
0x1ac50  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x1ac55  ldloc.2
0x1ac56  ldarg.0
0x1ac57  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x1ac5c  ldarg.0
0x1ac5d  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x1ac62  ldarg.0
0x1ac63  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x1ac68  ldarg.0
0x1ac69  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x1ac6e  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x1ac73  rethrow
0x1ac75  stloc.3
0x1ac76  ldstr    aLocalizexml// "LocalizeXml"
0x1ac7b  ldarg.0
0x1ac7c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1ac81  ldarg.0
0x1ac82  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x1ac87  ldc.i4.8
0x1ac88  newarr   [mscorlib]System.String
0x1ac8d  stloc.s  0xC
0x1ac8f  ldloc.s  0xC
0x1ac91  ldc.i4.0
0x1ac92  ldstr    aBstrxmlpath// "bstrXmlPath"
0x1ac97  stelem.ref
0x1ac98  ldloc.s  0xC
0x1ac9a  ldc.i4.1
  ... truncated ...
```
