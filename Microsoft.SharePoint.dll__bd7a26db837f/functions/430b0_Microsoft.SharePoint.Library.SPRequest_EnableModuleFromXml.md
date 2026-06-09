# Microsoft.SharePoint.Library.SPRequest::EnableModuleFromXml

- ea: `0x430b0`
- end: `0x43428`
- name: `Microsoft.SharePoint.Library.SPRequest::EnableModuleFromXml`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x55e210`

## callees

- `0x30b0`
- `0x430b0`
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

- `0x4314f`: `bstrXML`
- `0x431df`: `bstrXML`
- `0x43270`: `bstrXML`
- `0x43318`: `bstrXML`
- `0x433b5`: `bstrXML`
- `0x430bc`: `SPRequest.EnableModuleFromXml`
- `0x43118`: `EnableModuleFromXml`
- `0x431a8`: `EnableModuleFromXml`
- `0x43239`: `EnableModuleFromXml`
- `0x432e1`: `EnableModuleFromXml`
- `0x4337e`: `EnableModuleFromXml`
- `0x43134`: `bstrSetupDirectory`
- `0x431c4`: `bstrSetupDirectory`
- `0x43255`: `bstrSetupDirectory`
- `0x432fd`: `bstrSetupDirectory`
- `0x4339a`: `bstrSetupDirectory`
- `0x4313d`: `bstrFeatureDirectory`
- `0x431cd`: `bstrFeatureDirectory`
- `0x4325e`: `bstrFeatureDirectory`
- `0x43306`: `bstrFeatureDirectory`
- `0x433a3`: `bstrFeatureDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x430b0  ldc.i4   0x66366C37
0x430b5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x430ba  ldc.i4.s 0x64
0x430bc  ldstr    aSprequestEnabl_1// "SPRequest.EnableModuleFromXml"
0x430c1  ldc.i4.1
0x430c2  ldc.i4.2
0x430c3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x430c8  stloc.s  5
0x430ca  ldloc.s  5
0x430cc  ldc.i4.0
0x430cd  ldc.i4   0x96
0x430d2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x430d7  stelem.ref
0x430d8  ldloc.s  5
0x430da  ldc.i4.1
0x430db  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x430e0  stelem.ref
0x430e1  ldloc.s  5
0x430e3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x430e8  stloc.s  6
0x430ea  ldarg.0
0x430eb  dup
0x430ec  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x430f1  ldc.i4.1
0x430f2  add
0x430f3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x430f8  ldarg.0
0x430f9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x430fe  ldarg.0
0x430ff  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x43104  ldarg.1
0x43105  ldarg.2
0x43106  ldarg.3
0x43107  ldarg.s  4
0x43109  ldarg.s  5
0x4310b  ldarg.s  6
0x4310d  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::EnableModuleFromXml(string, string, string, string, bool, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISPEnableModuleCallback)
0x43112  leave    loc_43408
0x43117  stloc.0
0x43118  ldstr    aEnablemodulefr// "EnableModuleFromXml"
0x4311d  ldarg.0
0x4311e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x43123  ldarg.0
0x43124  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x43129  ldc.i4.6
0x4312a  newarr   [mscorlib]System.String
0x4312f  stloc.s  7
0x43131  ldloc.s  7
0x43133  ldc.i4.0
0x43134  ldstr    aBstrsetupdirec// "bstrSetupDirectory"
0x43139  stelem.ref
0x4313a  ldloc.s  7
0x4313c  ldc.i4.1
0x4313d  ldstr    aBstrfeaturedir// "bstrFeatureDirectory"
0x43142  stelem.ref
0x43143  ldloc.s  7
0x43145  ldc.i4.2
0x43146  ldstr    aBstrurl// "bstrUrl"
0x4314b  stelem.ref
0x4314c  ldloc.s  7
0x4314e  ldc.i4.3
0x4314f  ldstr    aBstrxml// "bstrXML"
0x43154  stelem.ref
0x43155  ldloc.s  7
0x43157  ldc.i4.4
0x43158  ldstr    aFforceunghost// "fForceUnghost"
0x4315d  stelem.ref
0x4315e  ldloc.s  7
0x43160  ldc.i4.5
0x43161  ldstr    aPmodulecontext// "pModuleContext"
0x43166  stelem.ref
0x43167  ldloc.s  7
0x43169  ldc.i4.6
0x4316a  newarr   [mscorlib]System.Object
0x4316f  stloc.s  8
0x43171  ldloc.s  8
0x43173  ldc.i4.0
0x43174  ldarg.1
0x43175  stelem.ref
0x43176  ldloc.s  8
0x43178  ldc.i4.1
0x43179  ldarg.2
0x4317a  stelem.ref
0x4317b  ldloc.s  8
0x4317d  ldc.i4.2
0x4317e  ldarg.3
0x4317f  stelem.ref
0x43180  ldloc.s  8
0x43182  ldc.i4.3
0x43183  ldarg.s  4
0x43185  stelem.ref
0x43186  ldloc.s  8
0x43188  ldc.i4.4
0x43189  ldarg.s  5
0x4318b  box      [mscorlib]System.Boolean
0x43190  stelem.ref
0x43191  ldloc.s  8
0x43193  ldc.i4.5
0x43194  ldarg.s  6
0x43196  stelem.ref
0x43197  ldloc.s  8
0x43199  ldloc.0
0x4319a  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4319f  ldloc.0
0x431a0  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x431a5  rethrow
0x431a7  stloc.1
0x431a8  ldstr    aEnablemodulefr// "EnableModuleFromXml"
0x431ad  ldarg.0
0x431ae  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x431b3  ldarg.0
0x431b4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x431b9  ldc.i4.6
0x431ba  newarr   [mscorlib]System.String
0x431bf  stloc.s  9
0x431c1  ldloc.s  9
0x431c3  ldc.i4.0
0x431c4  ldstr    aBstrsetupdirec// "bstrSetupDirectory"
0x431c9  stelem.ref
0x431ca  ldloc.s  9
0x431cc  ldc.i4.1
0x431cd  ldstr    aBstrfeaturedir// "bstrFeatureDirectory"
0x431d2  stelem.ref
0x431d3  ldloc.s  9
0x431d5  ldc.i4.2
0x431d6  ldstr    aBstrurl// "bstrUrl"
0x431db  stelem.ref
0x431dc  ldloc.s  9
0x431de  ldc.i4.3
0x431df  ldstr    aBstrxml// "bstrXML"
0x431e4  stelem.ref
0x431e5  ldloc.s  9
0x431e7  ldc.i4.4
0x431e8  ldstr    aFforceunghost// "fForceUnghost"
0x431ed  stelem.ref
0x431ee  ldloc.s  9
0x431f0  ldc.i4.5
0x431f1  ldstr    aPmodulecontext// "pModuleContext"
0x431f6  stelem.ref
0x431f7  ldloc.s  9
0x431f9  ldc.i4.6
0x431fa  newarr   [mscorlib]System.Object
0x431ff  stloc.s  0xA
0x43201  ldloc.s  0xA
0x43203  ldc.i4.0
0x43204  ldarg.1
0x43205  stelem.ref
0x43206  ldloc.s  0xA
0x43208  ldc.i4.1
0x43209  ldarg.2
0x4320a  stelem.ref
0x4320b  ldloc.s  0xA
0x4320d  ldc.i4.2
0x4320e  ldarg.3
0x4320f  stelem.ref
0x43210  ldloc.s  0xA
0x43212  ldc.i4.3
0x43213  ldarg.s  4
0x43215  stelem.ref
0x43216  ldloc.s  0xA
0x43218  ldc.i4.4
0x43219  ldarg.s  5
0x4321b  box      [mscorlib]System.Boolean
0x43220  stelem.ref
0x43221  ldloc.s  0xA
0x43223  ldc.i4.5
0x43224  ldarg.s  6
0x43226  stelem.ref
0x43227  ldloc.s  0xA
0x43229  ldloc.1
0x4322a  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4322f  ldloc.1
0x43230  ldc.i4.0
0x43231  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x43236  rethrow
0x43238  stloc.2
0x43239  ldstr    aEnablemodulefr// "EnableModuleFromXml"
0x4323e  ldarg.0
0x4323f  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x43244  ldarg.0
0x43245  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4324a  ldc.i4.6
0x4324b  newarr   [mscorlib]System.String
0x43250  stloc.s  0xB
0x43252  ldloc.s  0xB
0x43254  ldc.i4.0
0x43255  ldstr    aBstrsetupdirec// "bstrSetupDirectory"
0x4325a  stelem.ref
0x4325b  ldloc.s  0xB
0x4325d  ldc.i4.1
0x4325e  ldstr    aBstrfeaturedir// "bstrFeatureDirectory"
0x43263  stelem.ref
0x43264  ldloc.s  0xB
0x43266  ldc.i4.2
0x43267  ldstr    aBstrurl// "bstrUrl"
0x4326c  stelem.ref
0x4326d  ldloc.s  0xB
0x4326f  ldc.i4.3
0x43270  ldstr    aBstrxml// "bstrXML"
0x43275  stelem.ref
0x43276  ldloc.s  0xB
0x43278  ldc.i4.4
0x43279  ldstr    aFforceunghost// "fForceUnghost"
0x4327e  stelem.ref
0x4327f  ldloc.s  0xB
0x43281  ldc.i4.5
0x43282  ldstr    aPmodulecontext// "pModuleContext"
0x43287  stelem.ref
0x43288  ldloc.s  0xB
0x4328a  ldc.i4.6
0x4328b  newarr   [mscorlib]System.Object
0x43290  stloc.s  0xC
0x43292  ldloc.s  0xC
0x43294  ldc.i4.0
0x43295  ldarg.1
0x43296  stelem.ref
0x43297  ldloc.s  0xC
0x43299  ldc.i4.1
0x4329a  ldarg.2
0x4329b  stelem.ref
0x4329c  ldloc.s  0xC
0x4329e  ldc.i4.2
0x4329f  ldarg.3
0x432a0  stelem.ref
0x432a1  ldloc.s  0xC
0x432a3  ldc.i4.3
0x432a4  ldarg.s  4
0x432a6  stelem.ref
0x432a7  ldloc.s  0xC
0x432a9  ldc.i4.4
0x432aa  ldarg.s  5
0x432ac  box      [mscorlib]System.Boolean
0x432b1  stelem.ref
0x432b2  ldloc.s  0xC
0x432b4  ldc.i4.5
0x432b5  ldarg.s  6
0x432b7  stelem.ref
0x432b8  ldloc.s  0xC
0x432ba  ldloc.2
0x432bb  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x432c0  ldloc.2
0x432c1  ldarg.0
0x432c2  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x432c7  ldarg.0
0x432c8  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x432cd  ldarg.0
0x432ce  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x432d3  ldarg.0
0x432d4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x432d9  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x432de  rethrow
0x432e0  stloc.3
0x432e1  ldstr    aEnablemodulefr// "EnableModuleFromXml"
0x432e6  ldarg.0
0x432e7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x432ec  ldarg.0
0x432ed  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x432f2  ldc.i4.6
0x432f3  newarr   [mscorlib]System.String
0x432f8  stloc.s  0xD
0x432fa  ldloc.s  0xD
0x432fc  ldc.i4.0
0x432fd  ldstr    aBstrsetupdirec// "bstrSetupDirectory"
0x43302  stelem.ref
0x43303  ldloc.s  0xD
0x43305  ldc.i4.1
0x43306  ldstr    aBstrfeaturedir// "bstrFeatureDirectory"
0x4330b  stelem.ref
0x4330c  ldloc.s  0xD
0x4330e  ldc.i4.2
0x4330f  ldstr    aBstrurl// "bstrUrl"
0x43314  stelem.ref
0x43315  ldloc.s  0xD
0x43317  ldc.i4.3
0x43318  ldstr    aBstrxml// "bstrXML"
0x4331d  stelem.ref
0x4331e  ldloc.s  0xD
0x43320  ldc.i4.4
0x43321  ldstr    aFforceunghost// "fForceUnghost"
0x43326  stelem.ref
0x43327  ldloc.s  0xD
0x43329  ldc.i4.5
0x4332a  ldstr    aPmodulecontext// "pModuleContext"
0x4332f  stelem.ref
0x43330  ldloc.s  0xD
0x43332  ldc.i4.6
0x43333  newarr   [mscorlib]System.Object
0x43338  stloc.s  0xE
0x4333a  ldloc.s  0xE
0x4333c  ldc.i4.0
0x4333d  ldarg.1
0x4333e  stelem.ref
0x4333f  ldloc.s  0xE
0x43341  ldc.i4.1
0x43342  ldarg.2
0x43343  stelem.ref
0x43344  ldloc.s  0xE
0x43346  ldc.i4.2
0x43347  ldarg.3
0x43348  stelem.ref
  ... truncated ...
```
