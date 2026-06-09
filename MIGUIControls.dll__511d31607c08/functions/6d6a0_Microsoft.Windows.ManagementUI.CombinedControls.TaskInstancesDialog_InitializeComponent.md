# Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::InitializeComponent

- ea: `0x6d6a0`
- end: `0x6daf5`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::InitializeComponent`
- size: `1109`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x6cfa0`

## string_xrefs

- `0x6d927`: `columnHeaderPath`
- `0x6d938`: `buttonEndTask`
- `0x6d954`: `buttonEndTask`
- `0x6dab9`: `TaskInstancesDialog`

## pseudocode

```c

```

## disassembly

```asm
0x6d6a0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog
0x6d6a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d6aa  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x6d6af  stloc.0
0x6d6b0  ldarg.0
0x6d6b1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x6d6b6  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonClose
0x6d6bb  ldarg.0
0x6d6bc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x6d6c1  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonRefresh
0x6d6c6  ldarg.0
0x6d6c7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x6d6cc  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d6d1  ldarg.0
0x6d6d2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x6d6d7  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderName
0x6d6dc  ldarg.0
0x6d6dd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x6d6e2  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderStarted
0x6d6e7  ldarg.0
0x6d6e8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x6d6ed  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderDuration
0x6d6f2  ldarg.0
0x6d6f3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x6d6f8  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderCurrentAction
0x6d6fd  ldarg.0
0x6d6fe  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x6d703  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderPath
0x6d708  ldarg.0
0x6d709  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x6d70e  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonEndTask
0x6d713  ldarg.0
0x6d714  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6d719  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::labelIdleSeparator
0x6d71e  ldarg.0
0x6d71f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x6d724  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonTableLayoutPanel
0x6d729  ldarg.0
0x6d72a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x6d72f  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6d734  ldarg.0
0x6d735  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6d73a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6d73f  ldarg.0
0x6d740  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonTableLayoutPanel
0x6d745  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6d74a  ldarg.0
0x6d74b  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6d750  ldloc.0
0x6d751  ldarg.0
0x6d752  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonClose
0x6d757  ldstr    aButtonclose// "buttonClose"
0x6d75c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d761  ldarg.0
0x6d762  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonClose
0x6d767  ldc.i4.2
0x6d768  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6d76d  ldarg.0
0x6d76e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonClose
0x6d773  ldstr    aButtonclose// "buttonClose"
0x6d778  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6d77d  ldarg.0
0x6d77e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonClose
0x6d783  ldarg.0
0x6d784  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonCancel_Click(object sender, class [mscorlib]System.EventArgs e)
0x6d78a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6d78f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6d794  ldloc.0
0x6d795  ldarg.0
0x6d796  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonRefresh
0x6d79b  ldstr    aButtonrefresh// "buttonRefresh"
0x6d7a0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d7a5  ldarg.0
0x6d7a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonRefresh
0x6d7ab  ldc.i4.1
0x6d7ac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6d7b1  ldarg.0
0x6d7b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonRefresh
0x6d7b7  ldstr    aButtonrefresh// "buttonRefresh"
0x6d7bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6d7c1  ldarg.0
0x6d7c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonRefresh
0x6d7c7  ldarg.0
0x6d7c8  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonOk_Click(object sender, class [mscorlib]System.EventArgs e)
0x6d7ce  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6d7d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6d7d8  ldarg.0
0x6d7d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d7de  ldc.i4.1
0x6d7df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x6d7e4  ldarg.0
0x6d7e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d7ea  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x6d7ef  ldc.i4.5
0x6d7f0  newarr   [System.Windows.Forms]System.Windows.Forms.ColumnHeader
0x6d7f5  dup
0x6d7f6  ldc.i4.0
0x6d7f7  ldarg.0
0x6d7f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderName
0x6d7fd  stelem.ref
0x6d7fe  dup
0x6d7ff  ldc.i4.1
0x6d800  ldarg.0
0x6d801  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderStarted
0x6d806  stelem.ref
0x6d807  dup
0x6d808  ldc.i4.2
0x6d809  ldarg.0
0x6d80a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderDuration
0x6d80f  stelem.ref
0x6d810  dup
0x6d811  ldc.i4.3
0x6d812  ldarg.0
0x6d813  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderCurrentAction
0x6d818  stelem.ref
0x6d819  dup
0x6d81a  ldc.i4.4
0x6d81b  ldarg.0
0x6d81c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderPath
0x6d821  stelem.ref
0x6d822  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ColumnHeader[])
0x6d827  ldarg.0
0x6d828  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d82d  ldc.i4.1
0x6d82e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_MultiSelect(bool)
0x6d833  ldarg.0
0x6d834  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6d839  ldarg.0
0x6d83a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d83f  ldc.i4.2
0x6d840  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6d845  ldloc.0
0x6d846  ldarg.0
0x6d847  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d84c  ldstr    aListviewmain// "listViewMain"
0x6d851  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d856  ldarg.0
0x6d857  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d85c  ldc.i4.1
0x6d85d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x6d862  ldarg.0
0x6d863  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d868  ldc.i4.0
0x6d869  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HideSelection(bool)
0x6d86e  ldarg.0
0x6d86f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d874  ldstr    aListviewmain// "listViewMain"
0x6d879  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6d87e  ldarg.0
0x6d87f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d884  ldc.i4.1
0x6d885  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_ShowItemToolTips(bool)
0x6d88a  ldarg.0
0x6d88b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d890  ldc.i4.1
0x6d891  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_Sorting(valuetype [System.Windows.Forms]System.Windows.Forms.SortOrder)
0x6d896  ldarg.0
0x6d897  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d89c  ldc.i4.0
0x6d89d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_UseCompatibleStateImageBehavior(bool)
0x6d8a2  ldarg.0
0x6d8a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d8a8  ldc.i4.1
0x6d8a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x6d8ae  ldarg.0
0x6d8af  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d8b4  ldarg.0
0x6d8b5  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x6d8bb  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6d8c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x6d8c5  ldarg.0
0x6d8c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d8cb  ldarg.0
0x6d8cc  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain_ColumnClick(object sender, class [System.Windows.Forms]System.Windows.Forms.ColumnClickEventArgs e)
0x6d8d2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnClickEventHandler::.ctor(object, native int)
0x6d8d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_ColumnClick(class [System.Windows.Forms]System.Windows.Forms.ColumnClickEventHandler)
0x6d8dc  ldloc.0
0x6d8dd  ldarg.0
0x6d8de  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderName
0x6d8e3  ldstr    aColumnheaderna// "columnHeaderName"
0x6d8e8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d8ed  ldloc.0
0x6d8ee  ldarg.0
0x6d8ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderStarted
0x6d8f4  ldstr    aColumnheaderst// "columnHeaderStarted"
0x6d8f9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d8fe  ldloc.0
0x6d8ff  ldarg.0
0x6d900  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderDuration
0x6d905  ldstr    aColumnheaderdu// "columnHeaderDuration"
0x6d90a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d90f  ldloc.0
0x6d910  ldarg.0
0x6d911  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderCurrentAction
0x6d916  ldstr    aColumnheadercu// "columnHeaderCurrentAction"
0x6d91b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d920  ldloc.0
0x6d921  ldarg.0
0x6d922  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::columnHeaderPath
0x6d927  ldstr    aColumnheaderpa// "columnHeaderPath"
0x6d92c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d931  ldloc.0
0x6d932  ldarg.0
0x6d933  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonEndTask
0x6d938  ldstr    aButtonendtask// "buttonEndTask"
0x6d93d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d942  ldarg.0
0x6d943  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonEndTask
0x6d948  ldc.i4.1
0x6d949  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6d94e  ldarg.0
0x6d94f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonEndTask
0x6d954  ldstr    aButtonendtask// "buttonEndTask"
0x6d959  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6d95e  ldarg.0
0x6d95f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonEndTask
0x6d964  ldarg.0
0x6d965  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonEndTask_Click(object sender, class [mscorlib]System.EventArgs e)
0x6d96b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6d970  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6d975  ldarg.0
0x6d976  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::labelIdleSeparator
0x6d97b  ldc.i4.2
0x6d97c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x6d981  ldarg.0
0x6d982  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6d987  ldarg.0
0x6d988  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::labelIdleSeparator
0x6d98d  ldc.i4.2
0x6d98e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6d993  ldloc.0
0x6d994  ldarg.0
0x6d995  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::labelIdleSeparator
0x6d99a  ldstr    aLabelidlesepar// "labelIdleSeparator"
0x6d99f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d9a4  ldarg.0
0x6d9a5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::labelIdleSeparator
0x6d9aa  ldstr    aLabelidlesepar// "labelIdleSeparator"
0x6d9af  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6d9b4  ldloc.0
0x6d9b5  ldarg.0
0x6d9b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonTableLayoutPanel
0x6d9bb  ldstr    aButtontablelay// "buttonTableLayoutPanel"
0x6d9c0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6d9c5  ldarg.0
0x6d9c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonTableLayoutPanel
0x6d9cb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6d9d0  ldarg.0
0x6d9d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonRefresh
0x6d9d6  ldc.i4.0
0x6d9d7  ldc.i4.0
0x6d9d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6d9dd  ldarg.0
0x6d9de  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonTableLayoutPanel
0x6d9e3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6d9e8  ldarg.0
0x6d9e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonClose
0x6d9ee  ldc.i4.1
0x6d9ef  ldc.i4.0
0x6d9f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6d9f5  ldarg.0
0x6d9f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonTableLayoutPanel
0x6d9fb  ldstr    aButtontablelay// "buttonTableLayoutPanel"
0x6da00  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6da05  ldloc.0
0x6da06  ldarg.0
0x6da07  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6da0c  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x6da11  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6da16  ldarg.0
0x6da17  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6da1c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6da21  ldarg.0
0x6da22  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonTableLayoutPanel
0x6da27  ldc.i4.1
0x6da28  ldc.i4.3
0x6da29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6da2e  ldarg.0
0x6da2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6da34  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6da39  ldarg.0
0x6da3a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6da3f  ldc.i4.0
0x6da40  ldc.i4.0
0x6da41  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6da46  ldarg.0
0x6da47  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6da4c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6da51  ldarg.0
0x6da52  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::labelIdleSeparator
0x6da57  ldc.i4.0
0x6da58  ldc.i4.2
0x6da59  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6da5e  ldarg.0
0x6da5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::tableLayoutPanel
0x6da64  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6da69  ldarg.0
0x6da6a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::buttonEndTask
0x6da6f  ldc.i4.1
0x6da70  ldc.i4.1
  ... truncated ...
```
