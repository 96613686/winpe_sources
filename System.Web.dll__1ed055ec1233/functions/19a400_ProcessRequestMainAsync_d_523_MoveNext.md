# <ProcessRequestMainAsync>d__523::MoveNext

- ea: `0x19a400`
- end: `0x19b4b6`
- name: `<ProcessRequestMainAsync>d__523::MoveNext`
- size: `4278`
- prototype: ``
- caller_count: `0`
- callee_count: `81`
- tags: `broker_com_uri`

## callees

- `0x83f0`
- `0xbf20`
- `0xbfa0`
- `0xe790`
- `0x160d0`
- `0x16180`
- `0x163c0`
- `0x163e0`
- `0x16a20`
- `0x17710`
- `0x1b730`
- `0x1bcd0`
- `0x1c550`
- `0x1c5e0`
- `0x1fd10`
- `0x2ae20`
- `0x2ea50`
- `0x2ebf0`
- `0x31470`
- `0x31650`
- `0x34fa0`
- `0x4f830`
- `0x4f880`
- `0x51900`
- `0x522c0`
- `0x58a00`
- `0x58a50`
- `0x5ef80`
- `0x5f490`
- `0x603a0`
- `0x60a40`
- `0x60b60`
- `0x60ef0`
- `0x71bd0`
- `0x71c00`
- `0x71e20`
- `0x72170`
- `0x72180`
- `0x721b0`
- `0x72600`
- `0x72780`
- `0x728a0`
- `0x728d0`
- `0x72af0`
- `0x72bc0`
- `0x72ca0`
- `0x72d60`
- `0x72de0`
- `0x73020`
- `0x739c0`

## string_xrefs

- `0x19a879`: `Begin InitComplete`
- `0x19a944`: `End InitComplete`
- `0x19af87`: `Begin LoadComplete`
- `0x19b054`: `End LoadComplete`
- `0x19b249`: `Begin PreRenderComplete`
- `0x19b271`: `End PreRenderComplete`
- `0x19b312`: `Begin SaveStateComplete`
- `0x19b33f`: `End SaveStateComplete`

## pseudocode

```c

```

## disassembly

```asm
0x19a400  ldarg.0
0x19a401  ldfld    int32 <ProcessRequestMainAsync>d__523::<>1__state
0x19a406  stloc.0
0x19a407  ldarg.0
0x19a408  ldfld    class System.Web.UI.Page <ProcessRequestMainAsync>d__523::<>4__this
0x19a40d  stloc.1
0x19a40e  ldloc.0
0x19a40f  ldc.i4.s 0xB
0x19a411  pop
0x19a412  pop
0x19a413  nop
0x19a414  ldloc.0
0x19a415  switch   loc_19A715, loc_19A800, loc_19A899, loc_19AA60, loc_19AB08, loc_19AC44, loc_19AD29, loc_19ADF7, loc_19AE9E, loc_19AFA7, loc_19B0C1, loc_19B17D
0x19a44a  ldarg.0
0x19a44b  ldloc.1
0x19a44c  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x19a451  stfld    class System.Web.HttpContext <ProcessRequestMainAsync>d__523::<con>5__2
0x19a456  ldarg.0
0x19a457  ldnull
0x19a458  stfld    string <ProcessRequestMainAsync>d__523::<exportedWebPartID>5__3
0x19a45d  ldarg.0
0x19a45e  ldfld    bool <ProcessRequestMainAsync>d__523::includeStagesBeforeAsyncPoint
0x19a463  brfalse  loc_19B1E5
0x19a468  ldloc.1
0x19a469  call     instance bool System.Web.UI.Page::get_IsInAspCompatMode()
0x19a46e  brfalse.s loc_19A475
0x19a470  call     void System.Web.Util.AspCompatApplicationStep::OnPageStartSessionObjects()
0x19a475  ldloc.1
0x19a476  call     instance class System.Web.UI.Adapters.PageAdapter System.Web.UI.Page::get_PageAdapter()
0x19a47b  brfalse.s loc_19A4A9
0x19a47d  ldloc.1
0x19a47e  ldloc.1
0x19a47f  call     instance class System.Web.UI.Adapters.PageAdapter System.Web.UI.Page::get_PageAdapter()
0x19a484  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Adapters.PageAdapter::DeterminePostBackMode()
0x19a489  stfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a48e  ldloc.1
0x19a48f  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a494  brfalse.s loc_19A4C9
0x19a496  ldloc.1
0x19a497  ldloc.1
0x19a498  call     instance class System.Web.UI.Adapters.PageAdapter System.Web.UI.Page::get_PageAdapter()
0x19a49d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Adapters.PageAdapter::DeterminePostBackModeUnvalidated()
0x19a4a2  stfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_unvalidatedRequestValueCollection
0x19a4a7  br.s     loc_19A4C9
0x19a4a9  ldloc.1
0x19a4aa  ldloc.1
0x19a4ab  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::DeterminePostBackMode()
0x19a4b0  stfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a4b5  ldloc.1
0x19a4b6  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a4bb  brfalse.s loc_19A4C9
0x19a4bd  ldloc.1
0x19a4be  ldloc.1
0x19a4bf  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::DeterminePostBackModeUnvalidated()
0x19a4c4  stfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_unvalidatedRequestValueCollection
0x19a4c9  ldarg.0
0x19a4ca  ldsfld   string [mscorlib]System.String::Empty
0x19a4cf  stfld    string <ProcessRequestMainAsync>d__523::<callbackControlId>5__4
0x19a4d4  ldloc.1
0x19a4d5  call     instance bool System.Web.UI.Page::DetermineIsExportingWebPart()
0x19a4da  brfalse  loc_19A5A2
0x19a4df  call     class System.Web.Configuration.RuntimeConfig System.Web.Configuration.RuntimeConfig::GetAppConfig()
0x19a4e4  callvirt instance class System.Web.Configuration.WebPartsSection System.Web.Configuration.RuntimeConfig::get_WebParts()
0x19a4e9  callvirt instance bool System.Web.Configuration.WebPartsSection::get_EnableExport()
0x19a4ee  brtrue.s loc_19A500
0x19a4f0  ldstr    aWebpartexporth// "WebPartExportHandler_DisabledExportHand"...
0x19a4f5  call     string System.Web.SR::GetString(string name)
0x19a4fa  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x19a4ff  throw
0x19a500  ldarg.0
0x19a501  ldloc.1
0x19a502  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x19a507  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x19a50c  ldstr    aWebpart// "webPart"
0x19a511  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19a516  stfld    string <ProcessRequestMainAsync>d__523::<exportedWebPartID>5__3
0x19a51b  ldarg.0
0x19a51c  ldfld    string <ProcessRequestMainAsync>d__523::<exportedWebPartID>5__3
0x19a521  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19a526  brfalse.s loc_19A538
0x19a528  ldstr    aWebpartexporth_0// "WebPartExportHandler_InvalidArgument"
0x19a52d  call     string System.Web.SR::GetString(string name)
0x19a532  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x19a537  throw
0x19a538  ldloc.1
0x19a539  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x19a53e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x19a543  ldstr    aScope// "scope"
0x19a548  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19a54d  ldstr    aShared// "shared"
0x19a552  ldc.i4.5
0x19a553  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x19a558  brfalse.s loc_19A566
0x19a55a  ldloc.1
0x19a55b  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.Page::_pageFlags
0x19a560  ldc.i4.4
0x19a561  call     instance void System.Web.Util.SimpleBitVector32::Set(int32 bit)
0x19a566  ldloc.1
0x19a567  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x19a56c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x19a571  ldstr    aQuery// "query"
0x19a576  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19a57b  stloc.3
0x19a57c  ldloc.3
0x19a57d  brtrue.s loc_19A585
0x19a57f  ldsfld   string [mscorlib]System.String::Empty
0x19a584  stloc.3
0x19a585  ldloc.1
0x19a586  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x19a58b  ldloc.3
0x19a58c  callvirt instance void System.Web.HttpRequest::set_QueryStringText(string value)
0x19a591  ldarg.0
0x19a592  ldfld    class System.Web.HttpContext <ProcessRequestMainAsync>d__523::<con>5__2
0x19a597  callvirt instance class System.Web.TraceContext System.Web.HttpContext::get_Trace()
0x19a59c  ldc.i4.0
0x19a59d  callvirt instance void System.Web.TraceContext::set_IsEnabled(bool value)
0x19a5a2  ldloc.1
0x19a5a3  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a5a8  brfalse  loc_19A681
0x19a5ad  ldloc.1
0x19a5ae  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a5b3  ldstr    aViewstateencry// "__VIEWSTATEENCRYPTED"
0x19a5b8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19a5bd  brfalse.s loc_19A5C6
0x19a5bf  ldloc.1
0x19a5c0  ldc.i4.1
0x19a5c1  call     instance void System.Web.UI.Page::set_ContainsEncryptedViewState(bool value)
0x19a5c6  ldarg.0
0x19a5c7  ldloc.1
0x19a5c8  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a5cd  ldstr    aCallbackid// "__CALLBACKID"
0x19a5d2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19a5d7  stfld    string <ProcessRequestMainAsync>d__523::<callbackControlId>5__4
0x19a5dc  ldarg.0
0x19a5dd  ldfld    string <ProcessRequestMainAsync>d__523::<callbackControlId>5__4
0x19a5e2  brfalse.s loc_19A5FE
0x19a5e4  ldloc.1
0x19a5e5  ldfld    class System.Web.HttpRequest System.Web.UI.Page::_request
0x19a5ea  callvirt instance valuetype System.Web.HttpVerb System.Web.HttpRequest::get_HttpVerb()
0x19a5ef  ldc.i4.5
0x19a5f0  bne.un.s loc_19A5FE
0x19a5f2  ldloc.1
0x19a5f3  ldc.i4.1
0x19a5f4  stfld    bool System.Web.UI.Page::_isCallback
0x19a5f9  br       loc_19A681
0x19a5fe  ldloc.1
0x19a5ff  call     instance bool System.Web.UI.Page::get_IsCrossPagePostBack()
0x19a604  brtrue.s loc_19A681
0x19a606  ldnull
0x19a607  stloc.s  4
0x19a609  ldloc.1
0x19a60a  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a60f  ldstr    aPreviouspage// "__PREVIOUSPAGE"
0x19a614  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19a619  brfalse.s loc_19A681
0x19a61b  ldloc.1
0x19a61c  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x19a621  ldstr    aPreviouspage// "__PREVIOUSPAGE"
0x19a626  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19a62b  ldsfld   class System.Web.Security.Cryptography.Purpose System.Web.Security.Cryptography.Purpose::WebForms_Page_PreviousPageID
0x19a630  call     string System.Web.UI.Page::DecryptString(string s, class System.Web.Security.Cryptography.Purpose purpose)
0x19a635  call     class System.Web.VirtualPath System.Web.VirtualPath::CreateNonRelativeAllowNull(string virtualPath)
0x19a63a  stloc.s  4
0x19a63c  leave.s  loc_19A64E
0x19a63e  pop
0x19a63f  ldloc.1
0x19a640  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.Page::_pageFlags
0x19a645  ldc.i4.8
0x19a646  ldc.i4.1
0x19a647  call     instance void System.Web.Util.SimpleBitVector32::set_Item(int32 bit, bool value)
0x19a64c  leave.s  loc_19A64E
0x19a64e  ldloc.s  4
0x19a650  ldnull
0x19a651  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x19a656  brfalse.s loc_19A681
0x19a658  ldloc.s  4
0x19a65a  ldloc.1
0x19a65b  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x19a660  callvirt instance class System.Web.VirtualPath System.Web.HttpRequest::get_CurrentExecutionFilePathObject()
0x19a665  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x19a66a  brfalse.s loc_19A681
0x19a66c  ldloc.1
0x19a66d  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.Page::_pageFlags
0x19a672  ldc.i4.8
0x19a673  ldc.i4.1
0x19a674  call     instance void System.Web.Util.SimpleBitVector32::set_Item(int32 bit, bool value)
0x19a679  ldloc.1
0x19a67a  ldloc.s  4
0x19a67c  stfld    class System.Web.VirtualPath System.Web.UI.Page::_previousPagePath
0x19a681  ldloc.1
0x19a682  call     instance bool System.Web.UI.Page::get_MaintainScrollPositionOnPostBack()
0x19a687  brfalse.s loc_19A68F
0x19a689  ldloc.1
0x19a68a  call     instance void System.Web.UI.Page::LoadScrollPosition()
0x19a68f  ldarg.0
0x19a690  ldfld    class System.Web.HttpContext <ProcessRequestMainAsync>d__523::<con>5__2
0x19a695  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x19a69a  brfalse.s loc_19A6B1
0x19a69c  ldloc.1
0x19a69d  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x19a6a2  ldstr    aAspxPage// "aspx.page"
0x19a6a7  ldstr    aBeginPreinit// "Begin PreInit"
0x19a6ac  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x19a6b1  ldc.i4.5
0x19a6b2  ldc.i4.4
0x19a6b3  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x19a6b8  brfalse.s loc_19A6CC
0x19a6ba  ldc.i4.s 0x16
0x19a6bc  ldloc.1
0x19a6bd  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x19a6c2  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x19a6c7  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x19a6cc  ldloc.1
0x19a6cd  call     instance class [mscorlib]System.Threading.Tasks.Task System.Web.UI.Page::PerformPreInitAsync()
0x19a6d2  ldarg.0
0x19a6d3  ldfld    class System.Web.HttpContext <ProcessRequestMainAsync>d__523::<con>5__2
0x19a6d8  call     valuetype System.Web.Util.WithinCancellableCallbackTaskAwaitable System.Web.Util.TaskExtensions::WithinCancellableCallback(class [mscorlib]System.Threading.Tasks.Task task, class System.Web.HttpContext context)
0x19a6dd  stloc.s  6
0x19a6df  ldloca.s 6
0x19a6e1  call     instance valuetype WithinCancellableCallbackTaskAwaiter System.Web.Util.WithinCancellableCallbackTaskAwaitable::GetAwaiter()
0x19a6e6  stloc.s  5
0x19a6e8  ldloca.s 5
0x19a6ea  call     instance bool WithinCancellableCallbackTaskAwaiter::get_IsCompleted()
0x19a6ef  brtrue.s loc_19A732
0x19a6f1  ldarg.0
0x19a6f2  ldc.i4.0
0x19a6f3  dup
0x19a6f4  stloc.0
0x19a6f5  stfld    int32 <ProcessRequestMainAsync>d__523::<>1__state
0x19a6fa  ldarg.0
0x19a6fb  ldloc.s  5
0x19a6fd  stfld    valuetype WithinCancellableCallbackTaskAwaiter <ProcessRequestMainAsync>d__523::<>u__1
0x19a702  ldarg.0
0x19a703  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ProcessRequestMainAsync>d__523::<>t__builder
0x19a708  ldloca.s 5
0x19a70a  ldarg.0
0x19a70b  call     T0x2B000118
0x19a710  leave    loc_19B4B5
0x19a715  ldarg.0
0x19a716  ldfld    valuetype WithinCancellableCallbackTaskAwaiter <ProcessRequestMainAsync>d__523::<>u__1
0x19a71b  stloc.s  5
0x19a71d  ldarg.0
0x19a71e  ldflda   valuetype WithinCancellableCallbackTaskAwaiter <ProcessRequestMainAsync>d__523::<>u__1
0x19a723  initobj  WithinCancellableCallbackTaskAwaiter
0x19a729  ldarg.0
0x19a72a  ldc.i4.m1
0x19a72b  dup
0x19a72c  stloc.0
0x19a72d  stfld    int32 <ProcessRequestMainAsync>d__523::<>1__state
0x19a732  ldloca.s 5
0x19a734  call     instance void WithinCancellableCallbackTaskAwaiter::GetResult()
0x19a739  ldc.i4.5
0x19a73a  ldc.i4.4
0x19a73b  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x19a740  brfalse.s loc_19A754
0x19a742  ldc.i4.s 0x17
0x19a744  ldloc.1
0x19a745  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x19a74a  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x19a74f  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x19a754  ldarg.0
0x19a755  ldfld    class System.Web.HttpContext <ProcessRequestMainAsync>d__523::<con>5__2
0x19a75a  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x19a75f  brfalse.s loc_19A776
0x19a761  ldloc.1
0x19a762  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x19a767  ldstr    aAspxPage// "aspx.page"
0x19a76c  ldstr    aEndPreinit// "End PreInit"
0x19a771  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x19a776  ldarg.0
0x19a777  ldfld    class System.Web.HttpContext <ProcessRequestMainAsync>d__523::<con>5__2
0x19a77c  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x19a781  brfalse.s loc_19A798
0x19a783  ldloc.1
0x19a784  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x19a789  ldstr    aAspxPage// "aspx.page"
0x19a78e  ldstr    aBeginInit// "Begin Init"
0x19a793  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x19a798  ldc.i4.5
0x19a799  ldc.i4.4
0x19a79a  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x19a79f  brfalse.s loc_19A7B3
0x19a7a1  ldc.i4.s 0x18
0x19a7a3  ldloc.1
0x19a7a4  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x19a7a9  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x19a7ae  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x19a7b3  ldloc.1
0x19a7b4  ldnull
0x19a7b5  ldloc.1
0x19a7b6  call     instance class [mscorlib]System.Threading.Tasks.Task System.Web.UI.Control::InitRecursiveAsync(class System.Web.UI.Control namingContainer, class System.Web.UI.Page page)
0x19a7bb  stloc.2
0x19a7bc  ldloc.2
0x19a7bd  ldarg.0
0x19a7be  ldfld    class System.Web.HttpContext <ProcessRequestMainAsync>d__523::<con>5__2
0x19a7c3  call     valuetype System.Web.Util.WithinCancellableCallbackTaskAwaitable System.Web.Util.TaskExtensions::WithinCancellableCallback(class [mscorlib]System.Threading.Tasks.Task task, class System.Web.HttpContext context)
0x19a7c8  stloc.s  6
0x19a7ca  ldloca.s 6
0x19a7cc  call     instance valuetype WithinCancellableCallbackTaskAwaiter System.Web.Util.WithinCancellableCallbackTaskAwaitable::GetAwaiter()
0x19a7d1  stloc.s  7
  ... truncated ...
```
