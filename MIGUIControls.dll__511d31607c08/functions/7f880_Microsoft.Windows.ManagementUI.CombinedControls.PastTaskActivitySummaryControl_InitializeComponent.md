# Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::InitializeComponent

- ea: `0x7f880`
- end: `0x7fbde`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::InitializeComponent`
- size: `862`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x7efb0`

## string_xrefs

- `0x7f935`: `pastTaskSummaryLabel`
- `0x7f945`: `pastTaskSummaryLabel`
- `0x7f96f`: `pastTaskTimeSpanComboBox.Items`
- `0x7f97d`: `pastTaskTimeSpanComboBox.Items1`
- `0x7f98b`: `pastTaskTimeSpanComboBox.Items2`
- `0x7f999`: `pastTaskTimeSpanComboBox.Items3`
- `0x7f9b0`: `pastTaskTimeSpanComboBox`
- `0x7f9c0`: `pastTaskTimeSpanComboBox`
- `0x7f9d1`: `pastTaskTimeSpanComboBox.Text`
- `0x7fa10`: `dataReadingStatusLabel`
- `0x7fa20`: `dataReadingStatusLabel`
- `0x7fadc`: `pastTaskActivityListView`
- `0x7fb10`: `pastTaskActivityListView`
- `0x7fb9c`: `PastTaskActivitySummaryControl`

## pseudocode

```c

```

## disassembly

```asm
0x7f880  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl
0x7f885  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7f88a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x7f88f  stloc.0
0x7f890  ldarg.0
0x7f891  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7f896  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::overallDescriptionLabel
0x7f89b  ldarg.0
0x7f89c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7f8a1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f8a6  ldarg.0
0x7f8a7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x7f8ac  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f8b1  ldarg.0
0x7f8b2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7f8b7  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7f8bc  ldarg.0
0x7f8bd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x7f8c2  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7f8c7  ldarg.0
0x7f8c8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x7f8cd  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7f8d2  ldarg.0
0x7f8d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7f8d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7f8dd  ldarg.0
0x7f8de  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7f8e3  ldarg.0
0x7f8e4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::overallDescriptionLabel
0x7f8e9  ldc.i4.1
0x7f8ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x7f8ef  ldloc.0
0x7f8f0  ldarg.0
0x7f8f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::overallDescriptionLabel
0x7f8f6  ldstr    aOveralldescrip// "overallDescriptionLabel"
0x7f8fb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7f900  ldarg.0
0x7f901  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::overallDescriptionLabel
0x7f906  ldstr    aOveralldescrip// "overallDescriptionLabel"
0x7f90b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7f910  ldarg.0
0x7f911  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f916  ldc.i4.1
0x7f917  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x7f91c  ldarg.0
0x7f91d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7f922  ldarg.0
0x7f923  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f928  ldc.i4.2
0x7f929  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7f92e  ldloc.0
0x7f92f  ldarg.0
0x7f930  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f935  ldstr    aPasttasksummar_0// "pastTaskSummaryLabel"
0x7f93a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7f93f  ldarg.0
0x7f940  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7f945  ldstr    aPasttasksummar_0// "pastTaskSummaryLabel"
0x7f94a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7f94f  ldarg.0
0x7f950  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f955  ldc.i4.2
0x7f956  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x7f95b  ldarg.0
0x7f95c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f961  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x7f966  ldc.i4.4
0x7f967  newarr   [mscorlib]System.Object
0x7f96c  dup
0x7f96d  ldc.i4.0
0x7f96e  ldloc.0
0x7f96f  ldstr    aPasttasktimesp// "pastTaskTimeSpanComboBox.Items"
0x7f974  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7f979  stelem.ref
0x7f97a  dup
0x7f97b  ldc.i4.1
0x7f97c  ldloc.0
0x7f97d  ldstr    aPasttasktimesp_0// "pastTaskTimeSpanComboBox.Items1"
0x7f982  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7f987  stelem.ref
0x7f988  dup
0x7f989  ldc.i4.2
0x7f98a  ldloc.0
0x7f98b  ldstr    aPasttasktimesp_1// "pastTaskTimeSpanComboBox.Items2"
0x7f990  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7f995  stelem.ref
0x7f996  dup
0x7f997  ldc.i4.3
0x7f998  ldloc.0
0x7f999  ldstr    aPasttasktimesp_2// "pastTaskTimeSpanComboBox.Items3"
0x7f99e  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7f9a3  stelem.ref
0x7f9a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::AddRange(object[])
0x7f9a9  ldloc.0
0x7f9aa  ldarg.0
0x7f9ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f9b0  ldstr    aPasttasktimesp_3// "pastTaskTimeSpanComboBox"
0x7f9b5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7f9ba  ldarg.0
0x7f9bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f9c0  ldstr    aPasttasktimesp_3// "pastTaskTimeSpanComboBox"
0x7f9c5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7f9ca  ldarg.0
0x7f9cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f9d0  ldloc.0
0x7f9d1  ldstr    aPasttasktimesp_4// "pastTaskTimeSpanComboBox.Text"
0x7f9d6  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7f9db  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x7f9e0  ldarg.0
0x7f9e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7f9e6  ldarg.0
0x7f9e7  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox_SelectionChangeCommitted(object sender, class [mscorlib]System.EventArgs e)
0x7f9ed  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7f9f2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectionChangeCommitted(class [mscorlib]System.EventHandler)
0x7f9f7  ldarg.0
0x7f9f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7f9fd  ldarg.0
0x7f9fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7fa03  ldc.i4.2
0x7fa04  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7fa09  ldloc.0
0x7fa0a  ldarg.0
0x7fa0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7fa10  ldstr    aDatareadingsta// "dataReadingStatusLabel"
0x7fa15  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7fa1a  ldarg.0
0x7fa1b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7fa20  ldstr    aDatareadingsta// "dataReadingStatusLabel"
0x7fa25  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7fa2a  ldloc.0
0x7fa2b  ldarg.0
0x7fa2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fa31  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x7fa36  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7fa3b  ldarg.0
0x7fa3c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fa41  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7fa46  ldarg.0
0x7fa47  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::overallDescriptionLabel
0x7fa4c  ldc.i4.0
0x7fa4d  ldc.i4.0
0x7fa4e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7fa53  ldarg.0
0x7fa54  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fa59  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7fa5e  ldarg.0
0x7fa5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fa64  ldc.i4.0
0x7fa65  ldc.i4.3
0x7fa66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7fa6b  ldarg.0
0x7fa6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fa71  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7fa76  ldarg.0
0x7fa77  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::dataReadingStatusLabel
0x7fa7c  ldc.i4.0
0x7fa7d  ldc.i4.2
0x7fa7e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7fa83  ldarg.0
0x7fa84  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fa89  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7fa8e  ldarg.0
0x7fa8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskTimeSpanComboBox
0x7fa94  ldc.i4.1
0x7fa95  ldc.i4.0
0x7fa96  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7fa9b  ldarg.0
0x7fa9c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7faa1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7faa6  ldarg.0
0x7faa7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskSummaryLabel
0x7faac  ldc.i4.0
0x7faad  ldc.i4.1
0x7faae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7fab3  ldarg.0
0x7fab4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fab9  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x7fabe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7fac3  ldarg.0
0x7fac4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fac9  ldarg.0
0x7faca  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7facf  ldc.i4.2
0x7fad0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7fad5  ldloc.0
0x7fad6  ldarg.0
0x7fad7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fadc  ldstr    aPasttaskactivi// "pastTaskActivityListView"
0x7fae1  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7fae6  ldarg.0
0x7fae7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7faec  ldc.i4.1
0x7faed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x7faf2  ldarg.0
0x7faf3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7faf8  ldc.i4.1
0x7faf9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HeaderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ColumnHeaderStyle)
0x7fafe  ldarg.0
0x7faff  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fb04  ldc.i4.0
0x7fb05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_MultiSelect(bool)
0x7fb0a  ldarg.0
0x7fb0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fb10  ldstr    aPasttaskactivi// "pastTaskActivityListView"
0x7fb15  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7fb1a  ldarg.0
0x7fb1b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fb20  ldc.i4.1
0x7fb21  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_ShowItemToolTips(bool)
0x7fb26  ldarg.0
0x7fb27  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fb2c  ldc.i4.0
0x7fb2d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_UseCompatibleStateImageBehavior(bool)
0x7fb32  ldarg.0
0x7fb33  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fb38  ldarg.0
0x7fb39  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView_MouseClick(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0x7fb3f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0x7fb44  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_MouseClick(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0x7fb49  ldarg.0
0x7fb4a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fb4f  ldarg.0
0x7fb50  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView_DoubleClick(object sender, class [mscorlib]System.EventArgs e)
0x7fb56  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7fb5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_DoubleClick(class [mscorlib]System.EventHandler)
0x7fb60  ldarg.0
0x7fb61  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView
0x7fb66  ldarg.0
0x7fb67  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::pastTaskActivityListView_KeyUp(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyEventArgs e)
0x7fb6d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyEventHandler::.ctor(object, native int)
0x7fb72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyUp(class [System.Windows.Forms]System.Windows.Forms.KeyEventHandler)
0x7fb77  ldloc.0
0x7fb78  ldarg.0
0x7fb79  ldstr    aThis// "$this"
0x7fb7e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7fb83  ldarg.0
0x7fb84  ldc.i4.1
0x7fb85  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x7fb8a  ldarg.0
0x7fb8b  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7fb90  ldarg.0
0x7fb91  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fb96  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7fb9b  ldarg.0
0x7fb9c  ldstr    aPasttaskactivi_0// "PastTaskActivitySummaryControl"
0x7fba1  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7fba6  ldarg.0
0x7fba7  ldarg.0
0x7fba8  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::PastTaskActivitySummaryControl_Load(object sender, class [mscorlib]System.EventArgs e)
0x7fbae  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7fbb3  call     instance void [System.Windows.Forms]System.Windows.Forms.UserControl::add_Load(class [mscorlib]System.EventHandler)
0x7fbb8  ldarg.0
0x7fbb9  ldarg.0
0x7fbba  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::PastTaskActivitySummaryControl_RightToLeftChanged(object sender, class [mscorlib]System.EventArgs e)
0x7fbc0  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7fbc5  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::add_RightToLeftChanged(class [mscorlib]System.EventHandler)
0x7fbca  ldarg.0
0x7fbcb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::tableLayoutPanel
0x7fbd0  ldc.i4.0
0x7fbd1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x7fbd6  ldarg.0
0x7fbd7  ldc.i4.0
0x7fbd8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x7fbdd  ret
```
