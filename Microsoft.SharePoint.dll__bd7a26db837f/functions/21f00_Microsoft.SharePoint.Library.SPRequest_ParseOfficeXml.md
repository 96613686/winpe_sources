# Microsoft.SharePoint.Library.SPRequest::ParseOfficeXml

- ea: `0x21f00`
- end: `0x22178`
- name: `Microsoft.SharePoint.Library.SPRequest::ParseOfficeXml`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x80aad0`

## callees

- `0x30b0`
- `0x21f00`
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

- `0x21f7e`: `bstrXML`
- `0x21fdc`: `bstrXML`
- `0x2203b`: `bstrXML`
- `0x220b1`: `bstrXML`
- `0x2211c`: `bstrXML`
- `0x21f0c`: `SPRequest.ParseOfficeXml`
- `0x21f62`: `ParseOfficeXml`
- `0x21fc0`: `ParseOfficeXml`
- `0x2201f`: `ParseOfficeXml`
- `0x22095`: `ParseOfficeXml`
- `0x22100`: `ParseOfficeXml`
- `0x21f90`: `p2DWriter`
- `0x21fee`: `p2DWriter`
- `0x2204d`: `p2DWriter`
- `0x220c3`: `p2DWriter`
- `0x2212e`: `p2DWriter`

## pseudocode

```c

```

## disassembly

```asm
0x21f00  ldc.i4   0x66366C37
0x21f05  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x21f0a  ldc.i4.s 0x64
0x21f0c  ldstr    aSprequestParse// "SPRequest.ParseOfficeXml"
0x21f11  ldc.i4.1
0x21f12  ldc.i4.2
0x21f13  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x21f18  stloc.s  5
0x21f1a  ldloc.s  5
0x21f1c  ldc.i4.0
0x21f1d  ldc.i4   0x96
0x21f22  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x21f27  stelem.ref
0x21f28  ldloc.s  5
0x21f2a  ldc.i4.1
0x21f2b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x21f30  stelem.ref
0x21f31  ldloc.s  5
0x21f33  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x21f38  stloc.s  6
0x21f3a  ldarg.0
0x21f3b  dup
0x21f3c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x21f41  ldc.i4.1
0x21f42  add
0x21f43  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x21f48  ldarg.0
0x21f49  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x21f4e  ldarg.0
0x21f4f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x21f54  ldarg.1
0x21f55  ldarg.2
0x21f56  ldarg.3
0x21f57  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::ParseOfficeXml(string, string, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISP2DSafeArrayWriter)
0x21f5c  leave    loc_22158
0x21f61  stloc.0
0x21f62  ldstr    aParseofficexml// "ParseOfficeXml"
0x21f67  ldarg.0
0x21f68  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x21f6d  ldarg.0
0x21f6e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x21f73  ldc.i4.3
0x21f74  newarr   [mscorlib]System.String
0x21f79  stloc.s  7
0x21f7b  ldloc.s  7
0x21f7d  ldc.i4.0
0x21f7e  ldstr    aBstrxml// "bstrXML"
0x21f83  stelem.ref
0x21f84  ldloc.s  7
0x21f86  ldc.i4.1
0x21f87  ldstr    aBstrprefix// "bstrPrefix"
0x21f8c  stelem.ref
0x21f8d  ldloc.s  7
0x21f8f  ldc.i4.2
0x21f90  ldstr    aP2dwriter// "p2DWriter"
0x21f95  stelem.ref
0x21f96  ldloc.s  7
0x21f98  ldc.i4.3
0x21f99  newarr   [mscorlib]System.Object
0x21f9e  stloc.s  8
0x21fa0  ldloc.s  8
0x21fa2  ldc.i4.0
0x21fa3  ldarg.1
0x21fa4  stelem.ref
0x21fa5  ldloc.s  8
0x21fa7  ldc.i4.1
0x21fa8  ldarg.2
0x21fa9  stelem.ref
0x21faa  ldloc.s  8
0x21fac  ldc.i4.2
0x21fad  ldarg.3
0x21fae  stelem.ref
0x21faf  ldloc.s  8
0x21fb1  ldloc.0
0x21fb2  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x21fb7  ldloc.0
0x21fb8  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x21fbd  rethrow
0x21fbf  stloc.1
0x21fc0  ldstr    aParseofficexml// "ParseOfficeXml"
0x21fc5  ldarg.0
0x21fc6  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x21fcb  ldarg.0
0x21fcc  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x21fd1  ldc.i4.3
0x21fd2  newarr   [mscorlib]System.String
0x21fd7  stloc.s  9
0x21fd9  ldloc.s  9
0x21fdb  ldc.i4.0
0x21fdc  ldstr    aBstrxml// "bstrXML"
0x21fe1  stelem.ref
0x21fe2  ldloc.s  9
0x21fe4  ldc.i4.1
0x21fe5  ldstr    aBstrprefix// "bstrPrefix"
0x21fea  stelem.ref
0x21feb  ldloc.s  9
0x21fed  ldc.i4.2
0x21fee  ldstr    aP2dwriter// "p2DWriter"
0x21ff3  stelem.ref
0x21ff4  ldloc.s  9
0x21ff6  ldc.i4.3
0x21ff7  newarr   [mscorlib]System.Object
0x21ffc  stloc.s  0xA
0x21ffe  ldloc.s  0xA
0x22000  ldc.i4.0
0x22001  ldarg.1
0x22002  stelem.ref
0x22003  ldloc.s  0xA
0x22005  ldc.i4.1
0x22006  ldarg.2
0x22007  stelem.ref
0x22008  ldloc.s  0xA
0x2200a  ldc.i4.2
0x2200b  ldarg.3
0x2200c  stelem.ref
0x2200d  ldloc.s  0xA
0x2200f  ldloc.1
0x22010  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x22015  ldloc.1
0x22016  ldc.i4.0
0x22017  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x2201c  rethrow
0x2201e  stloc.2
0x2201f  ldstr    aParseofficexml// "ParseOfficeXml"
0x22024  ldarg.0
0x22025  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x2202a  ldarg.0
0x2202b  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x22030  ldc.i4.3
0x22031  newarr   [mscorlib]System.String
0x22036  stloc.s  0xB
0x22038  ldloc.s  0xB
0x2203a  ldc.i4.0
0x2203b  ldstr    aBstrxml// "bstrXML"
0x22040  stelem.ref
0x22041  ldloc.s  0xB
0x22043  ldc.i4.1
0x22044  ldstr    aBstrprefix// "bstrPrefix"
0x22049  stelem.ref
0x2204a  ldloc.s  0xB
0x2204c  ldc.i4.2
0x2204d  ldstr    aP2dwriter// "p2DWriter"
0x22052  stelem.ref
0x22053  ldloc.s  0xB
0x22055  ldc.i4.3
0x22056  newarr   [mscorlib]System.Object
0x2205b  stloc.s  0xC
0x2205d  ldloc.s  0xC
0x2205f  ldc.i4.0
0x22060  ldarg.1
0x22061  stelem.ref
0x22062  ldloc.s  0xC
0x22064  ldc.i4.1
0x22065  ldarg.2
0x22066  stelem.ref
0x22067  ldloc.s  0xC
0x22069  ldc.i4.2
0x2206a  ldarg.3
0x2206b  stelem.ref
0x2206c  ldloc.s  0xC
0x2206e  ldloc.2
0x2206f  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x22074  ldloc.2
0x22075  ldarg.0
0x22076  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x2207b  ldarg.0
0x2207c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x22081  ldarg.0
0x22082  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x22087  ldarg.0
0x22088  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x2208d  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x22092  rethrow
0x22094  stloc.3
0x22095  ldstr    aParseofficexml// "ParseOfficeXml"
0x2209a  ldarg.0
0x2209b  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x220a0  ldarg.0
0x220a1  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x220a6  ldc.i4.3
0x220a7  newarr   [mscorlib]System.String
0x220ac  stloc.s  0xD
0x220ae  ldloc.s  0xD
0x220b0  ldc.i4.0
0x220b1  ldstr    aBstrxml// "bstrXML"
0x220b6  stelem.ref
0x220b7  ldloc.s  0xD
0x220b9  ldc.i4.1
0x220ba  ldstr    aBstrprefix// "bstrPrefix"
0x220bf  stelem.ref
0x220c0  ldloc.s  0xD
0x220c2  ldc.i4.2
0x220c3  ldstr    aP2dwriter// "p2DWriter"
0x220c8  stelem.ref
0x220c9  ldloc.s  0xD
0x220cb  ldc.i4.3
0x220cc  newarr   [mscorlib]System.Object
0x220d1  stloc.s  0xE
0x220d3  ldloc.s  0xE
0x220d5  ldc.i4.0
0x220d6  ldarg.1
0x220d7  stelem.ref
0x220d8  ldloc.s  0xE
0x220da  ldc.i4.1
0x220db  ldarg.2
0x220dc  stelem.ref
0x220dd  ldloc.s  0xE
0x220df  ldc.i4.2
0x220e0  ldarg.3
0x220e1  stelem.ref
0x220e2  ldloc.s  0xE
0x220e4  ldloc.3
0x220e5  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x220ea  ldloc.3
0x220eb  ldarg.0
0x220ec  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x220f1  ldarg.0
0x220f2  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTraceOnRelease
0x220f7  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestNullReferenceException(class [mscorlib]System.NullReferenceException nullEx, string stackTraceOnCreate, string stackTraceOnRelease)
0x220fc  rethrow
0x220fe  stloc.s  4
0x22100  ldstr    aParseofficexml// "ParseOfficeXml"
0x22105  ldarg.0
0x22106  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x2210b  ldarg.0
0x2210c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x22111  ldc.i4.3
0x22112  newarr   [mscorlib]System.String
0x22117  stloc.s  0xF
0x22119  ldloc.s  0xF
0x2211b  ldc.i4.0
0x2211c  ldstr    aBstrxml// "bstrXML"
0x22121  stelem.ref
0x22122  ldloc.s  0xF
0x22124  ldc.i4.1
0x22125  ldstr    aBstrprefix// "bstrPrefix"
0x2212a  stelem.ref
0x2212b  ldloc.s  0xF
0x2212d  ldc.i4.2
0x2212e  ldstr    aP2dwriter// "p2DWriter"
0x22133  stelem.ref
0x22134  ldloc.s  0xF
0x22136  ldc.i4.3
0x22137  newarr   [mscorlib]System.Object
0x2213c  stloc.s  0x10
0x2213e  ldloc.s  0x10
0x22140  ldc.i4.0
0x22141  ldarg.1
0x22142  stelem.ref
0x22143  ldloc.s  0x10
0x22145  ldc.i4.1
0x22146  ldarg.2
0x22147  stelem.ref
0x22148  ldloc.s  0x10
0x2214a  ldc.i4.2
0x2214b  ldarg.3
0x2214c  stelem.ref
0x2214d  ldloc.s  0x10
0x2214f  ldloc.s  4
0x22151  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x22156  rethrow
0x22158  leave.s  loc_22169
0x2215a  ldarg.0
0x2215b  dup
0x2215c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x22161  ldc.i4.1
0x22162  sub
0x22163  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x22168  endfinally
0x22169  leave.s  loc_22177
0x2216b  ldloc.s  6
0x2216d  brfalse.s loc_22176
0x2216f  ldloc.s  6
0x22171  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22176  endfinally
0x22177  ret
```
