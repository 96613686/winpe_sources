# Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::UpdateUiDirectly

- ea: `0x7fcf0`
- end: `0x7ff72`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::UpdateUiDirectly`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7fcc0`

## callees

- `0x12ed0`
- `0x13430`
- `0x5d740`
- `0x64320`
- `0x64380`
- `0x645c0`
- `0x64620`
- `0x67010`
- `0x7fcf0`
- `0xa2770`
- `0xa2780`

## string_xrefs

- `0x7fd1c`: `SummaryPageReadingData_Wait`
- `0x7fd56`: `SummaryPageReadingDataFailed`
- `0x7fd90`: `TaskSummaryPageNotSupportedInPreVista`
- `0x7fdca`: `SummaryPageReadingDataCancelled`
- `0x7ff67`: `Unexpected Update UI Type.`
- `0x7fefd`: `LabelActiveTasksSummary`

## pseudocode

```c

```

## disassembly

```asm
0x7fcf0  ldarg.2
0x7fcf1  callvirt instance valuetype UiUpdateTypeEnum TaskHomePageUpdateUiArgs::get_UiUpdateType()
0x7fcf6  stloc.1
0x7fcf7  ldloc.1
0x7fcf8  switch   loc_7FD16, loc_7FD50, loc_7FDC4, loc_7FD8A, loc_7FDFE
0x7fd11  br       loc_7FF67
0x7fd16  ldarg.0
0x7fd17  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7fd1c  ldstr    aSummarypagerea// "SummaryPageReadingData_Wait"
0x7fd21  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7fd26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7fd2b  ldarg.0
0x7fd2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7fd31  ldc.i4.1
0x7fd32  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fd37  ldarg.0
0x7fd38  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fd3d  ldc.i4.0
0x7fd3e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fd43  ldarg.0
0x7fd44  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x7fd49  ldc.i4.0
0x7fd4a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fd4f  ret
0x7fd50  ldarg.0
0x7fd51  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7fd56  ldstr    aSummarypagerea_0// "SummaryPageReadingDataFailed"
0x7fd5b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7fd60  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7fd65  ldarg.0
0x7fd66  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7fd6b  ldc.i4.1
0x7fd6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fd71  ldarg.0
0x7fd72  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fd77  ldc.i4.0
0x7fd78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fd7d  ldarg.0
0x7fd7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x7fd83  ldc.i4.0
0x7fd84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fd89  ret
0x7fd8a  ldarg.0
0x7fd8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7fd90  ldstr    aTasksummarypag// "TaskSummaryPageNotSupportedInPreVista"
0x7fd95  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7fd9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7fd9f  ldarg.0
0x7fda0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7fda5  ldc.i4.1
0x7fda6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fdab  ldarg.0
0x7fdac  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fdb1  ldc.i4.0
0x7fdb2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fdb7  ldarg.0
0x7fdb8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x7fdbd  ldc.i4.0
0x7fdbe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fdc3  ret
0x7fdc4  ldarg.0
0x7fdc5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7fdca  ldstr    aSummarypagerea_1// "SummaryPageReadingDataCancelled"
0x7fdcf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7fdd4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7fdd9  ldarg.0
0x7fdda  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7fddf  ldc.i4.1
0x7fde0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fde5  ldarg.0
0x7fde6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fdeb  ldc.i4.0
0x7fdec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fdf1  ldarg.0
0x7fdf2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x7fdf7  ldc.i4.0
0x7fdf8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7fdfd  ret
0x7fdfe  ldarg.2
0x7fdff  callvirt instance object TaskHomePageUpdateUiArgs::get_Data()
0x7fe04  castclass [mscorlib]System.Collections.ArrayList
0x7fe09  stloc.0
0x7fe0a  ldarg.0
0x7fe0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fe10  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::BeginUpdate()
0x7fe15  ldarg.0
0x7fe16  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fe1b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x7fe20  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::Clear()
0x7fe25  ldloc.0
0x7fe26  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x7fe2b  stloc.2
0x7fe2c  br       loc_7FEB2
0x7fe31  ldloc.2
0x7fe32  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7fe37  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITask
0x7fe3c  stloc.3
0x7fe3d  ldloc.3
0x7fe3e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_Parent()
0x7fe43  isinst   Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder
0x7fe48  stloc.s  4
0x7fe4a  ldloc.s  4
0x7fe4c  brfalse.s loc_7FE59
0x7fe4e  ldloc.s  4
0x7fe50  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Path()
0x7fe55  stloc.s  5
0x7fe57  br.s     loc_7FE60
0x7fe59  ldsfld   string [mscorlib]System.String::Empty
0x7fe5e  stloc.s  5
0x7fe60  ldc.i4.4
0x7fe61  newarr   [mscorlib]System.String
0x7fe66  dup
0x7fe67  ldc.i4.0
0x7fe68  ldloc.3
0x7fe69  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x7fe6e  stelem.ref
0x7fe6f  dup
0x7fe70  ldc.i4.1
0x7fe71  ldloc.3
0x7fe72  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x7fe77  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::get_NextRunTime()
0x7fe7c  stelem.ref
0x7fe7d  dup
0x7fe7e  ldc.i4.2
0x7fe7f  ldloc.3
0x7fe80  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x7fe85  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::get_TriggerDescription()
0x7fe8a  stelem.ref
0x7fe8b  dup
0x7fe8c  ldc.i4.3
0x7fe8d  ldloc.s  5
0x7fe8f  stelem.ref
0x7fe90  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListViewItem::.ctor(string[])
0x7fe95  stloc.s  6
0x7fe97  ldloc.s  6
0x7fe99  ldloc.3
0x7fe9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListViewItem::set_Tag(object)
0x7fe9f  ldarg.0
0x7fea0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fea5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x7feaa  ldloc.s  6
0x7feac  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListViewItem [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ListViewItem)
0x7feb1  pop
0x7feb2  ldloc.2
0x7feb3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7feb8  brtrue   loc_7FE31
0x7febd  leave.s  loc_7FED3
0x7febf  ldloc.2
0x7fec0  isinst   [mscorlib]System.IDisposable
0x7fec5  stloc.s  7
0x7fec7  ldloc.s  7
0x7fec9  brfalse.s loc_7FED2
0x7fecb  ldloc.s  7
0x7fecd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7fed2  endfinally
0x7fed3  ldarg.0
0x7fed4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fed9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::EndUpdate()
0x7fede  ldarg.0
0x7fedf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x7fee4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7fee9  ldtoken  [mscorlib]System.String
0x7feee  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7fef3  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7fef8  castclass [mscorlib]System.IFormatProvider
0x7fefd  ldstr    aLabelactivetas// "LabelActiveTasksSummary"
0x7ff02  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7ff07  ldc.i4.1
0x7ff08  newarr   [mscorlib]System.Object
0x7ff0d  dup
0x7ff0e  ldc.i4.0
0x7ff0f  ldloc.0
0x7ff10  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x7ff15  stloc.s  8
0x7ff17  ldloca.s 8
0x7ff19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7ff1e  ldtoken  [mscorlib]System.Int32
0x7ff23  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7ff28  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7ff2d  castclass [mscorlib]System.IFormatProvider
0x7ff32  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7ff37  stelem.ref
0x7ff38  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7ff3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7ff42  ldarg.0
0x7ff43  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x7ff48  ldc.i4.0
0x7ff49  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7ff4e  ldarg.0
0x7ff4f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7ff54  ldc.i4.1
0x7ff55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7ff5a  ldarg.0
0x7ff5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x7ff60  ldc.i4.1
0x7ff61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x7ff66  ret
0x7ff67  ldstr    aUnexpectedUpda// "Unexpected Update UI Type."
0x7ff6c  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x7ff71  ret
```
