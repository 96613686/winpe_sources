# System.Web.UI.PageRequestManager::RenderPageCallback

- ea: `0x117d0`
- end: `0x119ba`
- name: `System.Web.UI.PageRequestManager::RenderPageCallback`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `installer_update`

## callees

- `0xfec0`
- `0x107a0`
- `0x107b0`
- `0x107f0`
- `0x10820`
- `0x10830`
- `0x10880`
- `0x108a0`
- `0x10c20`
- `0x10c90`
- `0x10ca0`
- `0x10cb0`
- `0x10e80`
- `0x10e90`
- `0x11280`
- `0x11320`
- `0x113b0`
- `0x117d0`
- `0x119c0`
- `0x13d10`
- `0x14240`
- `0x3a830`
- `0x3a840`

## string_xrefs

- `0x118dd`: `updatePanelIDs`
- `0x118f3`: `childUpdatePanelIDs`

## pseudocode

```c

```

## disassembly

```asm
0x117d0  ldarg.0
0x117d1  call     instance void System.Web.UI.PageRequestManager::ProcessUpdatePanels()
0x117d6  ldarg.0
0x117d7  ldfld    class System.Web.UI.ScriptManager System.Web.UI.PageRequestManager::_owner
0x117dc  callvirt instance class System.Web.UI.IPage System.Web.UI.ScriptManager::get_IPage()
0x117e1  callvirt instance class System.Web.HttpResponseInternalBase System.Web.UI.IPage::get_Response()
0x117e6  stloc.0
0x117e7  ldloc.0
0x117e8  ldstr    aTextPlain// "text/plain"
0x117ed  callvirt instance void [System.Web]System.Web.HttpResponseBase::set_ContentType(string)
0x117f2  ldloc.0
0x117f3  callvirt instance class [System.Web]System.Web.HttpCachePolicyBase [System.Web]System.Web.HttpResponseBase::get_Cache()
0x117f8  callvirt instance void [System.Web]System.Web.HttpCachePolicyBase::SetNoServerCaching()
0x117fd  ldarg.1
0x117fe  ldstr    asc_4004E// "#"
0x11803  ldsfld   string [mscorlib]System.String::Empty
0x11808  ldstr    a4// "4"
0x1180d  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x11812  ldarg.0
0x11813  ldfld    class System.Web.UI.ScriptManager System.Web.UI.PageRequestManager::_owner
0x11818  callvirt instance class System.Web.UI.IPage System.Web.UI.ScriptManager::get_IPage()
0x1181d  callvirt instance class System.Web.UI.IHtmlForm System.Web.UI.IPage::get_Form()
0x11822  stloc.1
0x11823  ldloc.1
0x11824  ldarg.0
0x11825  ldftn    instance void System.Web.UI.PageRequestManager::RenderFormCallback(class [System.Web]System.Web.UI.HtmlTextWriter writer, class [System.Web]System.Web.UI.Control containerControl)
0x1182b  newobj   instance void [System.Web]System.Web.UI.RenderMethod::.ctor(object, native int)
0x11830  callvirt instance void System.Web.UI.IHtmlForm::SetRenderMethodDelegate(class [System.Web]System.Web.UI.RenderMethod renderMethod)
0x11835  ldarg.0
0x11836  ldarg.1
0x11837  stfld    class [System.Web]System.Web.UI.HtmlTextWriter System.Web.UI.PageRequestManager::_updatePanelWriter
0x1183c  newobj   instance void ParserHtmlTextWriter::.ctor()
0x11841  stloc.2
0x11842  ldloc.1
0x11843  ldloc.2
0x11844  callvirt instance void System.Web.UI.IHtmlForm::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x11849  ldarg.0
0x1184a  ldfld    class System.Web.UI.ScriptManager System.Web.UI.PageRequestManager::_owner
0x1184f  callvirt instance class System.Web.UI.IPage System.Web.UI.ScriptManager::get_IPage()
0x11854  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> System.Web.UI.IPage::get_HiddenFieldsToRender()
0x11859  stloc.3
0x1185a  ldloc.3
0x1185b  brfalse.s loc_118AE
0x1185d  ldloc.3
0x1185e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x11863  stloc.s  4
0x11865  br.s     loc_11897
0x11867  ldloc.s  4
0x11869  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x1186e  stloc.s  5
0x11870  ldloca.s 5
0x11872  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x11877  call     bool System.Web.UI.ControlUtil::IsBuiltInHiddenField(string hiddenFieldName)
0x1187c  brfalse.s loc_11897
0x1187e  ldarg.1
0x1187f  ldstr    aHiddenfield// "hiddenField"
0x11884  ldloca.s 5
0x11886  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1188b  ldloca.s 5
0x1188d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x11892  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x11897  ldloc.s  4
0x11899  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1189e  brtrue.s loc_11867
0x118a0  leave.s  loc_118AE
0x118a2  ldloc.s  4
0x118a4  brfalse.s loc_118AD
0x118a6  ldloc.s  4
0x118a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x118ad  endfinally
0x118ae  ldarg.1
0x118af  ldstr    aAsyncpostbackc// "asyncPostBackControlIDs"
0x118b4  ldsfld   string [mscorlib]System.String::Empty
0x118b9  ldarg.0
0x118ba  ldc.i4.0
0x118bb  call     instance string System.Web.UI.PageRequestManager::GetAsyncPostBackControlIDs(bool includeQuotes)
0x118c0  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x118c5  ldarg.1
0x118c6  ldstr    aPostbackcontro// "postBackControlIDs"
0x118cb  ldsfld   string [mscorlib]System.String::Empty
0x118d0  ldarg.0
0x118d1  ldc.i4.0
0x118d2  call     instance string System.Web.UI.PageRequestManager::GetPostBackControlIDs(bool includeQuotes)
0x118d7  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x118dc  ldarg.1
0x118dd  ldstr    aUpdatepanelids// "updatePanelIDs"
0x118e2  ldsfld   string [mscorlib]System.String::Empty
0x118e7  ldarg.0
0x118e8  call     instance string System.Web.UI.PageRequestManager::GetAllUpdatePanelIDs()
0x118ed  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x118f2  ldarg.1
0x118f3  ldstr    aChildupdatepan// "childUpdatePanelIDs"
0x118f8  ldsfld   string [mscorlib]System.String::Empty
0x118fd  ldarg.0
0x118fe  call     instance string System.Web.UI.PageRequestManager::GetChildUpdatePanelIDs()
0x11903  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x11908  ldarg.1
0x11909  ldstr    aPanelstorefres// "panelsToRefreshIDs"
0x1190e  ldsfld   string [mscorlib]System.String::Empty
0x11913  ldarg.0
0x11914  call     instance string System.Web.UI.PageRequestManager::GetRefreshingUpdatePanelIDs()
0x11919  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x1191e  ldarg.1
0x1191f  ldstr    aAsyncpostbackt// "asyncPostBackTimeout"
0x11924  ldsfld   string [mscorlib]System.String::Empty
0x11929  ldarg.0
0x1192a  ldfld    class System.Web.UI.ScriptManager System.Web.UI.PageRequestManager::_owner
0x1192f  callvirt instance int32 System.Web.UI.ScriptManager::get_AsyncPostBackTimeout()
0x11934  stloc.s  6
0x11936  ldloca.s 6
0x11938  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1193d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11942  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x11947  ldloc.2
0x11948  callvirt instance string ParserHtmlTextWriter::get_FormAction()
0x1194d  brfalse.s loc_11965
0x1194f  ldarg.1
0x11950  ldstr    aFormaction// "formAction"
0x11955  ldsfld   string [mscorlib]System.String::Empty
0x1195a  ldloc.2
0x1195b  callvirt instance string ParserHtmlTextWriter::get_FormAction()
0x11960  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x11965  ldarg.0
0x11966  ldfld    class System.Web.UI.ScriptManager System.Web.UI.PageRequestManager::_owner
0x1196b  callvirt instance class System.Web.UI.IPage System.Web.UI.ScriptManager::get_IPage()
0x11970  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlHead System.Web.UI.IPage::get_Header()
0x11975  brfalse.s loc_119A4
0x11977  ldarg.0
0x11978  ldfld    class System.Web.UI.ScriptManager System.Web.UI.PageRequestManager::_owner
0x1197d  callvirt instance class System.Web.UI.IPage System.Web.UI.ScriptManager::get_IPage()
0x11982  callvirt instance string System.Web.UI.IPage::get_Title()
0x11987  stloc.s  7
0x11989  ldloc.s  7
0x1198b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11990  brtrue.s loc_119A4
0x11992  ldarg.1
0x11993  ldstr    aPagetitle// "pageTitle"
0x11998  ldsfld   string [mscorlib]System.String::Empty
0x1199d  ldloc.s  7
0x1199f  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x119a4  ldarg.0
0x119a5  ldarg.1
0x119a6  call     instance void System.Web.UI.PageRequestManager::RenderDataItems(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x119ab  ldarg.0
0x119ac  ldarg.1
0x119ad  call     instance void System.Web.UI.PageRequestManager::ProcessScriptRegistration(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x119b2  ldarg.0
0x119b3  ldarg.1
0x119b4  call     instance void System.Web.UI.PageRequestManager::ProcessFocus(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x119b9  ret
```
