# <GetItemNameAsync>d__11::MoveNext

- ea: `0x71190`
- end: `0x7159a`
- name: `<GetItemNameAsync>d__11::MoveNext`
- size: `1034`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x3f960`
- `0x3f980`
- `0x3fd10`
- `0x70a30`
- `0x71190`

## string_xrefs

- `0x711f5`: `VSIDE`
- `0x71490`: `Received invalid results for extension id query: {0}`
- `0x714c0`: `Invalid results return for extension id query.`

## pseudocode

```c

```

## disassembly

```asm
0x71190  ldarg.0
0x71191  ldfld    int32 <GetItemNameAsync>d__11::<>1__state
0x71196  stloc.0
0x71197  ldarg.0
0x71198  ldfld    class Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService <GetItemNameAsync>d__11::<>4__this
0x7119d  stloc.1
0x7119e  ldloc.0
0x7119f  ldc.i4.1
0x711a0  ble.un.s loc_711E4
0x711a2  ldarg.0
0x711a3  ldflda   valuetype [mscorlib]System.Guid <GetItemNameAsync>d__11::<extensionId>5__2
0x711a8  initobj  [mscorlib]System.Guid
0x711ae  ldarg.0
0x711af  ldarg.0
0x711b0  ldfld    class [mscorlib]System.Version <GetItemNameAsync>d__11::instanceVersion
0x711b5  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsPriorTargetVersionExpansionSupported(class [mscorlib]System.Version)
0x711ba  stfld    bool <GetItemNameAsync>d__11::<allowPriorTarget>5__3
0x711bf  ldarg.0
0x711c0  ldloc.1
0x711c1  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry> Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::lazyTelemetry
0x711c6  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry>::get_Value()
0x711cb  dup
0x711cc  brtrue.s loc_711D2
0x711ce  pop
0x711cf  ldnull
0x711d0  br.s     loc_711DF
0x711d2  ldsfld   string Marketplace::GetItemNameEvent
0x711d7  ldnull
0x711d8  ldc.i4.0
0x711d9  ldc.i4.0
0x711da  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x711df  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetItemNameAsync>d__11::<telemetryOperation>5__4
0x711e4  nop
0x711e5  ldloc.0
0x711e6  ldc.i4.1
0x711e7  pop
0x711e8  pop
0x711e9  nop
0x711ea  ldloc.0
0x711eb  brfalse.s loc_71214
0x711ed  ldloc.0
0x711ee  ldc.i4.1
0x711ef  beq      loc_71392
0x711f4  ldarg.0
0x711f5  ldstr    aVside// "VSIDE"
0x711fa  ldsfld   string Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::VisualStudioMarketplaceBaseUri
0x711ff  newobj   instance void [System]System.Uri::.ctor(string)
0x71204  ldc.i4.0
0x71205  newobj   instance void [Microsoft.VisualStudio.Services.Common]Microsoft.VisualStudio.Services.Common.VssCredentials::.ctor(bool)
0x7120a  newobj   instance void UserAgentEnabledGalleryHttpClient::.ctor(string userAgent, class [System]System.Uri baseUrl, class [Microsoft.VisualStudio.Services.Common]Microsoft.VisualStudio.Services.Common.VssCredentials credentials)
0x7120f  stfld    class UserAgentEnabledGalleryHttpClient <GetItemNameAsync>d__11::<client>5__5
0x71214  nop
0x71215  ldloc.0
0x71216  brfalse  loc_712C9
0x7121b  ldloc.1
0x7121c  ldarg.0
0x7121d  ldfld    class UserAgentEnabledGalleryHttpClient <GetItemNameAsync>d__11::<client>5__5
0x71222  call     instance void Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::InitializeClient(class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.GalleryHttpClient client)
0x71227  newobj   instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQuery::.ctor()
0x7122c  dup
0x7122d  ldc.i4.0
0x7122e  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQuery::set_Flags(valuetype [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryFlags)
0x71233  dup
0x71234  ldc.i4.1
0x71235  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter>::.ctor(int32)
0x7123a  dup
0x7123b  newobj   instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter::.ctor()
0x71240  dup
0x71241  ldc.i4.1
0x71242  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria>::.ctor(int32)
0x71247  dup
0x71248  newobj   instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria::.ctor()
0x7124d  dup
0x7124e  ldc.i4.s 0x11
0x71250  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria::set_FilterType(int32)
0x71255  dup
0x71256  ldstr    aVsixid// "VsixId="
0x7125b  ldarg.0
0x7125c  ldfld    string <GetItemNameAsync>d__11::vsixId
0x71261  call     string [mscorlib]System.String::Concat(string, string)
0x71266  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria::set_Value(string)
0x7126b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria>::Add(var<u1>)
0x71270  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter::set_Criteria(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria>)
0x71275  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter>::Add(var<u1>)
0x7127a  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQuery::set_Filters(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter>)
0x7127f  stloc.3
0x71280  ldarg.0
0x71281  ldfld    class UserAgentEnabledGalleryHttpClient <GetItemNameAsync>d__11::<client>5__5
0x71286  ldloc.3
0x71287  ldnull
0x71288  ldnull
0x71289  ldnull
0x7128a  ldarg.0
0x7128b  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <GetItemNameAsync>d__11::token
0x71290  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult> [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.GalleryHttpClient::QueryExtensionsAsync(class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQuery, string, string, object, valuetype [mscorlib]System.Threading.CancellationToken)
0x71295  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult>::GetAwaiter()
0x7129a  stloc.s  6
0x7129c  ldloca.s 6
0x7129e  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult>::get_IsCompleted()
0x712a3  brtrue.s loc_712E6
0x712a5  ldarg.0
0x712a6  ldc.i4.0
0x712a7  dup
0x712a8  stloc.0
0x712a9  stfld    int32 <GetItemNameAsync>d__11::<>1__state
0x712ae  ldarg.0
0x712af  ldloc.s  6
0x712b1  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult> <GetItemNameAsync>d__11::<>u__1
0x712b6  ldarg.0
0x712b7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetItemNameAsync>d__11::<>t__builder
0x712bc  ldloca.s 6
0x712be  ldarg.0
0x712bf  call     T0x2B000311
0x712c4  leave    loc_71599
0x712c9  ldarg.0
0x712ca  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult> <GetItemNameAsync>d__11::<>u__1
0x712cf  stloc.s  6
0x712d1  ldarg.0
0x712d2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult> <GetItemNameAsync>d__11::<>u__1
0x712d7  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult>
0x712dd  ldarg.0
0x712de  ldc.i4.m1
0x712df  dup
0x712e0  stloc.0
0x712e1  stfld    int32 <GetItemNameAsync>d__11::<>1__state
0x712e6  ldloca.s 6
0x712e8  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult>::GetResult()
0x712ed  stloc.s  4
0x712ef  ldloc.1
0x712f0  ldloc.s  4
0x712f2  ldarg.0
0x712f3  ldfld    bool <GetItemNameAsync>d__11::<allowPriorTarget>5__3
0x712f8  ldloca.s 5
0x712fa  ldnull
0x712fb  call     instance bool Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::TryGetSingleExtension(class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult queryResult, bool allowPriorTarget, [out] class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.PublishedExtension& extension, [opt] string extensionName)
0x71300  brtrue.s loc_71349
0x71302  ldloc.1
0x71303  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger> Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::lazyLogger
0x71308  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger>::get_Value()
0x7130d  dup
0x7130e  brtrue.s loc_71313
0x71310  pop
0x71311  br.s     loc_7132C
0x71313  ldstr    aReceivedInvali// "Received invalid results for vsix id qu"...
0x71318  ldc.i4.1
0x71319  newarr   [mscorlib]System.Object
0x7131e  dup
0x7131f  ldc.i4.0
0x71320  ldarg.0
0x71321  ldfld    string <GetItemNameAsync>d__11::vsixId
0x71326  stelem.ref
0x71327  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x7132c  ldarg.0
0x7132d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetItemNameAsync>d__11::<telemetryOperation>5__4
0x71332  dup
0x71333  brtrue.s loc_71338
0x71335  pop
0x71336  br.s     loc_71342
0x71338  ldstr    aInvalidResults// "Invalid results returned for vsix id qu"...
0x7133d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x71342  ldnull
0x71343  stloc.2
0x71344  leave    loc_71585
0x71349  ldarg.0
0x7134a  ldloc.s  5
0x7134c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.PublishedExtension::get_ExtensionId()
0x71351  stfld    valuetype [mscorlib]System.Guid <GetItemNameAsync>d__11::<extensionId>5__2
0x71356  leave.s  loc_71370
0x71358  ldloc.0
0x71359  ldc.i4.0
0x7135a  bge.s    loc_7136F
0x7135c  ldarg.0
0x7135d  ldfld    class UserAgentEnabledGalleryHttpClient <GetItemNameAsync>d__11::<client>5__5
0x71362  brfalse.s loc_7136F
0x71364  ldarg.0
0x71365  ldfld    class UserAgentEnabledGalleryHttpClient <GetItemNameAsync>d__11::<client>5__5
0x7136a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7136f  endfinally
0x71370  ldarg.0
0x71371  ldnull
0x71372  stfld    class UserAgentEnabledGalleryHttpClient <GetItemNameAsync>d__11::<client>5__5
0x71377  ldarg.0
0x71378  ldsfld   string Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::VisualStudioMarketplaceBaseUri
0x7137d  newobj   instance void [System]System.Uri::.ctor(string)
0x71382  ldc.i4.0
0x71383  newobj   instance void [Microsoft.VisualStudio.Services.Common]Microsoft.VisualStudio.Services.Common.VssCredentials::.ctor(bool)
0x71388  newobj   instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.GalleryHttpClient::.ctor(class [System]System.Uri, class [Microsoft.VisualStudio.Services.Common]Microsoft.VisualStudio.Services.Common.VssCredentials)
0x7138d  stfld    class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.GalleryHttpClient <GetItemNameAsync>d__11::<client>5__6
0x71392  nop
0x71393  ldloc.0
0x71394  ldc.i4.1
0x71395  beq      loc_71446
0x7139a  ldloc.1
0x7139b  ldarg.0
0x7139c  ldfld    class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.GalleryHttpClient <GetItemNameAsync>d__11::<client>5__6
0x713a1  call     instance void Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::InitializeClient(class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.GalleryHttpClient client)
0x713a6  ldarg.0
0x713a7  ldfld    class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.GalleryHttpClient <GetItemNameAsync>d__11::<client>5__6
0x713ac  newobj   instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQuery::.ctor()
0x713b1  dup
0x713b2  ldc.i4.0
0x713b3  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQuery::set_Flags(valuetype [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryFlags)
0x713b8  dup
0x713b9  ldc.i4.1
0x713ba  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter>::.ctor(int32)
0x713bf  dup
0x713c0  newobj   instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter::.ctor()
0x713c5  dup
0x713c6  ldc.i4.1
0x713c7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria>::.ctor(int32)
0x713cc  dup
0x713cd  newobj   instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria::.ctor()
0x713d2  dup
0x713d3  ldc.i4.4
0x713d4  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria::set_FilterType(int32)
0x713d9  dup
0x713da  ldarg.0
0x713db  ldflda   valuetype [mscorlib]System.Guid <GetItemNameAsync>d__11::<extensionId>5__2
0x713e0  constrained. [mscorlib]System.Guid
0x713e6  callvirt instance string [mscorlib]System.Object::ToString()
0x713eb  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria::set_Value(string)
0x713f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria>::Add(var<u1>)
0x713f5  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter::set_Criteria(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.FilterCriteria>)
0x713fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter>::Add(var<u1>)
0x713ff  callvirt instance void [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQuery::set_Filters(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.QueryFilter>)
0x71404  ldnull
0x71405  ldnull
0x71406  ldnull
0x71407  ldarg.0
0x71408  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <GetItemNameAsync>d__11::token
0x7140d  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult> [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.GalleryHttpClient::QueryExtensionsAsync(class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQuery, string, string, object, valuetype [mscorlib]System.Threading.CancellationToken)
0x71412  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult>::GetAwaiter()
0x71417  stloc.s  6
0x71419  ldloca.s 6
0x7141b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult>::get_IsCompleted()
0x71420  brtrue.s loc_71463
0x71422  ldarg.0
0x71423  ldc.i4.1
0x71424  dup
0x71425  stloc.0
0x71426  stfld    int32 <GetItemNameAsync>d__11::<>1__state
0x7142b  ldarg.0
0x7142c  ldloc.s  6
0x7142e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult> <GetItemNameAsync>d__11::<>u__1
0x71433  ldarg.0
0x71434  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetItemNameAsync>d__11::<>t__builder
0x71439  ldloca.s 6
0x7143b  ldarg.0
0x7143c  call     T0x2B000311
0x71441  leave    loc_71599
0x71446  ldarg.0
0x71447  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult> <GetItemNameAsync>d__11::<>u__1
0x7144c  stloc.s  6
0x7144e  ldarg.0
0x7144f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult> <GetItemNameAsync>d__11::<>u__1
0x71454  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult>
0x7145a  ldarg.0
0x7145b  ldc.i4.m1
0x7145c  dup
0x7145d  stloc.0
0x7145e  stfld    int32 <GetItemNameAsync>d__11::<>1__state
0x71463  ldloca.s 6
0x71465  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult>::GetResult()
0x7146a  stloc.s  7
0x7146c  ldloc.1
0x7146d  ldloc.s  7
0x7146f  ldarg.0
0x71470  ldfld    bool <GetItemNameAsync>d__11::<allowPriorTarget>5__3
0x71475  ldloca.s 8
0x71477  ldnull
0x71478  call     instance bool Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::TryGetSingleExtension(class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.ExtensionQueryResult queryResult, bool allowPriorTarget, [out] class [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.WebApi.PublishedExtension& extension, [opt] string extensionName)
0x7147d  brtrue.s loc_714D1
0x7147f  ldloc.1
0x71480  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger> Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::lazyLogger
0x71485  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger>::get_Value()
0x7148a  dup
0x7148b  brtrue.s loc_71490
0x7148d  pop
0x7148e  br.s     loc_714B4
0x71490  ldstr    aReceivedInvali_0// "Received invalid results for extension "...
0x71495  ldc.i4.1
0x71496  newarr   [mscorlib]System.Object
0x7149b  dup
0x7149c  ldc.i4.0
0x7149d  ldarg.0
0x7149e  ldflda   valuetype [mscorlib]System.Guid <GetItemNameAsync>d__11::<extensionId>5__2
0x714a3  constrained. [mscorlib]System.Guid
0x714a9  callvirt instance string [mscorlib]System.Object::ToString()
0x714ae  stelem.ref
0x714af  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x714b4  ldarg.0
0x714b5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetItemNameAsync>d__11::<telemetryOperation>5__4
0x714ba  dup
0x714bb  brtrue.s loc_714C0
0x714bd  pop
0x714be  br.s     loc_714CA
0x714c0  ldstr    aInvalidResults_0// "Invalid results return for extension id"...
0x714c5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x714ca  ldnull
0x714cb  stloc.2
  ... truncated ...
```
