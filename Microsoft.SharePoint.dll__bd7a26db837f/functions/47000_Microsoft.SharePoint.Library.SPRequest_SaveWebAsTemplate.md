# Microsoft.SharePoint.Library.SPRequest::SaveWebAsTemplate

- ea: `0x47000`
- end: `0x4732b`
- name: `Microsoft.SharePoint.Library.SPRequest::SaveWebAsTemplate`
- size: `811`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x30b0`
- `0x47000`
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

- `0x4700c`: `SPRequest.SaveWebAsTemplate`
- `0x47066`: `SaveWebAsTemplate`
- `0x470e7`: `SaveWebAsTemplate`
- `0x47169`: `SaveWebAsTemplate`
- `0x47202`: `SaveWebAsTemplate`
- `0x47290`: `SaveWebAsTemplate`
- `0x4708b`: `bstrTemplateName`
- `0x4710c`: `bstrTemplateName`
- `0x4718e`: `bstrTemplateName`
- `0x47227`: `bstrTemplateName`
- `0x472b5`: `bstrTemplateName`
- `0x47094`: `bstrTemplateTitle`
- `0x47115`: `bstrTemplateTitle`
- `0x47197`: `bstrTemplateTitle`
- `0x47230`: `bstrTemplateTitle`
- `0x472be`: `bstrTemplateTitle`

## pseudocode

```c

```

## disassembly

```asm
0x47000  ldc.i4   0x66366C37
0x47005  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4700a  ldc.i4.s 0x64
0x4700c  ldstr    aSprequestSavew// "SPRequest.SaveWebAsTemplate"
0x47011  ldc.i4.1
0x47012  ldc.i4.2
0x47013  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x47018  stloc.s  5
0x4701a  ldloc.s  5
0x4701c  ldc.i4.0
0x4701d  ldc.i4   0x96
0x47022  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x47027  stelem.ref
0x47028  ldloc.s  5
0x4702a  ldc.i4.1
0x4702b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x47030  stelem.ref
0x47031  ldloc.s  5
0x47033  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x47038  stloc.s  6
0x4703a  ldarg.0
0x4703b  dup
0x4703c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x47041  ldc.i4.1
0x47042  add
0x47043  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x47048  ldarg.0
0x47049  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x4704e  ldarg.0
0x4704f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x47054  ldarg.1
0x47055  ldarg.2
0x47056  ldarg.3
0x47057  ldarg.s  4
0x47059  ldarg.s  5
0x4705b  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::SaveWebAsTemplate(string, string, string, string, bool)
0x47060  leave    loc_4730B
0x47065  stloc.0
0x47066  ldstr    aSavewebastempl// "SaveWebAsTemplate"
0x4706b  ldarg.0
0x4706c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x47071  ldarg.0
0x47072  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x47077  ldc.i4.5
0x47078  newarr   [mscorlib]System.String
0x4707d  stloc.s  7
0x4707f  ldloc.s  7
0x47081  ldc.i4.0
0x47082  ldstr    aBstrurl// "bstrUrl"
0x47087  stelem.ref
0x47088  ldloc.s  7
0x4708a  ldc.i4.1
0x4708b  ldstr    aBstrtemplatena// "bstrTemplateName"
0x47090  stelem.ref
0x47091  ldloc.s  7
0x47093  ldc.i4.2
0x47094  ldstr    aBstrtemplateti// "bstrTemplateTitle"
0x47099  stelem.ref
0x4709a  ldloc.s  7
0x4709c  ldc.i4.3
0x4709d  ldstr    aBstrdescriptio// "bstrDescription"
0x470a2  stelem.ref
0x470a3  ldloc.s  7
0x470a5  ldc.i4.4
0x470a6  ldstr    aBsavedata// "bSaveData"
0x470ab  stelem.ref
0x470ac  ldloc.s  7
0x470ae  ldc.i4.5
0x470af  newarr   [mscorlib]System.Object
0x470b4  stloc.s  8
0x470b6  ldloc.s  8
0x470b8  ldc.i4.0
0x470b9  ldarg.1
0x470ba  stelem.ref
0x470bb  ldloc.s  8
0x470bd  ldc.i4.1
0x470be  ldarg.2
0x470bf  stelem.ref
0x470c0  ldloc.s  8
0x470c2  ldc.i4.2
0x470c3  ldarg.3
0x470c4  stelem.ref
0x470c5  ldloc.s  8
0x470c7  ldc.i4.3
0x470c8  ldarg.s  4
0x470ca  stelem.ref
0x470cb  ldloc.s  8
0x470cd  ldc.i4.4
0x470ce  ldarg.s  5
0x470d0  box      [mscorlib]System.Boolean
0x470d5  stelem.ref
0x470d6  ldloc.s  8
0x470d8  ldloc.0
0x470d9  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x470de  ldloc.0
0x470df  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x470e4  rethrow
0x470e6  stloc.1
0x470e7  ldstr    aSavewebastempl// "SaveWebAsTemplate"
0x470ec  ldarg.0
0x470ed  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x470f2  ldarg.0
0x470f3  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x470f8  ldc.i4.5
0x470f9  newarr   [mscorlib]System.String
0x470fe  stloc.s  9
0x47100  ldloc.s  9
0x47102  ldc.i4.0
0x47103  ldstr    aBstrurl// "bstrUrl"
0x47108  stelem.ref
0x47109  ldloc.s  9
0x4710b  ldc.i4.1
0x4710c  ldstr    aBstrtemplatena// "bstrTemplateName"
0x47111  stelem.ref
0x47112  ldloc.s  9
0x47114  ldc.i4.2
0x47115  ldstr    aBstrtemplateti// "bstrTemplateTitle"
0x4711a  stelem.ref
0x4711b  ldloc.s  9
0x4711d  ldc.i4.3
0x4711e  ldstr    aBstrdescriptio// "bstrDescription"
0x47123  stelem.ref
0x47124  ldloc.s  9
0x47126  ldc.i4.4
0x47127  ldstr    aBsavedata// "bSaveData"
0x4712c  stelem.ref
0x4712d  ldloc.s  9
0x4712f  ldc.i4.5
0x47130  newarr   [mscorlib]System.Object
0x47135  stloc.s  0xA
0x47137  ldloc.s  0xA
0x47139  ldc.i4.0
0x4713a  ldarg.1
0x4713b  stelem.ref
0x4713c  ldloc.s  0xA
0x4713e  ldc.i4.1
0x4713f  ldarg.2
0x47140  stelem.ref
0x47141  ldloc.s  0xA
0x47143  ldc.i4.2
0x47144  ldarg.3
0x47145  stelem.ref
0x47146  ldloc.s  0xA
0x47148  ldc.i4.3
0x47149  ldarg.s  4
0x4714b  stelem.ref
0x4714c  ldloc.s  0xA
0x4714e  ldc.i4.4
0x4714f  ldarg.s  5
0x47151  box      [mscorlib]System.Boolean
0x47156  stelem.ref
0x47157  ldloc.s  0xA
0x47159  ldloc.1
0x4715a  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4715f  ldloc.1
0x47160  ldc.i4.0
0x47161  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x47166  rethrow
0x47168  stloc.2
0x47169  ldstr    aSavewebastempl// "SaveWebAsTemplate"
0x4716e  ldarg.0
0x4716f  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x47174  ldarg.0
0x47175  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4717a  ldc.i4.5
0x4717b  newarr   [mscorlib]System.String
0x47180  stloc.s  0xB
0x47182  ldloc.s  0xB
0x47184  ldc.i4.0
0x47185  ldstr    aBstrurl// "bstrUrl"
0x4718a  stelem.ref
0x4718b  ldloc.s  0xB
0x4718d  ldc.i4.1
0x4718e  ldstr    aBstrtemplatena// "bstrTemplateName"
0x47193  stelem.ref
0x47194  ldloc.s  0xB
0x47196  ldc.i4.2
0x47197  ldstr    aBstrtemplateti// "bstrTemplateTitle"
0x4719c  stelem.ref
0x4719d  ldloc.s  0xB
0x4719f  ldc.i4.3
0x471a0  ldstr    aBstrdescriptio// "bstrDescription"
0x471a5  stelem.ref
0x471a6  ldloc.s  0xB
0x471a8  ldc.i4.4
0x471a9  ldstr    aBsavedata// "bSaveData"
0x471ae  stelem.ref
0x471af  ldloc.s  0xB
0x471b1  ldc.i4.5
0x471b2  newarr   [mscorlib]System.Object
0x471b7  stloc.s  0xC
0x471b9  ldloc.s  0xC
0x471bb  ldc.i4.0
0x471bc  ldarg.1
0x471bd  stelem.ref
0x471be  ldloc.s  0xC
0x471c0  ldc.i4.1
0x471c1  ldarg.2
0x471c2  stelem.ref
0x471c3  ldloc.s  0xC
0x471c5  ldc.i4.2
0x471c6  ldarg.3
0x471c7  stelem.ref
0x471c8  ldloc.s  0xC
0x471ca  ldc.i4.3
0x471cb  ldarg.s  4
0x471cd  stelem.ref
0x471ce  ldloc.s  0xC
0x471d0  ldc.i4.4
0x471d1  ldarg.s  5
0x471d3  box      [mscorlib]System.Boolean
0x471d8  stelem.ref
0x471d9  ldloc.s  0xC
0x471db  ldloc.2
0x471dc  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x471e1  ldloc.2
0x471e2  ldarg.0
0x471e3  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x471e8  ldarg.0
0x471e9  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x471ee  ldarg.0
0x471ef  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x471f4  ldarg.0
0x471f5  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x471fa  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x471ff  rethrow
0x47201  stloc.3
0x47202  ldstr    aSavewebastempl// "SaveWebAsTemplate"
0x47207  ldarg.0
0x47208  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4720d  ldarg.0
0x4720e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x47213  ldc.i4.5
0x47214  newarr   [mscorlib]System.String
0x47219  stloc.s  0xD
0x4721b  ldloc.s  0xD
0x4721d  ldc.i4.0
0x4721e  ldstr    aBstrurl// "bstrUrl"
0x47223  stelem.ref
0x47224  ldloc.s  0xD
0x47226  ldc.i4.1
0x47227  ldstr    aBstrtemplatena// "bstrTemplateName"
0x4722c  stelem.ref
0x4722d  ldloc.s  0xD
0x4722f  ldc.i4.2
0x47230  ldstr    aBstrtemplateti// "bstrTemplateTitle"
0x47235  stelem.ref
0x47236  ldloc.s  0xD
0x47238  ldc.i4.3
0x47239  ldstr    aBstrdescriptio// "bstrDescription"
0x4723e  stelem.ref
0x4723f  ldloc.s  0xD
0x47241  ldc.i4.4
0x47242  ldstr    aBsavedata// "bSaveData"
0x47247  stelem.ref
0x47248  ldloc.s  0xD
0x4724a  ldc.i4.5
0x4724b  newarr   [mscorlib]System.Object
0x47250  stloc.s  0xE
0x47252  ldloc.s  0xE
0x47254  ldc.i4.0
0x47255  ldarg.1
0x47256  stelem.ref
0x47257  ldloc.s  0xE
0x47259  ldc.i4.1
0x4725a  ldarg.2
0x4725b  stelem.ref
0x4725c  ldloc.s  0xE
0x4725e  ldc.i4.2
0x4725f  ldarg.3
0x47260  stelem.ref
0x47261  ldloc.s  0xE
0x47263  ldc.i4.3
0x47264  ldarg.s  4
0x47266  stelem.ref
0x47267  ldloc.s  0xE
0x47269  ldc.i4.4
0x4726a  ldarg.s  5
0x4726c  box      [mscorlib]System.Boolean
0x47271  stelem.ref
0x47272  ldloc.s  0xE
0x47274  ldloc.3
0x47275  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4727a  ldloc.3
0x4727b  ldarg.0
0x4727c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x47281  ldarg.0
0x47282  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTraceOnRelease
0x47287  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestNullReferenceException(class [mscorlib]System.NullReferenceException nullEx, string stackTraceOnCreate, string stackTraceOnRelease)
0x4728c  rethrow
0x4728e  stloc.s  4
0x47290  ldstr    aSavewebastempl// "SaveWebAsTemplate"
0x47295  ldarg.0
0x47296  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4729b  ldarg.0
0x4729c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x472a1  ldc.i4.5
0x472a2  newarr   [mscorlib]System.String
0x472a7  stloc.s  0xF
0x472a9  ldloc.s  0xF
  ... truncated ...
```
