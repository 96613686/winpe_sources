# Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::.ctor

- ea: `0x7efb0`
- end: `0x7f0f8`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::.ctor`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x7d4c0`

## callees

- `0x12ed0`
- `0x1fd20`
- `0x1fd40`
- `0x7f740`
- `0x7f880`

## string_xrefs

- `0x7f043`: `ColumnPastTaskSummaryTaskName`
- `0x7f063`: `ColumnPastTaskSummaryRunResult`
- `0x7f080`: `ColumnPastTaskSummaryRunTimeStart`
- `0x7f09d`: `ColumnPastTaskSummaryRunTimeEnd`
- `0x7f0ba`: `ColumnPastTaskSummaryTrigger`

## pseudocode

```c

```

## disassembly

```asm
0x7efb0  ldarg.0
0x7efb1  ldc.i4.m1
0x7efb2  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::oldTimeSpanComboBoxSelectionIdx
0x7efb7  ldarg.0
0x7efb8  call     instance void [System.Windows.Forms]System.Windows.Forms.UserControl::.ctor()
0x7efbd  ldarg.0
0x7efbe  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::InitializeComponent()
0x7efc3  ldarg.0
0x7efc4  ldarg.0
0x7efc5  ldfld    class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs> Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::uiUpdateDelegate
0x7efca  ldarg.0
0x7efcb  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::UpdateUiDirectly(object sender, class TaskHomePageUpdateUiArgs args)
0x7efd1  newobj   instance void class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs>::.ctor(object, native int)
0x7efd6  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x7efdb  castclass class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs>
0x7efe0  stfld    class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs> Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::uiUpdateDelegate
0x7efe5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ImageList::.ctor()
0x7efea  stloc.0
0x7efeb  ldloc.0
0x7efec  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x7eff1  call     class [System.Drawing]System.Drawing.Bitmap Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::get_ExpandSign()
0x7eff6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::Add(class [System.Drawing]System.Drawing.Image)
0x7effb  ldloc.0
0x7effc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x7f001  call     class [System.Drawing]System.Drawing.Bitmap Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::get_CollapseSign()
0x7f006  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::Add(class [System.Drawing]System.Drawing.Image)
0x7f00b  ldloc.0
0x7f00c  ldc.i4   0xFF
0x7f011  ldc.i4.0
0x7f012  ldc.i4   0xFF
0x7f017  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32)
0x7f01c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList::set_TransparentColor(valuetype [System.Drawing]System.Drawing.Color)
0x7f021  ldarg.0
0x7f022  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f027  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::BeginUpdate()
0x7f02c  ldarg.0
0x7f02d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f032  ldc.i4.1
0x7f033  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x7f038  ldarg.0
0x7f039  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f03e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7f043  ldstr    aColumnpasttask// "ColumnPastTaskSummaryTaskName"
0x7f048  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f04d  ldc.i4   0xC8
0x7f052  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7f057  pop
0x7f058  ldarg.0
0x7f059  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f05e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7f063  ldstr    aColumnpasttask_0// "ColumnPastTaskSummaryRunResult"
0x7f068  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f06d  ldc.i4.s 0x4B
0x7f06f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7f074  pop
0x7f075  ldarg.0
0x7f076  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f07b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7f080  ldstr    aColumnpasttask_1// "ColumnPastTaskSummaryRunTimeStart"
0x7f085  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f08a  ldc.i4.s 0x64
0x7f08c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7f091  pop
0x7f092  ldarg.0
0x7f093  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f098  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7f09d  ldstr    aColumnpasttask_2// "ColumnPastTaskSummaryRunTimeEnd"
0x7f0a2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f0a7  ldc.i4.s 0x64
0x7f0a9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7f0ae  pop
0x7f0af  ldarg.0
0x7f0b0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f0b5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7f0ba  ldstr    aColumnpasttask_3// "ColumnPastTaskSummaryTrigger"
0x7f0bf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7f0c4  ldc.i4.s 0x64
0x7f0c6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7f0cb  pop
0x7f0cc  ldarg.0
0x7f0cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f0d2  ldloc.0
0x7f0d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_SmallImageList(class [System.Windows.Forms]System.Windows.Forms.ImageList)
0x7f0d8  ldarg.0
0x7f0d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f0de  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::EndUpdate()
0x7f0e3  ldarg.0
0x7f0e4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f0e9  ldc.i4.1
0x7f0ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_SelectedIndex(int32)
0x7f0ef  ldarg.0
0x7f0f0  ldnull
0x7f0f1  ldnull
0x7f0f2  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox_SelectionChangeCommitted(object sender, class [mscorlib]System.EventArgs e)
0x7f0f7  ret
```
