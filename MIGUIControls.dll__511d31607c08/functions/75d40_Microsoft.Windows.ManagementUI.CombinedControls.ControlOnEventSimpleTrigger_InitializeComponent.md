# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::InitializeComponent

- ea: `0x75d40`
- end: `0x75fbd`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::InitializeComponent`
- size: `637`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x757d0`

## callees

- `0x18640`

## string_xrefs

- `0x75dd5`: `comboBoxLog`
- `0x75dfd`: `comboBoxLog`
- `0x75e31`: `comboBoxSource`
- `0x75e4d`: `comboBoxSource`

## pseudocode

```c

```

## disassembly

```asm
0x75d40  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger
0x75d45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75d4a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x75d4f  ldarg.0
0x75d50  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x75d55  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelLog
0x75d5a  ldarg.0
0x75d5b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x75d60  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75d65  ldarg.0
0x75d66  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x75d6b  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxSource
0x75d70  ldarg.0
0x75d71  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x75d76  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelSource
0x75d7b  ldarg.0
0x75d7c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x75d81  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelEventId
0x75d86  ldarg.0
0x75d87  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.NumericTextBox::.ctor()
0x75d8c  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.NumericTextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::textBoxEventId
0x75d91  ldarg.0
0x75d92  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x75d97  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75d9c  ldarg.0
0x75d9d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75da2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x75da7  ldarg.0
0x75da8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x75dad  dup
0x75dae  ldarg.0
0x75daf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelLog
0x75db4  ldstr    aLabellog// "labelLog"
0x75db9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x75dbe  ldarg.0
0x75dbf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelLog
0x75dc4  ldstr    aLabellog// "labelLog"
0x75dc9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x75dce  dup
0x75dcf  ldarg.0
0x75dd0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75dd5  ldstr    aComboboxlog// "comboBoxLog"
0x75dda  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x75ddf  ldarg.0
0x75de0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75de5  ldc.i4.2
0x75de6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x75deb  ldarg.0
0x75dec  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75df1  ldc.i4.1
0x75df2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x75df7  ldarg.0
0x75df8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75dfd  ldstr    aComboboxlog// "comboBoxLog"
0x75e02  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x75e07  ldarg.0
0x75e08  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75e0d  ldc.i4.1
0x75e0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_Sorted(bool)
0x75e13  ldarg.0
0x75e14  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75e19  ldarg.0
0x75e1a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x75e20  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x75e25  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x75e2a  dup
0x75e2b  ldarg.0
0x75e2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxSource
0x75e31  ldstr    aComboboxsource// "comboBoxSource"
0x75e36  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x75e3b  ldarg.0
0x75e3c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxSource
0x75e41  ldc.i4.1
0x75e42  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x75e47  ldarg.0
0x75e48  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxSource
0x75e4d  ldstr    aComboboxsource// "comboBoxSource"
0x75e52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x75e57  ldarg.0
0x75e58  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxSource
0x75e5d  ldc.i4.1
0x75e5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_Sorted(bool)
0x75e63  dup
0x75e64  ldarg.0
0x75e65  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelSource
0x75e6a  ldstr    aLabelsource// "labelSource"
0x75e6f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x75e74  ldarg.0
0x75e75  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelSource
0x75e7a  ldstr    aLabelsource// "labelSource"
0x75e7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x75e84  dup
0x75e85  ldarg.0
0x75e86  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelEventId
0x75e8b  ldstr    aLabeleventid// "labelEventId"
0x75e90  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x75e95  ldarg.0
0x75e96  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelEventId
0x75e9b  ldstr    aLabeleventid// "labelEventId"
0x75ea0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x75ea5  dup
0x75ea6  ldarg.0
0x75ea7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.NumericTextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::textBoxEventId
0x75eac  ldstr    aTextboxeventid// "textBoxEventId"
0x75eb1  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x75eb6  ldarg.0
0x75eb7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.NumericTextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::textBoxEventId
0x75ebc  ldstr    aTextboxeventid// "textBoxEventId"
0x75ec1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x75ec6  dup
0x75ec7  ldarg.0
0x75ec8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75ecd  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x75ed2  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x75ed7  ldarg.0
0x75ed8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75edd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x75ee2  ldarg.0
0x75ee3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelLog
0x75ee8  ldc.i4.0
0x75ee9  ldc.i4.0
0x75eea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x75eef  ldarg.0
0x75ef0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75ef5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x75efa  ldarg.0
0x75efb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.NumericTextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::textBoxEventId
0x75f00  ldc.i4.1
0x75f01  ldc.i4.2
0x75f02  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x75f07  ldarg.0
0x75f08  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75f0d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x75f12  ldarg.0
0x75f13  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelSource
0x75f18  ldc.i4.0
0x75f19  ldc.i4.1
0x75f1a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x75f1f  ldarg.0
0x75f20  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75f25  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x75f2a  ldarg.0
0x75f2b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxSource
0x75f30  ldc.i4.1
0x75f31  ldc.i4.1
0x75f32  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x75f37  ldarg.0
0x75f38  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75f3d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x75f42  ldarg.0
0x75f43  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::labelEventId
0x75f48  ldc.i4.0
0x75f49  ldc.i4.2
0x75f4a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x75f4f  ldarg.0
0x75f50  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75f55  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x75f5a  ldarg.0
0x75f5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75f60  ldc.i4.1
0x75f61  ldc.i4.0
0x75f62  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x75f67  ldarg.0
0x75f68  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75f6d  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x75f72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x75f77  ldarg.0
0x75f78  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x75f7d  ldarg.0
0x75f7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75f83  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x75f88  ldarg.0
0x75f89  ldstr    aThis// "$this"
0x75f8e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x75f93  ldarg.0
0x75f94  ldstr    aControlonevent_1// "ControlOnEventSimpleTrigger"
0x75f99  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x75f9e  ldarg.0
0x75f9f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75fa4  ldc.i4.0
0x75fa5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x75faa  ldarg.0
0x75fab  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::tableLayoutPanel1
0x75fb0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x75fb5  ldarg.0
0x75fb6  ldc.i4.0
0x75fb7  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x75fbc  ret
```
