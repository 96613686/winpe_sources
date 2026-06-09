# Microsoft.EventViewer.SnapIn.EventViewerHomepage::OnEventsSummaryListViewAction

- ea: `0x70f0`
- end: `0x76fa`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::OnEventsSummaryListViewAction`
- size: `1546`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6bf0`

## callees

- `0x1a00`
- `0x70f0`
- `0x7810`

## string_xrefs

- `0x7120`: `ViewNameTemplate_WithLevelOnly`
- `0x7153`: `ViewNameTemplate_WithGivenIdAndSource`

## pseudocode

```c

```

## disassembly

```asm
0x70f0  ldc.i4   0xED5
0x70f5  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint)
0x70fa  ldarg.1
0x70fb  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_GroupedBySeverity()
0x7100  stloc.0
0x7101  ldarg.1
0x7102  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_QueryInfo()
0x7107  stloc.1
0x7108  ldc.i8   0x30000000000000
0x7111  stloc.s  4
0x7113  ldarg.1
0x7114  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_IsGroupedBySeverityItem()
0x7119  brfalse.s loc_714E
0x711b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7120  ldstr    aViewnametempla// "ViewNameTemplate_WithLevelOnly"
0x7125  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x712a  ldc.i4.1
0x712b  newarr   [mscorlib]System.Object
0x7130  dup
0x7131  ldc.i4.0
0x7132  ldarg.1
0x7133  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_GroupedBySeverity()
0x7138  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_SeverityName()
0x713d  stelem.ref
0x713e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7143  stloc.2
0x7144  ldarg.1
0x7145  callvirt instance class [mscorlib]System.Collections.ArrayList [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_AdminChannels()
0x714a  stloc.s  6
0x714c  br.s     loc_71A6
0x714e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7153  ldstr    aViewnametempla_0// "ViewNameTemplate_WithGivenIdAndSource"
0x7158  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x715d  ldc.i4.3
0x715e  newarr   [mscorlib]System.Object
0x7163  dup
0x7164  ldc.i4.0
0x7165  ldarg.1
0x7166  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_GroupedBySeverity()
0x716b  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_SeverityName()
0x7170  stelem.ref
0x7171  dup
0x7172  ldc.i4.1
0x7173  ldloc.1
0x7174  callvirt instance unsigned int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_EventID()
0x7179  box      [mscorlib]System.UInt32
0x717e  stelem.ref
0x717f  dup
0x7180  ldc.i4.2
0x7181  ldarg.0
0x7182  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl Microsoft.EventViewer.SnapIn.EventViewerHomepage::eventHomeControl
0x7187  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::get_Context()
0x718c  ldloc.1
0x718d  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_EventSource()
0x7192  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetPublisherDisplayName(string)
0x7197  stelem.ref
0x7198  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x719d  stloc.2
0x719e  ldloc.1
0x719f  callvirt instance class [mscorlib]System.Collections.IEnumerable [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_Channels()
0x71a4  stloc.s  6
0x71a6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x71ab  stloc.s  7
0x71ad  ldc.i4.0
0x71ae  stloc.s  8
0x71b0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x71b5  stloc.s  9
0x71b7  ldarg.1
0x71b8  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_IsGroupedBySeverityItem()
0x71bd  brfalse  loc_731A
0x71c2  ldloc.0
0x71c3  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_Level()
0x71c8  ldc.i4.4
0x71c9  bne.un.s loc_71DD
0x71cb  ldloc.s  9
0x71cd  ldstr    aSystemLevel4Or// "*[System[(Level=4 or level=0)]]"
0x71d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x71d7  pop
0x71d8  br       loc_74AA
0x71dd  ldloc.0
0x71de  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_Level()
0x71e3  ldc.i4.5
0x71e4  bgt.s    loc_7211
0x71e6  ldloc.s  9
0x71e8  ldstr    aSystemLevel// "*[System/Level="
0x71ed  ldloc.0
0x71ee  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_Level()
0x71f3  stloc.s  0x12
0x71f5  ldloca.s 0x12
0x71f7  call     instance string [mscorlib]System.Int32::ToString()
0x71fc  ldstr    asc_C372// "]"
0x7201  call     string [mscorlib]System.String::Concat(string, string, string)
0x7206  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x720b  pop
0x720c  br       loc_74AA
0x7211  ldloc.0
0x7212  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_Level()
0x7217  ldc.i4   0x100
0x721c  blt      loc_7308
0x7221  ldc.i4.1
0x7222  stloc.s  8
0x7224  ldloc.0
0x7225  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_Level()
0x722a  ldc.i4   0x100
0x722f  bne.un.s loc_7278
0x7231  ldc.i8   0x20000000000000
0x723a  stloc.s  5
0x723c  ldloc.s  9
0x723e  ldstr    aSystemBandKeyw// "*[System[band(Keywords,"
0x7243  ldloca.s 5
0x7245  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x724a  ldtoken  [mscorlib]System.UInt64
0x724f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7254  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7259  castclass [mscorlib]System.IFormatProvider
0x725e  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x7263  ldstr    asc_C3A6// ")]]"
0x7268  call     string [mscorlib]System.String::Concat(string, string, string)
0x726d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7272  pop
0x7273  br       loc_74AA
0x7278  ldloc.0
0x7279  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_Level()
0x727e  ldc.i4   0x101
0x7283  bne.un.s loc_72CC
0x7285  ldc.i8   0x10000000000000
0x728e  stloc.s  5
0x7290  ldloc.s  9
0x7292  ldstr    aSystemBandKeyw// "*[System[band(Keywords,"
0x7297  ldloca.s 5
0x7299  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x729e  ldtoken  [mscorlib]System.UInt64
0x72a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x72a8  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x72ad  castclass [mscorlib]System.IFormatProvider
0x72b2  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x72b7  ldstr    asc_C3A6// ")]]"
0x72bc  call     string [mscorlib]System.String::Concat(string, string, string)
0x72c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x72c6  pop
0x72c7  br       loc_74AA
0x72cc  ldloc.s  9
0x72ce  ldstr    aSystemBandKeyw// "*[System[band(Keywords,"
0x72d3  ldloca.s 4
0x72d5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x72da  ldtoken  [mscorlib]System.UInt64
0x72df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x72e4  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x72e9  castclass [mscorlib]System.IFormatProvider
0x72ee  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x72f3  ldstr    aFalse_0// ") = false]]"
0x72f8  call     string [mscorlib]System.String::Concat(string, string, string)
0x72fd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7302  pop
0x7303  br       loc_74AA
0x7308  ldloc.s  9
0x730a  ldstr    aSystemLevel5// "*[System/Level>5]"
0x730f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7314  pop
0x7315  br       loc_74AA
0x731a  ldloc.s  9
0x731c  ldstr    aSystemProvider// "*[System[Provider[@Name='"
0x7321  ldloc.1
0x7322  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_EventSource()
0x7327  ldstr    asc_C41E// "']"
0x732c  call     string [mscorlib]System.String::Concat(string, string, string)
0x7331  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7336  pop
0x7337  ldloc.1
0x7338  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_Level()
0x733d  ldc.i4.4
0x733e  bne.un.s loc_7352
0x7340  ldloc.s  9
0x7342  ldstr    aAndLevel4OrLev// " and (Level=4 or Level=0)"
0x7347  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x734c  pop
0x734d  br       loc_7484
0x7352  ldloc.1
0x7353  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_Level()
0x7358  ldc.i4.5
0x7359  bgt.s    loc_7386
0x735b  ldloc.s  9
0x735d  ldstr    aAndLevel// " and (Level="
0x7362  ldloc.1
0x7363  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_Level()
0x7368  stloc.s  0x12
0x736a  ldloca.s 0x12
0x736c  call     instance string [mscorlib]System.Int32::ToString()
0x7371  ldstr    asc_C472// ")"
0x7376  call     string [mscorlib]System.String::Concat(string, string, string)
0x737b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7380  pop
0x7381  br       loc_7484
0x7386  ldloc.1
0x7387  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_Level()
0x738c  ldc.i4   0x100
0x7391  blt      loc_7477
0x7396  ldc.i4.1
0x7397  stloc.s  8
0x7399  ldloc.1
0x739a  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_Level()
0x739f  ldc.i4   0x100
0x73a4  bne.un.s loc_73ED
0x73a6  ldc.i8   0x20000000000000
0x73af  stloc.s  5
0x73b1  ldloc.s  9
0x73b3  ldstr    aAndBandKeyword// " and (band(Keywords,"
0x73b8  ldloca.s 5
0x73ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x73bf  ldtoken  [mscorlib]System.UInt64
0x73c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73c9  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x73ce  castclass [mscorlib]System.IFormatProvider
0x73d3  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x73d8  ldstr    asc_C4A0// "))"
0x73dd  call     string [mscorlib]System.String::Concat(string, string, string)
0x73e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x73e7  pop
0x73e8  br       loc_7484
0x73ed  ldloc.1
0x73ee  callvirt instance int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_Level()
0x73f3  ldc.i4   0x101
0x73f8  bne.un.s loc_743E
0x73fa  ldc.i8   0x10000000000000
0x7403  stloc.s  5
0x7405  ldloc.s  9
0x7407  ldstr    aAndBandKeyword_0// "and (band(Keywords,"
0x740c  ldloca.s 5
0x740e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7413  ldtoken  [mscorlib]System.UInt64
0x7418  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x741d  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7422  castclass [mscorlib]System.IFormatProvider
0x7427  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x742c  ldstr    asc_C4A0// "))"
0x7431  call     string [mscorlib]System.String::Concat(string, string, string)
0x7436  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x743b  pop
0x743c  br.s     loc_7484
0x743e  ldloc.s  9
0x7440  ldstr    aAndBandKeyword_0// "and (band(Keywords,"
0x7445  ldloca.s 4
0x7447  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x744c  ldtoken  [mscorlib]System.UInt64
0x7451  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7456  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x745b  castclass [mscorlib]System.IFormatProvider
0x7460  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x7465  ldstr    aFalse_1// ") = false)"
0x746a  call     string [mscorlib]System.String::Concat(string, string, string)
0x746f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7474  pop
0x7475  br.s     loc_7484
0x7477  ldloc.s  9
0x7479  ldstr    aAndLevel5// " and (Level>5)"
0x747e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7483  pop
0x7484  ldloc.s  9
0x7486  ldstr    aAndEventid// " and (EventID="
0x748b  ldloc.1
0x748c  callvirt instance unsigned int32 [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_EventID()
0x7491  stloc.s  0x13
0x7493  ldloca.s 0x13
0x7495  call     instance string [mscorlib]System.UInt32::ToString()
0x749a  ldstr    asc_C3A6// ")]]"
0x749f  call     string [mscorlib]System.String::Concat(string, string, string)
0x74a4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x74a9  pop
0x74aa  ldloc.s  9
0x74ac  callvirt instance string [mscorlib]System.Object::ToString()
0x74b1  stloc.s  0xA
0x74b3  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::.ctor()
0x74b8  stloc.s  0xB
0x74ba  ldarg.0
0x74bb  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x74c0  castclass Microsoft.EventViewer.SnapIn.MMCRootNode
0x74c5  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x74ca  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Context()
0x74cf  stloc.s  0xC
0x74d1  ldc.i4.1
0x74d2  stloc.s  0xE
0x74d4  ldloc.s  6
0x74d6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x74db  stloc.s  0x14
0x74dd  br.s     loc_7535
0x74df  ldloc.s  0x14
0x74e1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x74e6  castclass [mscorlib]System.String
0x74eb  stloc.s  0x15
0x74ed  ldc.i4.0
0x74ee  stloc.s  0xD
0x74f0  ldloc.s  0xC
0x74f2  brfalse.s loc_74FD
0x74f4  ldloc.s  0x15
0x74f6  call     bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsSecurityChannel(string)
0x74fb  stloc.s  0xD
0x74fd  ldloc.s  8
0x74ff  ldloc.s  0xD
0x7501  and
0x7502  brtrue.s loc_750C
  ... truncated ...
```
