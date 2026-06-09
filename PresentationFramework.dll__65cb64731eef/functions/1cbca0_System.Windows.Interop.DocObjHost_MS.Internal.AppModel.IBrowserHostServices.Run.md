# System.Windows.Interop.DocObjHost::MS.Internal.AppModel.IBrowserHostServices.Run

- ea: `0x1cbca0`
- end: `0x1cbf3d`
- name: `System.Windows.Interop.DocObjHost::MS.Internal.AppModel.IBrowserHostServices.Run`
- size: `669`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callees

- `0x38c40`
- `0x1cac50`
- `0x1cb910`
- `0x1cbca0`
- `0x1cbf40`
- `0x1cc480`
- `0x1cc500`
- `0x1cc5f0`
- `0x1cc760`
- `0x1cc870`
- `0x1cc8e0`
- `0x23ec10`
- `0x23ed30`
- `0x23f850`
- `0x240160`
- `0x240170`
- `0x2401b0`
- `0x2402e0`
- `0x2439b0`
- `0x27a4e0`

## string_xrefs

- `0x1cbca9`: `path string should not be null or empty when Run method is called.`
- `0x1cbecb`: `http://support.microsoft.com/kb/954494`

## pseudocode

```c

```

## disassembly

```asm
0x1cbca0  ldarg.1
0x1cbca1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1cbca6  ldc.i4.0
0x1cbca7  ceq
0x1cbca9  ldstr    aPathStringShou// "path string should not be null or empty"...
0x1cbcae  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1cbcb3  ldarg.3
0x1cbcb4  ldc.i4.0
0x1cbcb5  cgt.un
0x1cbcb7  ldstr    aUnknownMimeTyp// "Unknown mime type"
0x1cbcbc  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1cbcc1  ldc.i4   0x402
0x1cbcc6  ldc.i4   0x2379
0x1cbccb  ldstr    asc_29CCCE// "\""
0x1cbcd0  ldarg.1
0x1cbcd1  ldstr    asc_29CCCE// "\""
0x1cbcd6  call     string [mscorlib]System.String::Concat(string, string, string)
0x1cbcdb  ldstr    asc_29CCCE// "\""
0x1cbce0  ldarg.s  5
0x1cbce2  ldstr    asc_29CCCE// "\""
0x1cbce7  call     string [mscorlib]System.String::Concat(string, string, string)
0x1cbcec  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event, object, object)
0x1cbcf1  ldc.i4.0
0x1cbcf2  stloc.0
0x1cbcf3  ldarg.0
0x1cbcf4  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class InitData> System.Windows.Interop.DocObjHost::_initData
0x1cbcf9  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class InitData>::get_Value()
0x1cbcfe  stloc.1
0x1cbcff  ldloc.1
0x1cbd00  ldarg.s  0xE
0x1cbd02  stfld    class MS.Internal.AppModel.IHostBrowser InitData::HostBrowser
0x1cbd07  ldloc.1
0x1cbd08  ldarg.2
0x1cbd09  stfld    string InitData::Fragment
0x1cbd0e  ldloc.1
0x1cbd0f  ldarg.s  7
0x1cbd11  stfld    object InitData::UcomLoadIStream
0x1cbd16  ldloc.1
0x1cbd17  ldc.i4.1
0x1cbd18  stfld    bool InitData::HandleHistoryLoad
0x1cbd1d  ldloc.1
0x1cbd1e  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<valuetype MS.Internal.AppModel.MimeType> InitData::MimeType
0x1cbd23  ldarg.3
0x1cbd24  call     instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<valuetype MS.Internal.AppModel.MimeType>::set_Value(var<u1>)
0x1cbd29  ldnull
0x1cbd2a  stloc.2
0x1cbd2b  ldarg.s  0xE
0x1cbd2d  ldloca.s 2
0x1cbd2f  callvirt instance valuetype [WindowsBase]MS.Internal.Interop.HRESULT MS.Internal.AppModel.IHostBrowser::GetUserAgentString([out] string& userAgent)
0x1cbd34  stloc.3
0x1cbd35  ldloc.3
0x1cbd36  ldsfld   valuetype [WindowsBase]MS.Internal.Interop.HRESULT [WindowsBase]MS.Internal.Interop.HRESULT::E_OUTOFMEMORY
0x1cbd3b  call     bool [WindowsBase]MS.Internal.Interop.HRESULT::op_Equality(valuetype [WindowsBase]MS.Internal.Interop.HRESULT, valuetype [WindowsBase]MS.Internal.Interop.HRESULT)
0x1cbd40  brfalse.s loc_1CBD54
0x1cbd42  ldarg.s  8
0x1cbd44  ldc.i4.3
0x1cbd45  and
0x1cbd46  brfalse.s loc_1CBD54
0x1cbd48  call     string [WindowsBase]MS.Win32.UnsafeNativeMethods::ObtainUserAgentString()
0x1cbd4d  stloc.2
0x1cbd4e  ldsfld   valuetype [WindowsBase]MS.Internal.Interop.HRESULT [WindowsBase]MS.Internal.Interop.HRESULT::S_OK
0x1cbd53  stloc.3
0x1cbd54  ldloca.s 3
0x1cbd56  call     instance void [WindowsBase]MS.Internal.Interop.HRESULT::ThrowIfFailed()
0x1cbd5b  ldloc.1
0x1cbd5c  ldloc.2
0x1cbd5d  stfld    string InitData::UserAgentString
0x1cbd62  ldloc.1
0x1cbd63  ldarg.s  8
0x1cbd65  stfld    valuetype MS.Internal.AppModel.HostingFlags InitData::HostingFlags
0x1cbd6a  ldarg.1
0x1cbd6b  newobj   instance void [System]System.UriBuilder::.ctor(string)
0x1cbd70  call     instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x1cbd75  stloc.s  4
0x1cbd77  ldloc.1
0x1cbd78  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class [System]System.Uri> InitData::ActivationUri
0x1cbd7d  ldloc.s  4
0x1cbd7f  call     instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class [System]System.Uri>::set_Value(var<u1>)
0x1cbd84  ldloc.s  4
0x1cbd86  call     void System.Windows.Interop.PresentationAppDomainManager::set_ActivationUri(class [System]System.Uri value)
0x1cbd8b  ldc.i4.1
0x1cbd8c  call     void System.Windows.Interop.BrowserInteropHelper::SetBrowserHosted(bool value)
0x1cbd91  ldarg.s  8
0x1cbd93  ldc.i4.s 0x20
0x1cbd95  and
0x1cbd96  brfalse.s loc_1CBDD3
0x1cbd98  ldarg.0
0x1cbd99  ldfld    class MS.Internal.AppModel.IBrowserCallbackServices System.Windows.Interop.DocObjHost::_browserCallbackServices
0x1cbd9e  ldc.i4.0
0x1cbd9f  callvirt instance bool MS.Internal.AppModel.IBrowserCallbackServices::ChangeDownloadState([hasfieldmarshal] bool)
0x1cbda4  pop
0x1cbda5  ldarg.0
0x1cbda6  ldfld    class MS.Internal.AppModel.IBrowserCallbackServices System.Windows.Interop.DocObjHost::_browserCallbackServices
0x1cbdab  ldc.i4.m1
0x1cbdac  conv.i8
0x1cbdad  ldc.i4.0
0x1cbdae  conv.i8
0x1cbdaf  callvirt instance bool MS.Internal.AppModel.IBrowserCallbackServices::UpdateProgress([hasfieldmarshal] int64, [in] [hasfieldmarshal] int64 cBytesCompleted)
0x1cbdb4  pop
0x1cbdb5  ldarg.0
0x1cbdb6  call     instance void System.Windows.Interop.DocObjHost::EnableErrorPage()
0x1cbdbb  ldarg.0
0x1cbdbc  ldarg.1
0x1cbdbd  ldarg.s  4
0x1cbdbf  newobj   instance void System.Windows.Interop.ApplicationLauncherXappDebug::.ctor(string path, string debugSecurityZoneURL)
0x1cbdc4  call     instance class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.ApplicationLauncherXappDebug::Initialize()
0x1cbdc9  stfld    class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::_appProxyInternal
0x1cbdce  br       loc_1CBE92
0x1cbdd3  ldarg.3
0x1cbdd4  ldc.i4.1
0x1cbdd5  sub
0x1cbdd6  switch   loc_1CBDEC, loc_1CBE55, loc_1CBE39
0x1cbde7  br       loc_1CBE90
0x1cbdec  ldarg.0
0x1cbded  ldarg.0
0x1cbdee  call     instance class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::CreateAppDomainForXpsDocument()
0x1cbdf3  stfld    class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::_appProxyInternal
0x1cbdf8  ldarg.0
0x1cbdf9  ldfld    class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::_appProxyInternal
0x1cbdfe  brtrue.s loc_1CBE04
0x1cbe00  ldc.i4.m1
0x1cbe01  stloc.0
0x1cbe02  br.s     loc_1CBE2B
0x1cbe04  ldarg.s  6
0x1cbe06  brfalse.s loc_1CBE2B
0x1cbe08  ldarg.s  6
0x1cbe0a  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::GetIUnknownForObject(object)
0x1cbe0f  stloc.s  6
0x1cbe11  ldarg.0
0x1cbe12  ldfld    class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::_appProxyInternal
0x1cbe17  ldloc.s  6
0x1cbe19  box      [mscorlib]System.IntPtr
0x1cbe1e  callvirt instance void MS.Internal.AppModel.ApplicationProxyInternal::set_StreamContainer(object value)
0x1cbe23  ldloc.s  6
0x1cbe25  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::Release(native int)
0x1cbe2a  pop
0x1cbe2b  ldarg.0
0x1cbe2c  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class InitData> System.Windows.Interop.DocObjHost::_initData
0x1cbe31  ldnull
0x1cbe32  call     instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class InitData>::set_Value(var<u1>)
0x1cbe37  br.s     loc_1CBE92
0x1cbe39  ldarg.0
0x1cbe3a  ldarg.0
0x1cbe3b  ldloc.s  4
0x1cbe3d  call     instance class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::CreateAppDomainForLooseXaml(class [System]System.Uri uri)
0x1cbe42  stfld    class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::_appProxyInternal
0x1cbe47  ldarg.0
0x1cbe48  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class InitData> System.Windows.Interop.DocObjHost::_initData
0x1cbe4d  ldnull
0x1cbe4e  call     instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class InitData>::set_Value(var<u1>)
0x1cbe53  br.s     loc_1CBE92
0x1cbe55  ldloc.s  4
0x1cbe57  ldarg.s  5
0x1cbe59  ldarg.0
0x1cbe5a  ldfld    class MS.Internal.AppModel.IBrowserCallbackServices System.Windows.Interop.DocObjHost::_browserCallbackServices
0x1cbe5f  ldarg.0
0x1cbe60  ldftn    instance void System.Windows.Interop.DocObjHost::RunApplication(class ApplicationRunner runner)
0x1cbe66  newobj   instance void ApplicationRunnerCallback::.ctor(object object, native int method)
0x1cbe6b  ldarg.s  9
0x1cbe6d  ldarg.s  0xA
0x1cbe6f  ldarg.s  0xB
0x1cbe71  ldarg.s  0xC
0x1cbe73  ldarg.s  0xD
0x1cbe75  newobj   instance void MS.Internal.AppModel.XappLauncherApp::.ctor(class [System]System.Uri deploymentManifest, string applicationId, class MS.Internal.AppModel.IBrowserCallbackServices browser, class ApplicationRunnerCallback applicationRunner, class MS.Internal.AppModel.INativeProgressPage nativeProgressPage, string progressPageAssembly, string progressPageClass, string errorPageAssembly, string errorPageClass)
0x1cbe7a  stloc.s  5
0x1cbe7c  ldloc.1
0x1cbe7d  ldc.i4.0
0x1cbe7e  stfld    bool InitData::HandleHistoryLoad
0x1cbe83  ldarg.0
0x1cbe84  newobj   instance void MS.Internal.AppModel.ApplicationProxyInternal::.ctor()
0x1cbe89  stfld    class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::_appProxyInternal
0x1cbe8e  br.s     loc_1CBE92
0x1cbe90  ldc.i4.m1
0x1cbe91  stloc.0
0x1cbe92  ldloc.0
0x1cbe93  ldc.i4.m1
0x1cbe94  beq.s    loc_1CBEEA
0x1cbe96  ldarg.3
0x1cbe97  ldc.i4.1
0x1cbe98  beq.s    loc_1CBE9E
0x1cbe9a  ldarg.3
0x1cbe9b  ldc.i4.3
0x1cbe9c  bne.un.s loc_1CBEA4
0x1cbe9e  ldarg.0
0x1cbe9f  call     instance void System.Windows.Interop.DocObjHost::EnableErrorPage()
0x1cbea4  ldarg.0
0x1cbea5  call     instance bool System.Windows.Interop.DocObjHost::IsAffectedByCtfIssue()
0x1cbeaa  brfalse.s loc_1CBEDD
0x1cbeac  ldc.i4.m1
0x1cbead  stloc.0
0x1cbeae  ldarg.0
0x1cbeaf  ldfld    class MS.Internal.AppModel.IBrowserCallbackServices System.Windows.Interop.DocObjHost::_browserCallbackServices
0x1cbeb4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1cbeb9  ldstr    aAffectedbymsct// "AffectedByMsCtfIssue"
0x1cbebe  call     string System.Windows.SR::Get(string id)
0x1cbec3  ldc.i4.1
0x1cbec4  newarr   [mscorlib]System.Object
0x1cbec9  dup
0x1cbeca  ldc.i4.0
0x1cbecb  ldstr    aHttpSupportMic// "http://support.microsoft.com/kb/954494"
0x1cbed0  stelem.ref
0x1cbed1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1cbed6  callvirt instance void MS.Internal.AppModel.IBrowserCallbackServices::ProcessUnhandledException([in] [hasfieldmarshal] string pErrorMsg)
0x1cbedb  br.s     loc_1CBEEA
0x1cbedd  ldarg.0
0x1cbede  ldfld    class MS.Internal.AppModel.ApplicationProxyInternal System.Windows.Interop.DocObjHost::_appProxyInternal
0x1cbee3  ldloc.1
0x1cbee4  callvirt instance int32 MS.Internal.AppModel.ApplicationProxyInternal::Run(class InitData initData)
0x1cbee9  stloc.0
0x1cbeea  leave.s  loc_1CBF26
0x1cbeec  stloc.s  7
0x1cbeee  ldc.i4.m1
0x1cbeef  stloc.0
0x1cbef0  ldarg.0
0x1cbef1  ldfld    class MS.Internal.AppModel.IBrowserCallbackServices System.Windows.Interop.DocObjHost::_browserCallbackServices
0x1cbef6  ldloc.s  7
0x1cbef8  callvirt instance string [mscorlib]System.Object::ToString()
0x1cbefd  callvirt instance void MS.Internal.AppModel.IBrowserCallbackServices::ProcessUnhandledException([in] [hasfieldmarshal] string pErrorMsg)
0x1cbf02  rethrow
0x1cbf04  pop
0x1cbf05  ldc.i4.m1
0x1cbf06  stloc.0
0x1cbf07  ldarg.0
0x1cbf08  ldfld    class MS.Internal.AppModel.IBrowserCallbackServices System.Windows.Interop.DocObjHost::_browserCallbackServices
0x1cbf0d  ldstr    aNonclsactivati// "NonClsActivationException"
0x1cbf12  call     string System.Windows.SR::Get(string id)
0x1cbf17  callvirt instance void MS.Internal.AppModel.IBrowserCallbackServices::ProcessUnhandledException([in] [hasfieldmarshal] string pErrorMsg)
0x1cbf1c  rethrow
0x1cbf1e  ldarg.0
0x1cbf1f  ldloc.0
0x1cbf20  call     instance void System.Windows.Interop.DocObjHost::Cleanup(int32 exitCode)
0x1cbf25  endfinally
0x1cbf26  ldc.i4   0x402
0x1cbf2b  ldc.i4   0x237A
0x1cbf30  ldloc.0
0x1cbf31  box      [mscorlib]System.Int32
0x1cbf36  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event, object)
0x1cbf3b  ldloc.0
0x1cbf3c  ret
```
