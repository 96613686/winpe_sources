# Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::.ctor

- ea: `0x7fbf0`
- end: `0x7fcb5`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::.ctor`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x7d4c0`

## callees

- `0x12ed0`
- `0x80070`

## string_xrefs

- `0x7fc12`: `ColumnActiveTasksSummaryTaskName`
- `0x7fc32`: `ColumnActiveTasksSummaryNextRunTime`
- `0x7fc52`: `ColumnActiveTasksSummaryTriggers`
- `0x7fc72`: `ColumnActiveTasksSummaryLocation`

## pseudocode

```c

```

## disassembly

```asm
0x7fbf0  ldarg.0
0x7fbf1  call     instance void [System.Windows.Forms]System.Windows.Forms.UserControl::.ctor()
0x7fbf6  ldarg.0
0x7fbf7  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::InitializeComponent()
0x7fbfc  ldarg.0
0x7fbfd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fc02  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::BeginUpdate()
0x7fc07  ldarg.0
0x7fc08  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fc0d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7fc12  ldstr    aColumnactiveta// "ColumnActiveTasksSummaryTaskName"
0x7fc17  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7fc1c  ldc.i4   0xC8
0x7fc21  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7fc26  pop
0x7fc27  ldarg.0
0x7fc28  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fc2d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7fc32  ldstr    aColumnactiveta_0// "ColumnActiveTasksSummaryNextRunTime"
0x7fc37  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7fc3c  ldc.i4   0x96
0x7fc41  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7fc46  pop
0x7fc47  ldarg.0
0x7fc48  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fc4d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7fc52  ldstr    aColumnactiveta_1// "ColumnActiveTasksSummaryTriggers"
0x7fc57  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7fc5c  ldc.i4   0x96
0x7fc61  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7fc66  pop
0x7fc67  ldarg.0
0x7fc68  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fc6d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7fc72  ldstr    aColumnactiveta_2// "ColumnActiveTasksSummaryLocation"
0x7fc77  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7fc7c  ldc.i4   0x96
0x7fc81  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnHeader [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::Add(string, int32)
0x7fc86  pop
0x7fc87  ldarg.0
0x7fc88  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x7fc8d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::EndUpdate()
0x7fc92  ldarg.0
0x7fc93  ldarg.0
0x7fc94  ldfld    class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs> Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::uiUpdateDelegate
0x7fc99  ldarg.0
0x7fc9a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::UpdateUiDirectly(object sender, class TaskHomePageUpdateUiArgs args)
0x7fca0  newobj   instance void class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs>::.ctor(object, native int)
0x7fca5  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x7fcaa  castclass class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs>
0x7fcaf  stfld    class [mscorlib]System.EventHandler`1<class TaskHomePageUpdateUiArgs> Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::uiUpdateDelegate
0x7fcb4  ret
```
