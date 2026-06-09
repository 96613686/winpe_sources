# Microsoft.SharePoint.Library.SPRequest::CreateList

- ea: `0x4ed60`
- end: `0x4f45c`
- name: `Microsoft.SharePoint.Library.SPRequest::CreateList`
- size: `1788`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4ea400`
- `0x553a60`

## callees

- `0x30b0`
- `0x4ed60`
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

- `0x4ee28`: `lTemplateID`
- `0x4ef68`: `lTemplateID`
- `0x4f0a9`: `lTemplateID`
- `0x4f201`: `lTemplateID`
- `0x4f34e`: `lTemplateID`
- `0x4ed6c`: `SPRequest.CreateList`
- `0x4edde`: `CreateList`
- `0x4ef1e`: `CreateList`
- `0x4f05f`: `CreateList`
- `0x4f1b7`: `CreateList`
- `0x4f304`: `CreateList`
- `0x4ee31`: `bstrDocTemplateType`
- `0x4ef71`: `bstrDocTemplateType`
- `0x4f0b2`: `bstrDocTemplateType`
- `0x4f20a`: `bstrDocTemplateType`
- `0x4f357`: `bstrDocTemplateType`
- `0x4ee61`: `bstrListInstanceFeaturePath`
- `0x4efa1`: `bstrListInstanceFeaturePath`
- `0x4f0e2`: `bstrListInstanceFeaturePath`
- `0x4f23a`: `bstrListInstanceFeaturePath`
- `0x4f387`: `bstrListInstanceFeaturePath`
- `0x4ee75`: `bstrCustomSchemaXml`
- `0x4efb5`: `bstrCustomSchemaXml`
- `0x4f0f6`: `bstrCustomSchemaXml`
- `0x4f24e`: `bstrCustomSchemaXml`
- `0x4f39b`: `bstrCustomSchemaXml`
- `0x4ee7f`: `pListTemplateModuleCallback`
- `0x4efbf`: `pListTemplateModuleCallback`
- `0x4f100`: `pListTemplateModuleCallback`
- `0x4f258`: `pListTemplateModuleCallback`
- `0x4f3a5`: `pListTemplateModuleCallback`
- `0x4ee89`: `bstrListTemplateSolutionInfo`
- `0x4efc9`: `bstrListTemplateSolutionInfo`
- `0x4f10a`: `bstrListTemplateSolutionInfo`
- `0x4f262`: `bstrListTemplateSolutionInfo`
- `0x4f3af`: `bstrListTemplateSolutionInfo`

## pseudocode

```c

```

## disassembly

```asm
0x4ed60  ldc.i4   0x66366C37
0x4ed65  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4ed6a  ldc.i4.s 0x64
0x4ed6c  ldstr    aSprequestCreat_8// "SPRequest.CreateList"
0x4ed71  ldc.i4.1
0x4ed72  ldc.i4.2
0x4ed73  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x4ed78  stloc.s  6
0x4ed7a  ldloc.s  6
0x4ed7c  ldc.i4.0
0x4ed7d  ldc.i4   0x96
0x4ed82  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x4ed87  stelem.ref
0x4ed88  ldloc.s  6
0x4ed8a  ldc.i4.1
0x4ed8b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x4ed90  stelem.ref
0x4ed91  ldloc.s  6
0x4ed93  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x4ed98  stloc.s  7
0x4ed9a  ldarg.0
0x4ed9b  dup
0x4ed9c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4eda1  ldc.i4.1
0x4eda2  add
0x4eda3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4eda8  ldarg.0
0x4eda9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x4edae  ldarg.0
0x4edaf  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x4edb4  ldarg.1
0x4edb5  ldarg.2
0x4edb6  ldarg.3
0x4edb7  ldarg.s  4
0x4edb9  ldarg.s  5
0x4edbb  ldarg.s  6
0x4edbd  ldarg.s  7
0x4edbf  ldarg.s  8
0x4edc1  ldarg.s  9
0x4edc3  ldarg.s  0xA
0x4edc5  ldarg.s  0xB
0x4edc7  ldarg.s  0xC
0x4edc9  ldarg.s  0xD
0x4edcb  ldarg.s  0xE
0x4edcd  ldarg.s  0xF
0x4edcf  ldarg.s  0x10
0x4edd1  callvirt instance string [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::CreateList(string, string, string, string, string, int32, string, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ListQuickLaunchOptions, bool, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISPEnableModuleCallback, string, string, string, string, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISPEnableModuleCallback, string)
0x4edd6  stloc.s  5
0x4edd8  leave    loc_4F459
0x4eddd  stloc.0
0x4edde  ldstr    aCreatelist// "CreateList"
0x4ede3  ldarg.0
0x4ede4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4ede9  ldarg.0
0x4edea  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4edef  ldc.i4.s 0x10
0x4edf1  newarr   [mscorlib]System.String
0x4edf6  stloc.s  8
0x4edf8  ldloc.s  8
0x4edfa  ldc.i4.0
0x4edfb  ldstr    aBstrweburl// "bstrWebUrl"
0x4ee00  stelem.ref
0x4ee01  ldloc.s  8
0x4ee03  ldc.i4.1
0x4ee04  ldstr    aBstrtitle// "bstrTitle"
0x4ee09  stelem.ref
0x4ee0a  ldloc.s  8
0x4ee0c  ldc.i4.2
0x4ee0d  ldstr    aBstrdescriptio// "bstrDescription"
0x4ee12  stelem.ref
0x4ee13  ldloc.s  8
0x4ee15  ldc.i4.3
0x4ee16  ldstr    aBstrlisturl// "bstrListUrl"
0x4ee1b  stelem.ref
0x4ee1c  ldloc.s  8
0x4ee1e  ldc.i4.4
0x4ee1f  ldstr    aBstrfeatureid// "bstrFeatureId"
0x4ee24  stelem.ref
0x4ee25  ldloc.s  8
0x4ee27  ldc.i4.5
0x4ee28  ldstr    aLtemplateid// "lTemplateID"
0x4ee2d  stelem.ref
0x4ee2e  ldloc.s  8
0x4ee30  ldc.i4.6
0x4ee31  ldstr    aBstrdoctemplat// "bstrDocTemplateType"
0x4ee36  stelem.ref
0x4ee37  ldloc.s  8
0x4ee39  ldc.i4.7
0x4ee3a  ldstr    aQlopt// "qlOpt"
0x4ee3f  stelem.ref
0x4ee40  ldloc.s  8
0x4ee42  ldc.i4.8
0x4ee43  ldstr    aBprovisionview// "bProvisionViewsAndForms"
0x4ee48  stelem.ref
0x4ee49  ldloc.s  8
0x4ee4b  ldc.i4.s 9
0x4ee4d  ldstr    aPlistinstancem// "pListInstanceModuleCallback"
0x4ee52  stelem.ref
0x4ee53  ldloc.s  8
0x4ee55  ldc.i4.s 0xA
0x4ee57  ldstr    aBstrlistinstan// "bstrListInstanceSolutionInfo"
0x4ee5c  stelem.ref
0x4ee5d  ldloc.s  8
0x4ee5f  ldc.i4.s 0xB
0x4ee61  ldstr    aBstrlistinstan_0// "bstrListInstanceFeaturePath"
0x4ee66  stelem.ref
0x4ee67  ldloc.s  8
0x4ee69  ldc.i4.s 0xC
0x4ee6b  ldstr    aBstrlistinstan_1// "bstrListInstanceFeatureId"
0x4ee70  stelem.ref
0x4ee71  ldloc.s  8
0x4ee73  ldc.i4.s 0xD
0x4ee75  ldstr    aBstrcustomsche// "bstrCustomSchemaXml"
0x4ee7a  stelem.ref
0x4ee7b  ldloc.s  8
0x4ee7d  ldc.i4.s 0xE
0x4ee7f  ldstr    aPlisttemplatem// "pListTemplateModuleCallback"
0x4ee84  stelem.ref
0x4ee85  ldloc.s  8
0x4ee87  ldc.i4.s 0xF
0x4ee89  ldstr    aBstrlisttempla// "bstrListTemplateSolutionInfo"
0x4ee8e  stelem.ref
0x4ee8f  ldloc.s  8
0x4ee91  ldc.i4.s 0x10
0x4ee93  newarr   [mscorlib]System.Object
0x4ee98  stloc.s  9
0x4ee9a  ldloc.s  9
0x4ee9c  ldc.i4.0
0x4ee9d  ldarg.1
0x4ee9e  stelem.ref
0x4ee9f  ldloc.s  9
0x4eea1  ldc.i4.1
0x4eea2  ldarg.2
0x4eea3  stelem.ref
0x4eea4  ldloc.s  9
0x4eea6  ldc.i4.2
0x4eea7  ldarg.3
0x4eea8  stelem.ref
0x4eea9  ldloc.s  9
0x4eeab  ldc.i4.3
0x4eeac  ldarg.s  4
0x4eeae  stelem.ref
0x4eeaf  ldloc.s  9
0x4eeb1  ldc.i4.4
0x4eeb2  ldarg.s  5
0x4eeb4  stelem.ref
0x4eeb5  ldloc.s  9
0x4eeb7  ldc.i4.5
0x4eeb8  ldarg.s  6
0x4eeba  box      [mscorlib]System.Int32
0x4eebf  stelem.ref
0x4eec0  ldloc.s  9
0x4eec2  ldc.i4.6
0x4eec3  ldarg.s  7
0x4eec5  stelem.ref
0x4eec6  ldloc.s  9
0x4eec8  ldc.i4.7
0x4eec9  ldarg.s  8
0x4eecb  box      [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ListQuickLaunchOptions
0x4eed0  stelem.ref
0x4eed1  ldloc.s  9
0x4eed3  ldc.i4.8
0x4eed4  ldarg.s  9
0x4eed6  box      [mscorlib]System.Boolean
0x4eedb  stelem.ref
0x4eedc  ldloc.s  9
0x4eede  ldc.i4.s 9
0x4eee0  ldarg.s  0xA
0x4eee2  stelem.ref
0x4eee3  ldloc.s  9
0x4eee5  ldc.i4.s 0xA
0x4eee7  ldarg.s  0xB
0x4eee9  stelem.ref
0x4eeea  ldloc.s  9
0x4eeec  ldc.i4.s 0xB
0x4eeee  ldarg.s  0xC
0x4eef0  stelem.ref
0x4eef1  ldloc.s  9
0x4eef3  ldc.i4.s 0xC
0x4eef5  ldarg.s  0xD
0x4eef7  stelem.ref
0x4eef8  ldloc.s  9
0x4eefa  ldc.i4.s 0xD
0x4eefc  ldarg.s  0xE
0x4eefe  stelem.ref
0x4eeff  ldloc.s  9
0x4ef01  ldc.i4.s 0xE
0x4ef03  ldarg.s  0xF
0x4ef05  stelem.ref
0x4ef06  ldloc.s  9
0x4ef08  ldc.i4.s 0xF
0x4ef0a  ldarg.s  0x10
0x4ef0c  stelem.ref
0x4ef0d  ldloc.s  9
0x4ef0f  ldloc.0
0x4ef10  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4ef15  ldloc.0
0x4ef16  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x4ef1b  rethrow
0x4ef1d  stloc.1
0x4ef1e  ldstr    aCreatelist// "CreateList"
0x4ef23  ldarg.0
0x4ef24  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4ef29  ldarg.0
0x4ef2a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4ef2f  ldc.i4.s 0x10
0x4ef31  newarr   [mscorlib]System.String
0x4ef36  stloc.s  0xA
0x4ef38  ldloc.s  0xA
0x4ef3a  ldc.i4.0
0x4ef3b  ldstr    aBstrweburl// "bstrWebUrl"
0x4ef40  stelem.ref
0x4ef41  ldloc.s  0xA
0x4ef43  ldc.i4.1
0x4ef44  ldstr    aBstrtitle// "bstrTitle"
0x4ef49  stelem.ref
0x4ef4a  ldloc.s  0xA
0x4ef4c  ldc.i4.2
0x4ef4d  ldstr    aBstrdescriptio// "bstrDescription"
0x4ef52  stelem.ref
0x4ef53  ldloc.s  0xA
0x4ef55  ldc.i4.3
0x4ef56  ldstr    aBstrlisturl// "bstrListUrl"
0x4ef5b  stelem.ref
0x4ef5c  ldloc.s  0xA
0x4ef5e  ldc.i4.4
0x4ef5f  ldstr    aBstrfeatureid// "bstrFeatureId"
0x4ef64  stelem.ref
0x4ef65  ldloc.s  0xA
0x4ef67  ldc.i4.5
0x4ef68  ldstr    aLtemplateid// "lTemplateID"
0x4ef6d  stelem.ref
0x4ef6e  ldloc.s  0xA
0x4ef70  ldc.i4.6
0x4ef71  ldstr    aBstrdoctemplat// "bstrDocTemplateType"
0x4ef76  stelem.ref
0x4ef77  ldloc.s  0xA
0x4ef79  ldc.i4.7
0x4ef7a  ldstr    aQlopt// "qlOpt"
0x4ef7f  stelem.ref
0x4ef80  ldloc.s  0xA
0x4ef82  ldc.i4.8
0x4ef83  ldstr    aBprovisionview// "bProvisionViewsAndForms"
0x4ef88  stelem.ref
0x4ef89  ldloc.s  0xA
0x4ef8b  ldc.i4.s 9
0x4ef8d  ldstr    aPlistinstancem// "pListInstanceModuleCallback"
0x4ef92  stelem.ref
0x4ef93  ldloc.s  0xA
0x4ef95  ldc.i4.s 0xA
0x4ef97  ldstr    aBstrlistinstan// "bstrListInstanceSolutionInfo"
0x4ef9c  stelem.ref
0x4ef9d  ldloc.s  0xA
0x4ef9f  ldc.i4.s 0xB
0x4efa1  ldstr    aBstrlistinstan_0// "bstrListInstanceFeaturePath"
0x4efa6  stelem.ref
0x4efa7  ldloc.s  0xA
0x4efa9  ldc.i4.s 0xC
0x4efab  ldstr    aBstrlistinstan_1// "bstrListInstanceFeatureId"
0x4efb0  stelem.ref
0x4efb1  ldloc.s  0xA
0x4efb3  ldc.i4.s 0xD
0x4efb5  ldstr    aBstrcustomsche// "bstrCustomSchemaXml"
0x4efba  stelem.ref
0x4efbb  ldloc.s  0xA
0x4efbd  ldc.i4.s 0xE
0x4efbf  ldstr    aPlisttemplatem// "pListTemplateModuleCallback"
0x4efc4  stelem.ref
0x4efc5  ldloc.s  0xA
0x4efc7  ldc.i4.s 0xF
0x4efc9  ldstr    aBstrlisttempla// "bstrListTemplateSolutionInfo"
0x4efce  stelem.ref
0x4efcf  ldloc.s  0xA
0x4efd1  ldc.i4.s 0x10
0x4efd3  newarr   [mscorlib]System.Object
0x4efd8  stloc.s  0xB
0x4efda  ldloc.s  0xB
0x4efdc  ldc.i4.0
0x4efdd  ldarg.1
0x4efde  stelem.ref
0x4efdf  ldloc.s  0xB
0x4efe1  ldc.i4.1
0x4efe2  ldarg.2
0x4efe3  stelem.ref
0x4efe4  ldloc.s  0xB
0x4efe6  ldc.i4.2
0x4efe7  ldarg.3
0x4efe8  stelem.ref
0x4efe9  ldloc.s  0xB
0x4efeb  ldc.i4.3
0x4efec  ldarg.s  4
0x4efee  stelem.ref
0x4efef  ldloc.s  0xB
0x4eff1  ldc.i4.4
0x4eff2  ldarg.s  5
0x4eff4  stelem.ref
0x4eff5  ldloc.s  0xB
0x4eff7  ldc.i4.5
0x4eff8  ldarg.s  6
0x4effa  box      [mscorlib]System.Int32
  ... truncated ...
```
