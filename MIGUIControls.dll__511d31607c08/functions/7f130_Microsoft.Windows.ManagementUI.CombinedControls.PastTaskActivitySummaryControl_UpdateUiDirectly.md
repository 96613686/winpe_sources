# Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::UpdateUiDirectly

- ea: `0x7f130`
- end: `0x7f4c4`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::UpdateUiDirectly`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7f100`

## callees

- `0x12ed0`
- `0x13430`
- `0x7f130`
- `0xa2770`
- `0xa2780`
- `0xa2930`
- `0xa2990`
- `0xa2a40`
- `0xa2b90`
- `0xa2ce0`
- `0xa2d40`

## string_xrefs

- `0x7f18e`: `SummaryPageReadingData_Wait`
- `0x7f1d4`: `SummaryPageReadingDataFailed`
- `0x7f221`: `TaskSummaryPageNotSupportedInPreVista`
- `0x7f267`: `SummaryPageReadingDataCancelled`
- `0x7f4b9`: `Unexpected Update UI Type.`
- `0x7f39c`: `PastTaskSummaryLabelTextTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x7f130  ldarg.2
0x7f131  callvirt instance valuetype UiUpdateTypeEnum TaskHomePageUpdateUiArgs::get_UiUpdateType()
0x7f136  stloc.s  5
0x7f138  ldloc.s  5
0x7f13a  switch   loc_7F158, loc_7F19E, loc_7F231, loc_7F1EB, loc_7F27E
0x7f153  br       loc_7F4B9
0x7f158  ldarg.0
0x7f159  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f15e  ldc.i4.1
0x7f15f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f164  ldarg.0
0x7f165  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f16a  ldc.i4.0
0x7f16b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f170  ldarg.0
0x7f171  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f176  ldc.i4.0
0x7f177  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f17c  ldarg.0
0x7f17d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f182  ldc.i4.0
0x7f183  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7f188  ldarg.0
0x7f189  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f18e  ldstr    aSummarypagerea// "SummaryPageReadingData_Wait"
0x7f193  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f198  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7f19d  ret
0x7f19e  ldarg.0
0x7f19f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f1a4  ldc.i4.1
0x7f1a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f1aa  ldarg.0
0x7f1ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f1b0  ldc.i4.0
0x7f1b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f1b6  ldarg.0
0x7f1b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f1bc  ldc.i4.0
0x7f1bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f1c2  ldarg.0
0x7f1c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f1c8  ldc.i4.1
0x7f1c9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7f1ce  ldarg.0
0x7f1cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f1d4  ldstr    aSummarypagerea_0// "SummaryPageReadingDataFailed"
0x7f1d9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f1de  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7f1e3  ldarg.0
0x7f1e4  ldc.i4.m1
0x7f1e5  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::oldTimeSpanComboBoxSelectionIdx
0x7f1ea  ret
0x7f1eb  ldarg.0
0x7f1ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f1f1  ldc.i4.1
0x7f1f2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f1f7  ldarg.0
0x7f1f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f1fd  ldc.i4.0
0x7f1fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f203  ldarg.0
0x7f204  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f209  ldc.i4.0
0x7f20a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f20f  ldarg.0
0x7f210  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f215  ldc.i4.0
0x7f216  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7f21b  ldarg.0
0x7f21c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f221  ldstr    aTasksummarypag// "TaskSummaryPageNotSupportedInPreVista"
0x7f226  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f22b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7f230  ret
0x7f231  ldarg.0
0x7f232  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f237  ldc.i4.1
0x7f238  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f23d  ldarg.0
0x7f23e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f243  ldc.i4.0
0x7f244  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f249  ldarg.0
0x7f24a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f24f  ldc.i4.0
0x7f250  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f255  ldarg.0
0x7f256  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f25b  ldc.i4.1
0x7f25c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7f261  ldarg.0
0x7f262  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f267  ldstr    aSummarypagerea_1// "SummaryPageReadingDataCancelled"
0x7f26c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f271  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7f276  ldarg.0
0x7f277  ldc.i4.m1
0x7f278  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::oldTimeSpanComboBoxSelectionIdx
0x7f27d  ret
0x7f27e  ldarg.2
0x7f27f  callvirt instance object TaskHomePageUpdateUiArgs::get_Data()
0x7f284  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>
0x7f289  ldarg.0
0x7f28a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f28f  ldc.i4.0
0x7f290  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f295  ldarg.0
0x7f296  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f29b  ldc.i4.1
0x7f29c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f2a1  ldarg.0
0x7f2a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f2a7  ldc.i4.1
0x7f2a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7f2ad  ldc.i4.0
0x7f2ae  stloc.0
0x7f2af  ldc.i4.0
0x7f2b0  stloc.1
0x7f2b1  ldc.i4.0
0x7f2b2  stloc.2
0x7f2b3  ldc.i4.0
0x7f2b4  stloc.3
0x7f2b5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityDataGroup>::.ctor()
0x7f2ba  stloc.s  4
0x7f2bc  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::GetEnumerator()
0x7f2c1  stloc.s  6
0x7f2c3  br       loc_7F375
0x7f2c8  ldloca.s 6
0x7f2ca  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class PastTaskActivityData>::get_Current()
0x7f2cf  stloc.s  7
0x7f2d1  ldloca.s 7
0x7f2d3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class PastTaskActivityData>::get_Value()
0x7f2d8  stloc.s  8
0x7f2da  ldloc.s  8
0x7f2dc  callvirt instance valuetype [mscorlib]System.DateTime PastTaskActivityData::get_StartTime()
0x7f2e1  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x7f2e6  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7f2eb  brtrue   loc_7F375
0x7f2f0  ldloc.s  8
0x7f2f2  callvirt instance valuetype TaskStatusEnum PastTaskActivityData::get_TaskStatus()
0x7f2f7  stloc.s  0xA
0x7f2f9  ldloc.s  0xA
0x7f2fb  ldc.i4.1
0x7f2fc  sub
0x7f2fd  switch   loc_7F326, loc_7F320, loc_7F31A, loc_7F314
0x7f312  br.s     loc_7F32A
0x7f314  ldloc.0
0x7f315  ldc.i4.1
0x7f316  add
0x7f317  stloc.0
0x7f318  br.s     loc_7F32A
0x7f31a  ldloc.1
0x7f31b  ldc.i4.1
0x7f31c  add
0x7f31d  stloc.1
0x7f31e  br.s     loc_7F32A
0x7f320  ldloc.2
0x7f321  ldc.i4.1
0x7f322  add
0x7f323  stloc.2
0x7f324  br.s     loc_7F32A
0x7f326  ldloc.3
0x7f327  ldc.i4.1
0x7f328  add
0x7f329  stloc.3
0x7f32a  ldloc.s  8
0x7f32c  callvirt instance string PastTaskActivityData::get_TaskPath()
0x7f331  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7f336  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x7f33b  stloc.s  9
0x7f33d  ldloc.s  4
0x7f33f  ldloc.s  9
0x7f341  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityDataGroup>::ContainsKey(var<u1>)
0x7f346  brfalse.s loc_7F35A
0x7f348  ldloc.s  4
0x7f34a  ldloc.s  9
0x7f34c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityDataGroup>::get_Item(void)
0x7f351  ldloc.s  8
0x7f353  callvirt instance void PastTaskActivityDataGroup::Add(class PastTaskActivityData pastTaskData)
0x7f358  br.s     loc_7F375
0x7f35a  newobj   instance void PastTaskActivityDataGroup::.ctor()
0x7f35f  stloc.s  0xB
0x7f361  ldloc.s  0xB
0x7f363  ldloc.s  8
0x7f365  callvirt instance void PastTaskActivityDataGroup::Add(class PastTaskActivityData pastTaskData)
0x7f36a  ldloc.s  4
0x7f36c  ldloc.s  9
0x7f36e  ldloc.s  0xB
0x7f370  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityDataGroup>::Add(var<u1>, !!T0)
0x7f375  ldloca.s 6
0x7f377  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class PastTaskActivityData>::MoveNext()
0x7f37c  brtrue   loc_7F2C8
0x7f381  leave.s  loc_7F391
0x7f383  ldloca.s 6
0x7f385  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class PastTaskActivityData>
0x7f38b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f390  endfinally
0x7f391  ldarg.0
0x7f392  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f397  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7f39c  ldstr    aPasttasksummar// "PastTaskSummaryLabelTextTemplate"
0x7f3a1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f3a6  ldc.i4.5
0x7f3a7  newarr   [mscorlib]System.Object
0x7f3ac  dup
0x7f3ad  ldc.i4.0
0x7f3ae  ldloc.1
0x7f3af  ldloc.0
0x7f3b0  add
0x7f3b1  ldloc.3
0x7f3b2  add
0x7f3b3  ldloc.2
0x7f3b4  add
0x7f3b5  box      [mscorlib]System.Int32
0x7f3ba  stelem.ref
0x7f3bb  dup
0x7f3bc  ldc.i4.1
0x7f3bd  ldloc.0
0x7f3be  box      [mscorlib]System.Int32
0x7f3c3  stelem.ref
0x7f3c4  dup
0x7f3c5  ldc.i4.2
0x7f3c6  ldloc.3
0x7f3c7  box      [mscorlib]System.Int32
0x7f3cc  stelem.ref
0x7f3cd  dup
0x7f3ce  ldc.i4.3
0x7f3cf  ldloc.2
0x7f3d0  box      [mscorlib]System.Int32
0x7f3d5  stelem.ref
0x7f3d6  dup
0x7f3d7  ldc.i4.4
0x7f3d8  ldloc.1
0x7f3d9  box      [mscorlib]System.Int32
0x7f3de  stelem.ref
0x7f3df  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7f3e4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7f3e9  ldloc.s  4
0x7f3eb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityDataGroup>::get_Values()
0x7f3f0  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(class [mscorlib]System.Collections.ICollection)
0x7f3f5  dup
0x7f3f6  callvirt instance void [mscorlib]System.Collections.ArrayList::Sort()
0x7f3fb  ldarg.0
0x7f3fc  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f401  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::BeginUpdate()
0x7f406  ldarg.0
0x7f407  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f40c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x7f411  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::Clear()
0x7f416  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x7f41b  stloc.s  0xC
0x7f41d  br.s     loc_7F481
0x7f41f  ldloc.s  0xC
0x7f421  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7f426  castclass PastTaskActivityDataGroup
0x7f42b  stloc.s  0xD
0x7f42d  ldc.i4.5
0x7f42e  newarr   [mscorlib]System.String
0x7f433  dup
0x7f434  ldc.i4.0
0x7f435  ldloc.s  0xD
0x7f437  callvirt instance string PastTaskActivityDataGroup::get_DisplayString()
0x7f43c  stelem.ref
0x7f43d  dup
0x7f43e  ldc.i4.1
0x7f43f  ldsfld   string [mscorlib]System.String::Empty
0x7f444  stelem.ref
0x7f445  dup
0x7f446  ldc.i4.2
0x7f447  ldsfld   string [mscorlib]System.String::Empty
0x7f44c  stelem.ref
0x7f44d  dup
0x7f44e  ldc.i4.3
0x7f44f  ldsfld   string [mscorlib]System.String::Empty
0x7f454  stelem.ref
0x7f455  dup
0x7f456  ldc.i4.4
0x7f457  ldsfld   string [mscorlib]System.String::Empty
0x7f45c  stelem.ref
0x7f45d  ldc.i4.0
0x7f45e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListViewItem::.ctor(string[], int32)
0x7f463  stloc.s  0xE
0x7f465  ldloc.s  0xE
0x7f467  ldloc.s  0xD
0x7f469  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListViewItem::set_Tag(object)
0x7f46e  ldarg.0
0x7f46f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f474  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x7f479  ldloc.s  0xE
0x7f47b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListViewItem [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ListViewItem)
0x7f480  pop
0x7f481  ldloc.s  0xC
0x7f483  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7f488  brtrue.s loc_7F41F
0x7f48a  leave.s  loc_7F4A1
0x7f48c  ldloc.s  0xC
0x7f48e  isinst   [mscorlib]System.IDisposable
0x7f493  stloc.s  0xF
0x7f495  ldloc.s  0xF
  ... truncated ...
```
