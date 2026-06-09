# Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::UpdateUiDirectly

- ea: `0x7e8f0`
- end: `0x7eba4`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::UpdateUiDirectly`
- size: `692`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7db80`
- `0x7e8c0`

## callees

- `0x12ed0`
- `0x13430`
- `0x7dae0`
- `0x7e8f0`
- `0x7f100`
- `0x7fcc0`
- `0xa2770`
- `0xa2790`

## string_xrefs

- `0x7e90c`: `TaskSchedulerSummary`
- `0x7e9ab`: `SummaryPageReadingDataFailed`
- `0x7ea1b`: `TaskSummaryPageNotSupportedInPreVista`
- `0x7ea8b`: `SummaryPageReadingDataCancelled`
- `0x7eb99`: `Unexpected Update UI Type.`

## pseudocode

```c

```

## disassembly

```asm
0x7e8f0  ldarg.0
0x7e8f1  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshTime
0x7e8f6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7e8fb  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x7e900  stloc.0
0x7e901  ldarg.0
0x7e902  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::titleLabel
0x7e907  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7e90c  ldstr    aTaskschedulers_0// "TaskSchedulerSummary"
0x7e911  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7e916  ldc.i4.1
0x7e917  newarr   [mscorlib]System.Object
0x7e91c  dup
0x7e91d  ldc.i4.0
0x7e91e  ldloc.0
0x7e91f  stelem.ref
0x7e920  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7e925  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7e92a  ldarg.2
0x7e92b  callvirt instance valuetype UiUpdateTypeEnum TaskHomePageUpdateUiArgs::get_UiUpdateType()
0x7e930  stloc.1
0x7e931  ldloc.1
0x7e932  switch   loc_7E950, loc_7E9A5, loc_7EA85, loc_7EA15, loc_7EAF5
0x7e94b  br       loc_7EB99
0x7e950  ldarg.0
0x7e951  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7e956  ldstr    aSummarypagecan// "SummaryPageCancelRefresh"
0x7e95b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7e960  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7e965  ldarg.0
0x7e966  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7e96b  ldc.i4.1
0x7e96c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7e971  ldarg.0
0x7e972  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x7e977  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7e97c  ldarg.0
0x7e97d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7e982  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7e987  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7e98c  ldarg.0
0x7e98d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityControl
0x7e992  ldarg.2
0x7e993  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7e998  ldarg.0
0x7e999  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksSummaryControl
0x7e99e  ldarg.2
0x7e99f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7e9a4  ret
0x7e9a5  ldarg.0
0x7e9a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshStatusLabel
0x7e9ab  ldstr    aSummarypagerea_0// "SummaryPageReadingDataFailed"
0x7e9b0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7e9b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7e9ba  ldarg.0
0x7e9bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7e9c0  ldstr    aRefresh// "Refresh"
0x7e9c5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7e9ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7e9cf  ldarg.0
0x7e9d0  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::AdjustRefreshButtonLocation()
0x7e9d5  ldarg.0
0x7e9d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7e9db  ldc.i4.1
0x7e9dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7e9e1  ldarg.0
0x7e9e2  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7e9e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7e9ec  ldarg.0
0x7e9ed  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7e9f2  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7e9f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7e9fc  ldarg.0
0x7e9fd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityControl
0x7ea02  ldarg.2
0x7ea03  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7ea08  ldarg.0
0x7ea09  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksSummaryControl
0x7ea0e  ldarg.2
0x7ea0f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7ea14  ret
0x7ea15  ldarg.0
0x7ea16  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshStatusLabel
0x7ea1b  ldstr    aTasksummarypag// "TaskSummaryPageNotSupportedInPreVista"
0x7ea20  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7ea25  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7ea2a  ldarg.0
0x7ea2b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7ea30  ldstr    aRefresh// "Refresh"
0x7ea35  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7ea3a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7ea3f  ldarg.0
0x7ea40  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::AdjustRefreshButtonLocation()
0x7ea45  ldarg.0
0x7ea46  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7ea4b  ldc.i4.1
0x7ea4c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7ea51  ldarg.0
0x7ea52  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7ea57  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7ea5c  ldarg.0
0x7ea5d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7ea62  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7ea67  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7ea6c  ldarg.0
0x7ea6d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityControl
0x7ea72  ldarg.2
0x7ea73  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7ea78  ldarg.0
0x7ea79  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksSummaryControl
0x7ea7e  ldarg.2
0x7ea7f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7ea84  ret
0x7ea85  ldarg.0
0x7ea86  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshStatusLabel
0x7ea8b  ldstr    aSummarypagerea_1// "SummaryPageReadingDataCancelled"
0x7ea90  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7ea95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7ea9a  ldarg.0
0x7ea9b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7eaa0  ldstr    aRefresh// "Refresh"
0x7eaa5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7eaaa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7eaaf  ldarg.0
0x7eab0  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::AdjustRefreshButtonLocation()
0x7eab5  ldarg.0
0x7eab6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7eabb  ldc.i4.1
0x7eabc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7eac1  ldarg.0
0x7eac2  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7eac7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7eacc  ldarg.0
0x7eacd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7ead2  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7ead7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7eadc  ldarg.0
0x7eadd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityControl
0x7eae2  ldarg.2
0x7eae3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7eae8  ldarg.0
0x7eae9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksSummaryControl
0x7eaee  ldarg.2
0x7eaef  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7eaf4  ret
0x7eaf5  ldarg.0
0x7eaf6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshStatusLabel
0x7eafb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7eb00  ldstr    aRefreshpanella// "RefreshPanelLabelText"
0x7eb05  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7eb0a  ldc.i4.1
0x7eb0b  newarr   [mscorlib]System.Object
0x7eb10  dup
0x7eb11  ldc.i4.0
0x7eb12  ldloc.0
0x7eb13  stelem.ref
0x7eb14  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7eb19  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7eb1e  ldarg.0
0x7eb1f  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::AdjustRefreshButtonLocation()
0x7eb24  ldarg.0
0x7eb25  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7eb2a  ldc.i4.1
0x7eb2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7eb30  ldarg.0
0x7eb31  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7eb36  ldstr    aRefresh// "Refresh"
0x7eb3b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7eb40  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x7eb45  ldarg.0
0x7eb46  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7eb4b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7eb50  ldarg.0
0x7eb51  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshButton
0x7eb56  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_Default()
0x7eb5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x7eb60  ldarg.0
0x7eb61  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityControl
0x7eb66  ldarg.2
0x7eb67  callvirt instance valuetype UiUpdateTypeEnum TaskHomePageUpdateUiArgs::get_UiUpdateType()
0x7eb6c  ldarg.0
0x7eb6d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7eb72  newobj   instance void TaskHomePageUpdateUiArgs::.ctor(valuetype UiUpdateTypeEnum uiUpdateType, object data)
0x7eb77  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7eb7c  ldarg.0
0x7eb7d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksSummaryControl
0x7eb82  ldarg.2
0x7eb83  callvirt instance valuetype UiUpdateTypeEnum TaskHomePageUpdateUiArgs::get_UiUpdateType()
0x7eb88  ldarg.0
0x7eb89  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksList
0x7eb8e  newobj   instance void TaskHomePageUpdateUiArgs::.ctor(valuetype UiUpdateTypeEnum uiUpdateType, object data)
0x7eb93  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::UpdateUi(class TaskHomePageUpdateUiArgs args)
0x7eb98  ret
0x7eb99  ldstr    aUnexpectedUpda// "Unexpected Update UI Type."
0x7eb9e  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x7eba3  ret
```
