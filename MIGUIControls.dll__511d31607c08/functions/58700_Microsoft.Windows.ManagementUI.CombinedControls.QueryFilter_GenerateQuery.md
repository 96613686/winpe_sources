# Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GenerateQuery

- ea: `0x58700`
- end: `0x58a00`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GenerateQuery`
- size: `768`
- prototype: ``
- caller_count: `5`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x56540`
- `0x5a190`
- `0x5acc0`
- `0x5ad00`
- `0x5add0`

## callees

- `0x12ed0`
- `0x16310`
- `0x16350`
- `0x366d0`
- `0x4d630`
- `0x4d840`
- `0x4dca0`
- `0x4dce0`
- `0x4dfa0`
- `0x53a10`
- `0x53f00`
- `0x53fd0`
- `0x54110`
- `0x546a0`
- `0x55ea0`
- `0x57a90`
- `0x57c70`
- `0x57da0`
- `0x57f40`
- `0x580c0`
- `0x581f0`
- `0x58360`
- `0x584c0`
- `0x58700`

## string_xrefs

- `0x5876f`: `QueryErrorInvalidxml`
- `0x5877f`: `QueryErrorInvalidxml`

## pseudocode

```c

```

## disassembly

```asm
0x58700  ldarg.0
0x58701  ldc.i4.1
0x58702  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x58707  ldarg.0
0x58708  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::.ctor()
0x5870d  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x58712  ldsfld   string [mscorlib]System.String::Empty
0x58717  stloc.0
0x58718  ldsfld   string [mscorlib]System.String::Empty
0x5871d  stloc.1
0x5871e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::.ctor()
0x58723  stloc.2
0x58724  ldarg.0
0x58725  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x5872a  brfalse  loc_587C4
0x5872f  ldsfld   string [mscorlib]System.String::Empty
0x58734  stloc.3
0x58735  ldarg.0
0x58736  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x5873b  ldarg.0
0x5873c  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x58741  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_UserQuery(bool value)
0x58746  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x5874b  stloc.s  4
0x5874d  ldloc.s  4
0x5874f  ldarg.0
0x58750  ldfld    class [System.Windows.Forms]System.Windows.Forms.RichTextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::richTextBoxXml
0x58755  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x5875a  call     void Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::LoadXml(class [System.Xml]System.Xml.XmlDocument doc, string xml)
0x5875f  ldloc.s  4
0x58761  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x58766  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::.ctor(class [System.Xml]System.Xml.XmlElement evtQry)
0x5876b  stloc.2
0x5876c  leave.s  loc_5877C
0x5876e  pop
0x5876f  ldstr    aQueryerrorinva// "QueryErrorInvalidxml"
0x58774  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58779  stloc.3
0x5877a  leave.s  loc_5877C
0x5877c  leave.s  loc_5878C
0x5877e  pop
0x5877f  ldstr    aQueryerrorinva// "QueryErrorInvalidxml"
0x58784  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58789  stloc.3
0x5878a  leave.s  loc_5878C
0x5878c  ldloc.2
0x5878d  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::IsEmpty()
0x58792  brfalse.s loc_5879B
0x58794  ldarg.0
0x58795  ldc.i4.0
0x58796  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x5879b  ldarg.0
0x5879c  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x587a1  brfalse  loc_589ED
0x587a6  ldarg.0
0x587a7  ldloc.2
0x587a8  callvirt instance string [mscorlib]System.Object::ToString()
0x587ad  ldarg.0
0x587ae  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::get_SessionPtr()
0x587b3  ldloca.s 3
0x587b5  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::TestEventQuery(string query, native int ctx, [out] string& error)
0x587ba  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x587bf  br       loc_589ED
0x587c4  ldarg.0
0x587c5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::treeComboBoxChannels
0x587ca  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox::get_SelectedChannels()
0x587cf  stloc.s  5
0x587d1  ldloc.s  5
0x587d3  brfalse  loc_58952
0x587d8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x587dd  stloc.s  6
0x587df  ldc.i4.1
0x587e0  stloc.s  7
0x587e2  ldloc.s  5
0x587e4  stloc.s  8
0x587e6  ldc.i4.0
0x587e7  stloc.s  9
0x587e9  br.s     loc_58816
0x587eb  ldloc.s  8
0x587ed  ldloc.s  9
0x587ef  ldelem.ref
0x587f0  stloc.s  0xA
0x587f2  ldloc.s  7
0x587f4  brtrue.s loc_58803
0x587f6  ldloc.s  6
0x587f8  ldstr    asc_AC604// ","
0x587fd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58802  pop
0x58803  ldloc.s  6
0x58805  ldloc.s  0xA
0x58807  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5880c  pop
0x5880d  ldc.i4.0
0x5880e  stloc.s  7
0x58810  ldloc.s  9
0x58812  ldc.i4.1
0x58813  add
0x58814  stloc.s  9
0x58816  ldloc.s  9
0x58818  ldloc.s  8
0x5881a  ldlen
0x5881b  conv.i4
0x5881c  blt.s    loc_587EB
0x5881e  ldarg.0
0x5881f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x58824  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Channel
0x58829  ldloc.s  6
0x5882b  callvirt instance string [mscorlib]System.Object::ToString()
0x58830  ldc.i4.1
0x58831  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::SetProperty(string propertyName, string value, bool simple)
0x58836  ldarg.0
0x58837  ldarg.0
0x58838  ldloca.s 0
0x5883a  ldarg.0
0x5883b  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x58840  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterEventSource(string& selector, class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig& config)
0x58845  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x5884a  ldarg.0
0x5884b  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x58850  brfalse.s loc_58866
0x58852  ldarg.0
0x58853  ldarg.0
0x58854  ldloca.s 0
0x58856  ldarg.0
0x58857  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x5885c  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForComputer(string& selector, class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig& config)
0x58861  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x58866  ldarg.0
0x58867  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x5886c  brfalse.s loc_58882
0x5886e  ldarg.0
0x5886f  ldarg.0
0x58870  ldloca.s 0
0x58872  ldarg.0
0x58873  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x58878  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForLevels(string& selector, class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig& config)
0x5887d  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x58882  ldarg.0
0x58883  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x58888  brfalse.s loc_5889E
0x5888a  ldarg.0
0x5888b  ldarg.0
0x5888c  ldloca.s 0
0x5888e  ldarg.0
0x5888f  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x58894  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForCategory(string& selector, class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig& config)
0x58899  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x5889e  ldarg.0
0x5889f  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x588a4  brfalse.s loc_588BA
0x588a6  ldarg.0
0x588a7  ldarg.0
0x588a8  ldloca.s 0
0x588aa  ldarg.0
0x588ab  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x588b0  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterEventKeywords(string& selector, class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig& config)
0x588b5  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x588ba  ldarg.0
0x588bb  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x588c0  brfalse.s loc_588D8
0x588c2  ldarg.0
0x588c3  ldarg.0
0x588c4  ldloca.s 0
0x588c6  ldloca.s 1
0x588c8  ldarg.0
0x588c9  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x588ce  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForEventId(string& selector, string& supressor, class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig& config)
0x588d3  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x588d8  ldarg.0
0x588d9  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x588de  brfalse.s loc_588F4
0x588e0  ldarg.0
0x588e1  ldarg.0
0x588e2  ldloca.s 0
0x588e4  ldarg.0
0x588e5  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x588ea  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForUser(string& selector, class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig& config)
0x588ef  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x588f4  ldarg.0
0x588f5  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x588fa  brfalse.s loc_58910
0x588fc  ldarg.0
0x588fd  ldarg.0
0x588fe  ldloca.s 0
0x58900  ldarg.0
0x58901  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x58906  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForDateRange(string& selector, class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig& config)
0x5890b  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x58910  ldarg.0
0x58911  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x58916  brfalse.s loc_58952
0x58918  ldloc.0
0x58919  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5891e  brtrue.s loc_58933
0x58920  ldstr    aSystem_0// "*[System["
0x58925  ldloc.0
0x58926  ldstr    asc_AD7CC// "]]"
0x5892b  call     string [mscorlib]System.String::Concat(string, string, string)
0x58930  stloc.0
0x58931  br.s     loc_58939
0x58933  ldstr    asc_AB580// "*"
0x58938  stloc.0
0x58939  ldloc.1
0x5893a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5893f  brtrue.s loc_58952
0x58941  ldstr    aSystem_0// "*[System["
0x58946  ldloc.1
0x58947  ldstr    asc_AD7CC// "]]"
0x5894c  call     string [mscorlib]System.String::Concat(string, string, string)
0x58951  stloc.1
0x58952  ldarg.0
0x58953  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x58958  brfalse  loc_589ED
0x5895d  ldarg.0
0x5895e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::treeComboBoxChannels
0x58963  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox::get_SelectedChannels()
0x58968  brfalse  loc_589ED
0x5896d  ldloc.0
0x5896e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58973  brfalse.s loc_5897D
0x58975  ldloc.1
0x58976  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5897b  brtrue.s loc_589ED
0x5897d  ldloc.0
0x5897e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58983  brtrue.s loc_589B5
0x58985  ldarg.0
0x58986  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::treeComboBoxChannels
0x5898b  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox::get_SelectedChannels()
0x58990  stloc.s  8
0x58992  ldc.i4.0
0x58993  stloc.s  9
0x58995  br.s     loc_589AD
0x58997  ldloc.s  8
0x58999  ldloc.s  9
0x5899b  ldelem.ref
0x5899c  stloc.s  0xB
0x5899e  ldloc.2
0x5899f  ldloc.s  0xB
0x589a1  ldloc.0
0x589a2  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::AddSelector(string path, string selector)
0x589a7  ldloc.s  9
0x589a9  ldc.i4.1
0x589aa  add
0x589ab  stloc.s  9
0x589ad  ldloc.s  9
0x589af  ldloc.s  8
0x589b1  ldlen
0x589b2  conv.i4
0x589b3  blt.s    loc_58997
0x589b5  ldloc.1
0x589b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x589bb  brtrue.s loc_589ED
0x589bd  ldarg.0
0x589be  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::treeComboBoxChannels
0x589c3  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox::get_SelectedChannels()
0x589c8  stloc.s  8
0x589ca  ldc.i4.0
0x589cb  stloc.s  9
0x589cd  br.s     loc_589E5
0x589cf  ldloc.s  8
0x589d1  ldloc.s  9
0x589d3  ldelem.ref
0x589d4  stloc.s  0xC
0x589d6  ldloc.2
0x589d7  ldloc.s  0xC
0x589d9  ldloc.1
0x589da  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::AddSuppressor(string path, string supressor)
0x589df  ldloc.s  9
0x589e1  ldc.i4.1
0x589e2  add
0x589e3  stloc.s  9
0x589e5  ldloc.s  9
0x589e7  ldloc.s  8
0x589e9  ldlen
0x589ea  conv.i4
0x589eb  blt.s    loc_589CF
0x589ed  ldarg.0
0x589ee  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::queryConfig
0x589f3  ldloc.2
0x589f4  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Query(class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery value)
0x589f9  ldarg.0
0x589fa  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::generateQuerySucceeded
0x589ff  ret
```
