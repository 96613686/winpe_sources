# Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::InitializeComponent

- ea: `0x6c700`
- end: `0x6ce78`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::InitializeComponent`
- size: `1912`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6bd00`

## callees

- `0x68c80`
- `0x6db60`
- `0x6faf0`
- `0x6ff50`
- `0x72280`
- `0x78ff0`

## string_xrefs

- `0x6ca5d`: `controlTaskGeneralInfoControl`
- `0x6ca6d`: `controlTaskGeneralInfoControl`
- `0x6cb49`: `tabTasks`
- `0x6cb59`: `tabTasks`
- `0x6cd61`: `controlTaskHistory`
- `0x6cd71`: `controlTaskHistory`
- `0x6cdd6`: `EditTaskDialog`

## pseudocode

```c

```

## disassembly

```asm
0x6c700  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog
0x6c705  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6c70a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x6c70f  ldarg.0
0x6c710  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x6c715  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonCancel
0x6c71a  ldarg.0
0x6c71b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x6c720  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonOk
0x6c725  ldarg.0
0x6c726  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabControl::.ctor()
0x6c72b  stfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c730  ldarg.0
0x6c731  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x6c736  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSummary
0x6c73b  ldarg.0
0x6c73c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x6c741  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelSummary
0x6c746  ldarg.0
0x6c747  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::.ctor()
0x6c74c  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTaskGeneralInfoControl
0x6c751  ldarg.0
0x6c752  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x6c757  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTriggers
0x6c75c  ldarg.0
0x6c75d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x6c762  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelTrigger
0x6c767  ldarg.0
0x6c768  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::.ctor()
0x6c76d  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTriggerListControl
0x6c772  ldarg.0
0x6c773  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x6c778  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTasks
0x6c77d  ldarg.0
0x6c77e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x6c783  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelActions
0x6c788  ldarg.0
0x6c789  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::.ctor()
0x6c78e  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlActionListControl
0x6c793  ldarg.0
0x6c794  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x6c799  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabConditions
0x6c79e  ldarg.0
0x6c79f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x6c7a4  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelConditions
0x6c7a9  ldarg.0
0x6c7aa  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::.ctor()
0x6c7af  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlConditionsControl
0x6c7b4  ldarg.0
0x6c7b5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x6c7ba  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSettings
0x6c7bf  ldarg.0
0x6c7c0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x6c7c5  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelSettings
0x6c7ca  ldarg.0
0x6c7cb  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::.ctor()
0x6c7d0  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlSettingsControl
0x6c7d5  ldarg.0
0x6c7d6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x6c7db  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabHistory
0x6c7e0  ldarg.0
0x6c7e1  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::.ctor()
0x6c7e6  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTaskHistory
0x6c7eb  ldarg.0
0x6c7ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c7f1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c7f6  ldarg.0
0x6c7f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSummary
0x6c7fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c801  ldarg.0
0x6c802  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelSummary
0x6c807  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c80c  ldarg.0
0x6c80d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTriggers
0x6c812  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c817  ldarg.0
0x6c818  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelTrigger
0x6c81d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c822  ldarg.0
0x6c823  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTasks
0x6c828  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c82d  ldarg.0
0x6c82e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelActions
0x6c833  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c838  ldarg.0
0x6c839  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabConditions
0x6c83e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c843  ldarg.0
0x6c844  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelConditions
0x6c849  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c84e  ldarg.0
0x6c84f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSettings
0x6c854  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c859  ldarg.0
0x6c85a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelSettings
0x6c85f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c864  ldarg.0
0x6c865  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabHistory
0x6c86a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c86f  ldarg.0
0x6c870  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c875  ldarg.0
0x6c876  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonCancel
0x6c87b  ldc.i4.2
0x6c87c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6c881  dup
0x6c882  ldarg.0
0x6c883  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonCancel
0x6c888  ldstr    aButtoncancel// "buttonCancel"
0x6c88d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6c892  ldarg.0
0x6c893  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonCancel
0x6c898  ldstr    aButtoncancel// "buttonCancel"
0x6c89d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6c8a2  ldarg.0
0x6c8a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonCancel
0x6c8a8  ldarg.0
0x6c8a9  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonCancel_Click(object sender, class [mscorlib]System.EventArgs e)
0x6c8af  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6c8b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6c8b9  ldarg.0
0x6c8ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonOk
0x6c8bf  ldc.i4.1
0x6c8c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6c8c5  dup
0x6c8c6  ldarg.0
0x6c8c7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonOk
0x6c8cc  ldstr    aButtonok_0// "buttonOk"
0x6c8d1  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6c8d6  ldarg.0
0x6c8d7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonOk
0x6c8dc  ldstr    aButtonok_0// "buttonOk"
0x6c8e1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6c8e6  ldarg.0
0x6c8e7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonOk
0x6c8ec  ldarg.0
0x6c8ed  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::buttonOk_Click(object sender, class [mscorlib]System.EventArgs e)
0x6c8f3  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6c8f8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6c8fd  ldarg.0
0x6c8fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c903  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6c908  ldarg.0
0x6c909  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSummary
0x6c90e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6c913  ldarg.0
0x6c914  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c919  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6c91e  ldarg.0
0x6c91f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTriggers
0x6c924  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6c929  ldarg.0
0x6c92a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c92f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6c934  ldarg.0
0x6c935  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTasks
0x6c93a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6c93f  ldarg.0
0x6c940  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c945  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6c94a  ldarg.0
0x6c94b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabConditions
0x6c950  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6c955  ldarg.0
0x6c956  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c95b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6c960  ldarg.0
0x6c961  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSettings
0x6c966  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6c96b  ldarg.0
0x6c96c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c971  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6c976  ldarg.0
0x6c977  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabHistory
0x6c97c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6c981  dup
0x6c982  ldarg.0
0x6c983  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c988  ldstr    aTabcontroldeta// "tabControlDetail"
0x6c98d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6c992  ldarg.0
0x6c993  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c998  ldstr    aTabcontroldeta// "tabControlDetail"
0x6c99d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6c9a2  ldarg.0
0x6c9a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c9a8  ldc.i4.0
0x6c9a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::set_SelectedIndex(int32)
0x6c9ae  ldarg.0
0x6c9af  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c9b4  ldarg.0
0x6c9b5  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail_HelpRequested(object sender, class [System.Windows.Forms]System.Windows.Forms.HelpEventArgs hlpevent)
0x6c9bb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.HelpEventHandler::.ctor(object, native int)
0x6c9c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_HelpRequested(class [System.Windows.Forms]System.Windows.Forms.HelpEventHandler)
0x6c9c5  ldarg.0
0x6c9c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c9cb  ldarg.0
0x6c9cc  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::TabSelectionChanged(object sender, class [mscorlib]System.EventArgs e)
0x6c9d2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6c9d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x6c9dc  ldarg.0
0x6c9dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSummary
0x6c9e2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6c9e7  ldarg.0
0x6c9e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelSummary
0x6c9ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6c9f2  dup
0x6c9f3  ldarg.0
0x6c9f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSummary
0x6c9f9  ldstr    aTabsummary// "tabSummary"
0x6c9fe  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6ca03  ldarg.0
0x6ca04  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSummary
0x6ca09  ldstr    aTabsummary// "tabSummary"
0x6ca0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6ca13  ldarg.0
0x6ca14  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSummary
0x6ca19  ldc.i4.1
0x6ca1a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_UseVisualStyleBackColor(bool)
0x6ca1f  ldarg.0
0x6ca20  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelSummary
0x6ca25  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6ca2a  ldarg.0
0x6ca2b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTaskGeneralInfoControl
0x6ca30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6ca35  dup
0x6ca36  ldarg.0
0x6ca37  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelSummary
0x6ca3c  ldstr    aPanelsummary// "panelSummary"
0x6ca41  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6ca46  ldarg.0
0x6ca47  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelSummary
0x6ca4c  ldstr    aPanelsummary// "panelSummary"
0x6ca51  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6ca56  dup
0x6ca57  ldarg.0
0x6ca58  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTaskGeneralInfoControl
0x6ca5d  ldstr    aControltaskgen// "controlTaskGeneralInfoControl"
0x6ca62  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6ca67  ldarg.0
0x6ca68  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTaskGeneralInfoControl
0x6ca6d  ldstr    aControltaskgen// "controlTaskGeneralInfoControl"
0x6ca72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6ca77  ldarg.0
0x6ca78  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTriggers
0x6ca7d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6ca82  ldarg.0
0x6ca83  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelTrigger
0x6ca88  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6ca8d  dup
0x6ca8e  ldarg.0
0x6ca8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTriggers
0x6ca94  ldstr    aTabtriggers// "tabTriggers"
0x6ca99  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6ca9e  ldarg.0
0x6ca9f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTriggers
0x6caa4  ldstr    aTabtriggers// "tabTriggers"
0x6caa9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6caae  ldarg.0
0x6caaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTriggers
0x6cab4  ldc.i4.1
0x6cab5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_UseVisualStyleBackColor(bool)
0x6caba  ldarg.0
0x6cabb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelTrigger
0x6cac0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6cac5  ldarg.0
0x6cac6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTriggerListControl
0x6cacb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6cad0  dup
0x6cad1  ldarg.0
0x6cad2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelTrigger
0x6cad7  ldstr    aPaneltrigger// "panelTrigger"
0x6cadc  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6cae1  ldarg.0
0x6cae2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelTrigger
0x6cae7  ldstr    aPaneltrigger// "panelTrigger"
0x6caec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6caf1  dup
0x6caf2  ldarg.0
0x6caf3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTriggerListControl
0x6caf8  ldstr    aControltrigger// "controlTriggerListControl"
0x6cafd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6cb02  ldarg.0
0x6cb03  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTriggerListControl
0x6cb08  ldc.i4   0x190
0x6cb0d  ldc.i4   0x16D
0x6cb12  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x6cb17  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x6cb1c  ldarg.0
0x6cb1d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::controlTriggerListControl
0x6cb22  ldstr    aControltrigger// "controlTriggerListControl"
0x6cb27  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6cb2c  ldarg.0
0x6cb2d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTasks
0x6cb32  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6cb37  ldarg.0
0x6cb38  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::panelActions
0x6cb3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6cb42  dup
0x6cb43  ldarg.0
  ... truncated ...
```
