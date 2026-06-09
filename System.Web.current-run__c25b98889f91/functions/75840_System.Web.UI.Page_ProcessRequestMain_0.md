# System.Web.UI.Page::ProcessRequestMain_0

- ea: `0x75840`
- end: `0x761a9`
- name: `System.Web.UI.Page::ProcessRequestMain_0`
- size: `2409`
- prototype: ``
- caller_count: `2`
- callee_count: `72`
- tags: `broker_com_uri`

## callers

- `0x75600`
- `0x75830`

## callees

- `0xbf20`
- `0xbfa0`
- `0xe790`
- `0x160d0`
- `0x16180`
- `0x163c0`
- `0x163e0`
- `0x16a20`
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
- `0x522c0`
- `0x58a00`
- `0x58a50`
- `0x5ef80`
- `0x5f490`
- `0x60280`
- `0x609b0`
- `0x60ab0`
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
- `0x741d0`
- `0x74470`
- `0x74510`
- `0x75180`
- `0x751e0`

## string_xrefs

- `0x75b58`: `Begin InitComplete`
- `0x75b80`: `End InitComplete`
- `0x75e82`: `Begin LoadComplete`
- `0x75eaa`: `End LoadComplete`
- `0x75fa5`: `Begin PreRenderComplete`
- `0x75fc8`: `End PreRenderComplete`
- `0x7605f`: `Begin SaveStateComplete`
- `0x76087`: `End SaveStateComplete`

## pseudocode

```c

```

## disassembly

```asm
0x75840  ldarg.0
0x75841  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x75846  stloc.0
0x75847  ldnull
0x75848  stloc.1
0x75849  ldarg.1
0x7584a  brfalse  loc_75F4B
0x7584f  ldarg.0
0x75850  call     instance bool System.Web.UI.Page::get_IsInAspCompatMode()
0x75855  brfalse.s loc_7585C
0x75857  call     void System.Web.Util.AspCompatApplicationStep::OnPageStartSessionObjects()
0x7585c  ldarg.0
0x7585d  call     instance class System.Web.UI.Adapters.PageAdapter System.Web.UI.Page::get_PageAdapter()
0x75862  brfalse.s loc_75890
0x75864  ldarg.0
0x75865  ldarg.0
0x75866  call     instance class System.Web.UI.Adapters.PageAdapter System.Web.UI.Page::get_PageAdapter()
0x7586b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Adapters.PageAdapter::DeterminePostBackMode()
0x75870  stfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x75875  ldarg.0
0x75876  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x7587b  brfalse.s loc_758B0
0x7587d  ldarg.0
0x7587e  ldarg.0
0x7587f  call     instance class System.Web.UI.Adapters.PageAdapter System.Web.UI.Page::get_PageAdapter()
0x75884  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Adapters.PageAdapter::DeterminePostBackModeUnvalidated()
0x75889  stfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_unvalidatedRequestValueCollection
0x7588e  br.s     loc_758B0
0x75890  ldarg.0
0x75891  ldarg.0
0x75892  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::DeterminePostBackMode()
0x75897  stfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x7589c  ldarg.0
0x7589d  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x758a2  brfalse.s loc_758B0
0x758a4  ldarg.0
0x758a5  ldarg.0
0x758a6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::DeterminePostBackModeUnvalidated()
0x758ab  stfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_unvalidatedRequestValueCollection
0x758b0  ldsfld   string [mscorlib]System.String::Empty
0x758b5  stloc.2
0x758b6  ldarg.0
0x758b7  call     instance bool System.Web.UI.Page::DetermineIsExportingWebPart()
0x758bc  brfalse  loc_75975
0x758c1  call     class System.Web.Configuration.RuntimeConfig System.Web.Configuration.RuntimeConfig::GetAppConfig()
0x758c6  callvirt instance class System.Web.Configuration.WebPartsSection System.Web.Configuration.RuntimeConfig::get_WebParts()
0x758cb  callvirt instance bool System.Web.Configuration.WebPartsSection::get_EnableExport()
0x758d0  brtrue.s loc_758E2
0x758d2  ldstr    aWebpartexporth// "WebPartExportHandler_DisabledExportHand"...
0x758d7  call     string System.Web.SR::GetString(string name)
0x758dc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x758e1  throw
0x758e2  ldarg.0
0x758e3  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x758e8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x758ed  ldstr    aWebpart// "webPart"
0x758f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x758f7  stloc.1
0x758f8  ldloc.1
0x758f9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x758fe  brfalse.s loc_75910
0x75900  ldstr    aWebpartexporth_0// "WebPartExportHandler_InvalidArgument"
0x75905  call     string System.Web.SR::GetString(string name)
0x7590a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7590f  throw
0x75910  ldarg.0
0x75911  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x75916  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x7591b  ldstr    aScope// "scope"
0x75920  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75925  ldstr    aShared// "shared"
0x7592a  ldc.i4.5
0x7592b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x75930  brfalse.s loc_7593E
0x75932  ldarg.0
0x75933  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.Page::_pageFlags
0x75938  ldc.i4.4
0x75939  call     instance void System.Web.Util.SimpleBitVector32::Set(int32 bit)
0x7593e  ldarg.0
0x7593f  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x75944  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_QueryString()
0x75949  ldstr    aQuery// "query"
0x7594e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75953  stloc.3
0x75954  ldloc.3
0x75955  brtrue.s loc_7595D
0x75957  ldsfld   string [mscorlib]System.String::Empty
0x7595c  stloc.3
0x7595d  ldarg.0
0x7595e  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x75963  ldloc.3
0x75964  callvirt instance void System.Web.HttpRequest::set_QueryStringText(string value)
0x75969  ldloc.0
0x7596a  callvirt instance class System.Web.TraceContext System.Web.HttpContext::get_Trace()
0x7596f  ldc.i4.0
0x75970  callvirt instance void System.Web.TraceContext::set_IsEnabled(bool value)
0x75975  ldarg.0
0x75976  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x7597b  brfalse  loc_75A4A
0x75980  ldarg.0
0x75981  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x75986  ldstr    aViewstateencry// "__VIEWSTATEENCRYPTED"
0x7598b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75990  brfalse.s loc_75999
0x75992  ldarg.0
0x75993  ldc.i4.1
0x75994  call     instance void System.Web.UI.Page::set_ContainsEncryptedViewState(bool value)
0x75999  ldarg.0
0x7599a  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x7599f  ldstr    aCallbackid// "__CALLBACKID"
0x759a4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x759a9  stloc.2
0x759aa  ldloc.2
0x759ab  brfalse.s loc_759C7
0x759ad  ldarg.0
0x759ae  ldfld    class System.Web.HttpRequest System.Web.UI.Page::_request
0x759b3  callvirt instance valuetype System.Web.HttpVerb System.Web.HttpRequest::get_HttpVerb()
0x759b8  ldc.i4.5
0x759b9  bne.un.s loc_759C7
0x759bb  ldarg.0
0x759bc  ldc.i4.1
0x759bd  stfld    bool System.Web.UI.Page::_isCallback
0x759c2  br       loc_75A4A
0x759c7  ldarg.0
0x759c8  call     instance bool System.Web.UI.Page::get_IsCrossPagePostBack()
0x759cd  brtrue.s loc_75A4A
0x759cf  ldnull
0x759d0  stloc.s  4
0x759d2  ldarg.0
0x759d3  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x759d8  ldstr    aPreviouspage// "__PREVIOUSPAGE"
0x759dd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x759e2  brfalse.s loc_75A4A
0x759e4  ldarg.0
0x759e5  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Web.UI.Page::_requestValueCollection
0x759ea  ldstr    aPreviouspage// "__PREVIOUSPAGE"
0x759ef  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x759f4  ldsfld   class System.Web.Security.Cryptography.Purpose System.Web.Security.Cryptography.Purpose::WebForms_Page_PreviousPageID
0x759f9  call     string System.Web.UI.Page::DecryptString(string s, class System.Web.Security.Cryptography.Purpose purpose)
0x759fe  call     class System.Web.VirtualPath System.Web.VirtualPath::CreateNonRelativeAllowNull(string virtualPath)
0x75a03  stloc.s  4
0x75a05  leave.s  loc_75A17
0x75a07  pop
0x75a08  ldarg.0
0x75a09  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.Page::_pageFlags
0x75a0e  ldc.i4.8
0x75a0f  ldc.i4.1
0x75a10  call     instance void System.Web.Util.SimpleBitVector32::set_Item(int32 bit, bool value)
0x75a15  leave.s  loc_75A17
0x75a17  ldloc.s  4
0x75a19  ldnull
0x75a1a  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x75a1f  brfalse.s loc_75A4A
0x75a21  ldloc.s  4
0x75a23  ldarg.0
0x75a24  call     instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x75a29  callvirt instance class System.Web.VirtualPath System.Web.HttpRequest::get_CurrentExecutionFilePathObject()
0x75a2e  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x75a33  brfalse.s loc_75A4A
0x75a35  ldarg.0
0x75a36  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.Page::_pageFlags
0x75a3b  ldc.i4.8
0x75a3c  ldc.i4.1
0x75a3d  call     instance void System.Web.Util.SimpleBitVector32::set_Item(int32 bit, bool value)
0x75a42  ldarg.0
0x75a43  ldloc.s  4
0x75a45  stfld    class System.Web.VirtualPath System.Web.UI.Page::_previousPagePath
0x75a4a  ldarg.0
0x75a4b  call     instance bool System.Web.UI.Page::get_MaintainScrollPositionOnPostBack()
0x75a50  brfalse.s loc_75A58
0x75a52  ldarg.0
0x75a53  call     instance void System.Web.UI.Page::LoadScrollPosition()
0x75a58  ldloc.0
0x75a59  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x75a5e  brfalse.s loc_75A75
0x75a60  ldarg.0
0x75a61  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x75a66  ldstr    aAspxPage// "aspx.page"
0x75a6b  ldstr    aBeginPreinit// "Begin PreInit"
0x75a70  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x75a75  ldc.i4.5
0x75a76  ldc.i4.4
0x75a77  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x75a7c  brfalse.s loc_75A90
0x75a7e  ldc.i4.s 0x16
0x75a80  ldarg.0
0x75a81  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x75a86  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x75a8b  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x75a90  ldarg.0
0x75a91  call     instance void System.Web.UI.Page::PerformPreInit()
0x75a96  ldc.i4.5
0x75a97  ldc.i4.4
0x75a98  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x75a9d  brfalse.s loc_75AB1
0x75a9f  ldc.i4.s 0x17
0x75aa1  ldarg.0
0x75aa2  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x75aa7  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x75aac  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x75ab1  ldloc.0
0x75ab2  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x75ab7  brfalse.s loc_75ACE
0x75ab9  ldarg.0
0x75aba  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x75abf  ldstr    aAspxPage// "aspx.page"
0x75ac4  ldstr    aEndPreinit// "End PreInit"
0x75ac9  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x75ace  ldloc.0
0x75acf  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x75ad4  brfalse.s loc_75AEB
0x75ad6  ldarg.0
0x75ad7  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x75adc  ldstr    aAspxPage// "aspx.page"
0x75ae1  ldstr    aBeginInit// "Begin Init"
0x75ae6  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x75aeb  ldc.i4.5
0x75aec  ldc.i4.4
0x75aed  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x75af2  brfalse.s loc_75B06
0x75af4  ldc.i4.s 0x18
0x75af6  ldarg.0
0x75af7  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x75afc  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x75b01  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x75b06  ldarg.0
0x75b07  ldnull
0x75b08  callvirt instance void System.Web.UI.Control::InitRecursive(class System.Web.UI.Control namingContainer)
0x75b0d  ldc.i4.5
0x75b0e  ldc.i4.4
0x75b0f  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x75b14  brfalse.s loc_75B28
0x75b16  ldc.i4.s 0x19
0x75b18  ldarg.0
0x75b19  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x75b1e  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x75b23  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x75b28  ldloc.0
0x75b29  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x75b2e  brfalse.s loc_75B45
0x75b30  ldarg.0
0x75b31  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x75b36  ldstr    aAspxPage// "aspx.page"
0x75b3b  ldstr    aEndInit// "End Init"
0x75b40  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x75b45  ldloc.0
0x75b46  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x75b4b  brfalse.s loc_75B62
0x75b4d  ldarg.0
0x75b4e  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x75b53  ldstr    aAspxPage// "aspx.page"
0x75b58  ldstr    aBeginInitcompl// "Begin InitComplete"
0x75b5d  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x75b62  ldarg.0
0x75b63  ldsfld   class [mscorlib]System.EventArgs [mscorlib]System.EventArgs::Empty
0x75b68  callvirt instance void System.Web.UI.Page::OnInitComplete(class [mscorlib]System.EventArgs e)
0x75b6d  ldloc.0
0x75b6e  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x75b73  brfalse.s loc_75B8A
0x75b75  ldarg.0
0x75b76  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x75b7b  ldstr    aAspxPage// "aspx.page"
0x75b80  ldstr    aEndInitcomplet// "End InitComplete"
0x75b85  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x75b8a  ldarg.0
0x75b8b  call     instance bool System.Web.UI.Page::get_IsPostBack()
0x75b90  brfalse  loc_75C80
0x75b95  ldloc.0
0x75b96  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x75b9b  brfalse.s loc_75BB2
0x75b9d  ldarg.0
0x75b9e  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
0x75ba3  ldstr    aAspxPage// "aspx.page"
0x75ba8  ldstr    aBeginLoadstate// "Begin LoadState"
0x75bad  callvirt instance void System.Web.TraceContext::Write(string category, string message)
0x75bb2  ldc.i4.5
0x75bb3  ldc.i4.4
0x75bb4  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x75bb9  brfalse.s loc_75BCD
0x75bbb  ldc.i4.s 0x1A
0x75bbd  ldarg.0
0x75bbe  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x75bc3  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x75bc8  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x75bcd  ldarg.0
0x75bce  call     instance void System.Web.UI.Page::LoadAllState()
0x75bd3  ldc.i4.5
0x75bd4  ldc.i4.4
0x75bd5  call     bool System.Web.EtwTrace::IsTraceEnabled(int32 level, int32 flag)
0x75bda  brfalse.s loc_75BEE
0x75bdc  ldc.i4.s 0x1B
0x75bde  ldarg.0
0x75bdf  ldfld    class System.Web.HttpContext System.Web.UI.Page::_context
0x75be4  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x75be9  call     void System.Web.EtwTrace::Trace(valuetype System.Web.EtwTraceType traceType, class System.Web.HttpWorkerRequest workerRequest)
0x75bee  ldloc.0
0x75bef  callvirt instance bool System.Web.HttpContext::get_TraceIsEnabled()
0x75bf4  brfalse.s loc_75C20
0x75bf6  ldarg.0
0x75bf7  call     instance class System.Web.TraceContext System.Web.UI.Page::get_Trace()
  ... truncated ...
```
