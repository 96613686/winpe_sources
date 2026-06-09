# Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::InitializeComponent

- ea: `0x82800`
- end: `0x82fe7`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::InitializeComponent`
- size: `2023`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x80380`

## callees

- `0x25000`
- `0x68c80`
- `0x6ed60`
- `0x6faf0`
- `0x712a0`
- `0x73bb0`
- `0x78ff0`

## string_xrefs

- `0x82ee1`: `controlTaskHistory`
- `0x82f0b`: `controlTaskHistory`
- `0x82bf8`: `controlTaskGeneralPreviewControl`
- `0x82c22`: `controlTaskGeneralPreviewControl`
- `0x82f53`: `TaskDetailControl`

## pseudocode

```c

```

## disassembly

```asm
0x82800  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl
0x82805  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8280a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x8280f  ldarg.0
0x82810  newobj   instance void [System.Windows.Forms]System.Windows.Forms.SplitContainer::.ctor()
0x82815  stfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x8281a  ldarg.0
0x8281b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x82820  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82825  ldarg.0
0x82826  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx::.ctor()
0x8282b  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82830  ldarg.0
0x82831  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x82836  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral
0x8283b  ldarg.0
0x8283c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::.ctor()
0x82841  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlTaskGeneralPreviewControl
0x82846  ldarg.0
0x82847  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x8284c  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabTriggers
0x82851  ldarg.0
0x82852  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::.ctor()
0x82857  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlTriggerListControl
0x8285c  ldarg.0
0x8285d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x82862  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabActions
0x82867  ldarg.0
0x82868  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::.ctor()
0x8286d  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlActionListControl
0x82872  ldarg.0
0x82873  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x82878  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabConditions
0x8287d  ldarg.0
0x8287e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::.ctor()
0x82883  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlConditionsControl
0x82888  ldarg.0
0x82889  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x8288e  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabSettings
0x82893  ldarg.0
0x82894  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::.ctor()
0x82899  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlSettingsControl
0x8289e  ldarg.0
0x8289f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x828a4  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabHistory
0x828a9  ldarg.0
0x828aa  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory::.ctor()
0x828af  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskHistory Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlTaskHistory
0x828b4  ldarg.0
0x828b5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x828ba  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::panelNoItemSelected
0x828bf  ldarg.0
0x828c0  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x828c5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.SplitterPanel [System.Windows.Forms]System.Windows.Forms.SplitContainer::get_Panel1()
0x828ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x828cf  ldarg.0
0x828d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x828d5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.SplitterPanel [System.Windows.Forms]System.Windows.Forms.SplitContainer::get_Panel2()
0x828da  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x828df  ldarg.0
0x828e0  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x828e5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x828ea  ldarg.0
0x828eb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x828f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x828f5  ldarg.0
0x828f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral
0x828fb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x82900  ldarg.0
0x82901  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabTriggers
0x82906  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8290b  ldarg.0
0x8290c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabActions
0x82911  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x82916  ldarg.0
0x82917  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabConditions
0x8291c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x82921  ldarg.0
0x82922  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabSettings
0x82927  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8292c  ldarg.0
0x8292d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabHistory
0x82932  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x82937  ldarg.0
0x82938  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8293d  ldarg.0
0x8293e  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x82943  ldc.i4.2
0x82944  callvirt instance void [System.Windows.Forms]System.Windows.Forms.SplitContainer::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x82949  dup
0x8294a  ldarg.0
0x8294b  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x82950  ldstr    aPreviewpanespl// "previewPaneSplitter"
0x82955  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8295a  ldarg.0
0x8295b  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x82960  ldstr    aPreviewpanespl// "previewPaneSplitter"
0x82965  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8296a  dup
0x8296b  ldarg.0
0x8296c  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x82971  callvirt instance class [System.Windows.Forms]System.Windows.Forms.SplitterPanel [System.Windows.Forms]System.Windows.Forms.SplitContainer::get_Panel1()
0x82976  ldstr    aPreviewpanespl_0// "previewPaneSplitter.Panel1"
0x8297b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x82980  ldarg.0
0x82981  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x82986  callvirt instance class [System.Windows.Forms]System.Windows.Forms.SplitterPanel [System.Windows.Forms]System.Windows.Forms.SplitContainer::get_Panel1()
0x8298b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82990  ldarg.0
0x82991  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82996  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x8299b  dup
0x8299c  ldarg.0
0x8299d  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x829a2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.SplitterPanel [System.Windows.Forms]System.Windows.Forms.SplitContainer::get_Panel2()
0x829a7  ldstr    aPreviewpanespl_1// "previewPaneSplitter.Panel2"
0x829ac  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x829b1  ldarg.0
0x829b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x829b7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.SplitterPanel [System.Windows.Forms]System.Windows.Forms.SplitContainer::get_Panel2()
0x829bc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x829c1  ldarg.0
0x829c2  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x829c7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x829cc  ldarg.0
0x829cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::previewPaneSplitter
0x829d2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.SplitterPanel [System.Windows.Forms]System.Windows.Forms.SplitContainer::get_Panel2()
0x829d7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x829dc  ldarg.0
0x829dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::panelNoItemSelected
0x829e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x829e7  ldarg.0
0x829e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x829ed  ldc.i4.1
0x829ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_AllowColumnReorder(bool)
0x829f3  ldarg.0
0x829f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x829f9  ldc.i4.1
0x829fa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x829ff  dup
0x82a00  ldarg.0
0x82a01  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a06  ldstr    aListviewmain// "listViewMain"
0x82a0b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x82a10  ldarg.0
0x82a11  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a16  ldc.i4.1
0x82a17  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x82a1c  ldarg.0
0x82a1d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a22  ldc.i4.0
0x82a23  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HideSelection(bool)
0x82a28  ldarg.0
0x82a29  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a2e  ldstr    aListviewmain// "listViewMain"
0x82a33  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x82a38  ldarg.0
0x82a39  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a3e  ldc.i4.1
0x82a3f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_ShowItemToolTips(bool)
0x82a44  ldarg.0
0x82a45  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a4a  ldc.i4.0
0x82a4b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_UseCompatibleStateImageBehavior(bool)
0x82a50  ldarg.0
0x82a51  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a56  ldc.i4.1
0x82a57  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x82a5c  ldarg.0
0x82a5d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a62  ldarg.0
0x82a63  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain_DoubleClick(object sender, class [mscorlib]System.EventArgs e)
0x82a69  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x82a6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_DoubleClick(class [mscorlib]System.EventHandler)
0x82a73  ldarg.0
0x82a74  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a79  ldarg.0
0x82a7a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x82a80  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x82a85  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x82a8a  ldarg.0
0x82a8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82a90  ldarg.0
0x82a91  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::MouseButtonUp(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0x82a97  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0x82a9c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_MouseUp(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0x82aa1  ldarg.0
0x82aa2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82aa7  ldarg.0
0x82aa8  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain_KeyDown(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyEventArgs e)
0x82aae  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyEventHandler::.ctor(object, native int)
0x82ab3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyDown(class [System.Windows.Forms]System.Windows.Forms.KeyEventHandler)
0x82ab8  ldarg.0
0x82ab9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x82abe  ldarg.0
0x82abf  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain_ColumnClick(object sender, class [System.Windows.Forms]System.Windows.Forms.ColumnClickEventArgs e)
0x82ac5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnClickEventHandler::.ctor(object, native int)
0x82aca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_ColumnClick(class [System.Windows.Forms]System.Windows.Forms.ColumnClickEventHandler)
0x82acf  ldarg.0
0x82ad0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82ad5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82ada  ldarg.0
0x82adb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral
0x82ae0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82ae5  ldarg.0
0x82ae6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82aeb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82af0  ldarg.0
0x82af1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabTriggers
0x82af6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82afb  ldarg.0
0x82afc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82b01  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82b06  ldarg.0
0x82b07  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabActions
0x82b0c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82b11  ldarg.0
0x82b12  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82b17  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82b1c  ldarg.0
0x82b1d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabConditions
0x82b22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82b27  ldarg.0
0x82b28  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82b2d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82b32  ldarg.0
0x82b33  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabSettings
0x82b38  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82b3d  ldarg.0
0x82b3e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82b43  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82b48  ldarg.0
0x82b49  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabHistory
0x82b4e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82b53  dup
0x82b54  ldarg.0
0x82b55  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82b5a  ldstr    aTabcontroldeta// "tabControlDetail"
0x82b5f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x82b64  ldarg.0
0x82b65  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82b6a  ldstr    aTabcontroldeta// "tabControlDetail"
0x82b6f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x82b74  ldarg.0
0x82b75  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82b7a  ldc.i4.0
0x82b7b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::set_SelectedIndex(int32)
0x82b80  ldarg.0
0x82b81  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabControlDetail
0x82b86  ldarg.0
0x82b87  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::TabSelectionChanged(object sender, class [mscorlib]System.EventArgs e)
0x82b8d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x82b92  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x82b97  dup
0x82b98  ldarg.0
0x82b99  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral
0x82b9e  ldstr    aTabgeneral// "tabGeneral"
0x82ba3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x82ba8  ldarg.0
0x82ba9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral
0x82bae  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82bb3  ldarg.0
0x82bb4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlTaskGeneralPreviewControl
0x82bb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82bbe  ldarg.0
0x82bbf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral
0x82bc4  ldstr    aTabgeneral// "tabGeneral"
0x82bc9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x82bce  ldarg.0
0x82bcf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral
0x82bd4  ldc.i4.1
0x82bd5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_UseVisualStyleBackColor(bool)
0x82bda  ldarg.0
0x82bdb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral
0x82be0  ldarg.0
0x82be1  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabGeneral_Layout(object sender, class [System.Windows.Forms]System.Windows.Forms.LayoutEventArgs e)
0x82be7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LayoutEventHandler::.ctor(object, native int)
0x82bec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Layout(class [System.Windows.Forms]System.Windows.Forms.LayoutEventHandler)
0x82bf1  dup
0x82bf2  ldarg.0
0x82bf3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlTaskGeneralPreviewControl
0x82bf8  ldstr    aControltaskgen_2// "controlTaskGeneralPreviewControl"
0x82bfd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x82c02  ldarg.0
0x82c03  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlTaskGeneralPreviewControl
0x82c08  ldc.i4   0x268
0x82c0d  ldc.i4   0x178
0x82c12  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x82c17  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x82c1c  ldarg.0
0x82c1d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::controlTaskGeneralPreviewControl
0x82c22  ldstr    aControltaskgen_2// "controlTaskGeneralPreviewControl"
0x82c27  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x82c2c  dup
0x82c2d  ldarg.0
0x82c2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabTriggers
0x82c33  ldstr    aTabtriggers// "tabTriggers"
0x82c38  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x82c3d  ldarg.0
0x82c3e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::tabTriggers
  ... truncated ...
```
