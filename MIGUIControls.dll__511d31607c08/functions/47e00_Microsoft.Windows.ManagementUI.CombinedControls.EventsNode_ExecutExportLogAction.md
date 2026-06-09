# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecutExportLogAction

- ea: `0x47e00`
- end: `0x48062`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecutExportLogAction`
- size: `610`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x473f0`
- `0x47b70`

## callees

- `0x33aa0`
- `0x33bb0`
- `0x35ab0`
- `0x35b10`
- `0x35b70`
- `0x35d60`
- `0x386b0`
- `0x38840`
- `0x40d50`
- `0x46140`
- `0x461b0`
- `0x46b70`
- `0x46e70`
- `0x46f20`
- `0x47e00`
- `0x53fc0`
- `0x9ae00`
- `0x9ae40`
- `0x9af00`

## string_xrefs

- `0x47e71`: `ExecutExportLogAction: Got path '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x47e00  ldc.i4.0
0x47e01  stloc.0
0x47e02  ldsfld   string [mscorlib]System.String::Empty
0x47e07  stloc.1
0x47e08  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x47e0d  stloc.2
0x47e0e  ldc.i4.1
0x47e0f  stloc.3
0x47e10  ldarg.0
0x47e11  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::m_nodeType
0x47e16  ldc.i4.6
0x47e17  bne.un.s loc_47E2E
0x47e19  ldarg.0
0x47e1a  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ChannelPath()
0x47e1f  ldstr    aEtl// "etl"
0x47e24  ldc.i4.5
0x47e25  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x47e2a  brfalse.s loc_47E2E
0x47e2c  ldc.i4.0
0x47e2d  stloc.3
0x47e2e  ldc.i4.0
0x47e2f  stloc.s  4
0x47e31  ldarg.0
0x47e32  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x47e37  brtrue   loc_48059
0x47e3c  ldarg.0
0x47e3d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeContext()
0x47e42  br       loc_48059
0x47e47  ldc.i4.1
0x47e48  stloc.s  4
0x47e4a  ldarg.1
0x47e4b  brfalse.s loc_47E6B
0x47e4d  ldc.i4.0
0x47e4e  ldloca.s 1
0x47e50  ldc.i4.1
0x47e51  ldc.i4.0
0x47e52  ldloc.3
0x47e53  ldarg.0
0x47e54  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x47e59  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_IsLocalContext()
0x47e5e  ldc.i4.0
0x47e5f  ceq
0x47e61  ldloca.s 2
0x47e63  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetSaveLogFileNameAndLocales(bool clearLog, [out] string& fileName, bool modal, bool suppressElf, bool showLocalized, bool getUncPath, class [mscorlib]System.Collections.ArrayList& locales)
0x47e68  stloc.0
0x47e69  br.s     loc_47E6F
0x47e6b  ldarg.2
0x47e6c  stloc.1
0x47e6d  ldc.i4.1
0x47e6e  stloc.0
0x47e6f  ldarg.0
0x47e70  ldnull
0x47e71  ldstr    aExecutexportlo// "ExecutExportLogAction: Got path '{0}'"
0x47e76  ldc.i4.1
0x47e77  newarr   [mscorlib]System.Object
0x47e7c  dup
0x47e7d  ldc.i4.0
0x47e7e  ldloc.1
0x47e7f  stelem.ref
0x47e80  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x47e85  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0x47e8a  ldloc.0
0x47e8b  brfalse.s loc_47EF8
0x47e8d  ldarg.0
0x47e8e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x47e93  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_IsLocalContext()
0x47e98  brtrue.s loc_47EF8
0x47e9a  ldloc.1
0x47e9b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x47ea0  brfalse.s loc_47EF8
0x47ea2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x47ea7  stloc.s  5
0x47ea9  ldloc.s  5
0x47eab  ldnull
0x47eac  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::get_SaveLogFromRemoteUncPathError()
0x47eb1  ldc.i4.0
0x47eb2  newarr   [mscorlib]System.Object
0x47eb7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x47ebc  pop
0x47ebd  ldloc.s  5
0x47ebf  call     string [mscorlib]System.Environment::get_NewLine()
0x47ec4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x47ec9  pop
0x47eca  ldloc.s  5
0x47ecc  call     string [mscorlib]System.Environment::get_NewLine()
0x47ed1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x47ed6  pop
0x47ed7  ldloc.s  5
0x47ed9  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::get_RemoteExportFailElfExplanation()
0x47ede  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x47ee3  pop
0x47ee4  ldloc.s  5
0x47ee6  callvirt instance string [mscorlib]System.Object::ToString()
0x47eeb  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x47ef0  ldc.i4.0
0x47ef1  stloc.s  4
0x47ef3  br       loc_48059
0x47ef8  ldloc.0
0x47ef9  brfalse  loc_48057
0x47efe  ldloc.1
0x47eff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x47f04  brtrue   loc_48057
0x47f09  call     void [System.Windows.Forms]System.Windows.Forms.Application::DoEvents()
0x47f0e  ldloc.1
0x47f0f  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x47f14  ldstr    aEvtx// "evtx"
0x47f19  ldc.i4.5
0x47f1a  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x47f1f  brfalse  loc_47FDD
0x47f24  ldarg.3
0x47f25  ldarg.s  4
0x47f27  ldloc.1
0x47f28  ldarg.0
0x47f29  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ContextPtr()
0x47f2e  ldloc.3
0x47f2f  ldc.i4.0
0x47f30  ceq
0x47f32  call     void Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::ExportLog(string strChannel, string query, string fileName, native int session, bool useTracerpt)
0x47f37  leave.s  loc_47FA6
0x47f39  stloc.s  6
0x47f3b  ldc.i4.1
0x47f3c  stloc.s  4
0x47f3e  ldc.i4.0
0x47f3f  stloc.0
0x47f40  ldarg.0
0x47f41  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x47f46  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_IsLocalContext()
0x47f4b  brtrue.s loc_47F9D
0x47f4d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x47f52  stloc.s  7
0x47f54  ldloc.s  7
0x47f56  ldnull
0x47f57  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::get_RemoteExportFailFormatString()
0x47f5c  ldc.i4.2
0x47f5d  newarr   [mscorlib]System.Object
0x47f62  dup
0x47f63  ldc.i4.0
0x47f64  ldarg.0
0x47f65  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x47f6a  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_RemoteComputer()
0x47f6f  stelem.ref
0x47f70  dup
0x47f71  ldc.i4.1
0x47f72  ldloc.1
0x47f73  stelem.ref
0x47f74  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x47f79  pop
0x47f7a  ldloc.s  7
0x47f7c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x47f81  pop
0x47f82  ldloc.s  7
0x47f84  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::get_RemoteExportFailElfExplanation()
0x47f89  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x47f8e  pop
0x47f8f  ldloc.s  7
0x47f91  callvirt instance string [mscorlib]System.Object::ToString()
0x47f96  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x47f9b  br.s     loc_47FA4
0x47f9d  ldloc.s  6
0x47f9f  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(class [System]System.ComponentModel.Win32Exception ex)
0x47fa4  leave.s  loc_47FA6
0x47fa6  ldloc.0
0x47fa7  brfalse  loc_48044
0x47fac  ldc.i4.0
0x47fad  stloc.s  8
0x47faf  br.s     loc_47FD1
0x47fb1  ldloc.2
0x47fb2  ldloc.s  8
0x47fb4  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x47fb9  unbox.any [mscorlib]System.Int32
0x47fbe  ldloc.1
0x47fbf  ldarg.0
0x47fc0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x47fc5  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::LocalizeExportedLog(int32 locale, string fileName, class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext ctx)
0x47fca  stloc.0
0x47fcb  ldloc.s  8
0x47fcd  ldc.i4.1
0x47fce  add
0x47fcf  stloc.s  8
0x47fd1  ldloc.s  8
0x47fd3  ldloc.2
0x47fd4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x47fd9  blt.s    loc_47FB1
0x47fdb  br.s     loc_48044
0x47fdd  ldc.i4.m1
0x47fde  stloc.s  9
0x47fe0  ldloc.1
0x47fe1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x47fe6  brtrue.s loc_48003
0x47fe8  ldloc.1
0x47fe9  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x47fee  ldstr    aXml// "xml"
0x47ff3  ldc.i4.1
0x47ff4  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x47ff9  brfalse.s loc_48003
0x47ffb  ldc.i4.1
0x47ffc  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetLocaleInfoForXmlExport(bool modal)
0x48001  stloc.s  9
0x48003  ldarg.0
0x48004  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x48009  ldarg.0
0x4800a  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ChannelPath()
0x4800f  ldarg.0
0x48010  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::filtered
0x48015  brtrue.s loc_4801F
0x48017  ldarg.0
0x48018  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Query()
0x4801d  br.s     loc_4802F
0x4801f  ldarg.0
0x48020  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::filteredQry
0x48025  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Query()
0x4802a  callvirt instance string [mscorlib]System.Object::ToString()
0x4802f  ldloc.1
0x48030  ldarg.0
0x48031  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ResultsConfig()
0x48036  ldarg.0
0x48037  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::viewConfig
0x4803c  ldloc.s  9
0x4803e  call     bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::SaveLogFileAsync(class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext ctx, string strChannel, string qry, string fileName, string resultsConfig, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig cfg, int32 locale)
0x48043  stloc.0
0x48044  leave.s  loc_48059
0x48046  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4804b  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x48050  ldc.i4.0
0x48051  stloc.0
0x48052  ldc.i4.0
0x48053  stloc.s  4
0x48055  leave.s  loc_48059
0x48057  ldc.i4.0
0x48058  stloc.0
0x48059  ldloc.s  4
0x4805b  brfalse  loc_47E47
0x48060  ldloc.0
0x48061  ret
```
