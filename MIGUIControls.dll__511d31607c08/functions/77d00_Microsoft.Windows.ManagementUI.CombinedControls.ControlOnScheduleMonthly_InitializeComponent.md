# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::InitializeComponent

- ea: `0x77d00`
- end: `0x78050`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::InitializeComponent`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x77240`

## callees

- `0x19710`
- `0x1a6e0`

## string_xrefs

- `0x77db2`: `checkedListComboBoxMonths`
- `0x77dc2`: `checkedListComboBoxMonths`
- `0x77ea0`: `calendarCheckedListCombo`
- `0x77eb0`: `calendarCheckedListCombo`
- `0x77ed8`: `checkedListComboHowOften`
- `0x77ee8`: `checkedListComboHowOften`
- `0x77f10`: `checkedListComboBoxDayOfTheWeek`
- `0x77f20`: `checkedListComboBoxDayOfTheWeek`

## pseudocode

```c

```

## disassembly

```asm
0x77d00  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly
0x77d05  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x77d0a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x77d0f  ldarg.0
0x77d10  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x77d15  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::labelMonths
0x77d1a  ldarg.0
0x77d1b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::.ctor()
0x77d20  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxMonths
0x77d25  ldarg.0
0x77d26  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x77d2b  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonMonth
0x77d30  ldarg.0
0x77d31  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x77d36  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonDayOfWeek
0x77d3b  ldarg.0
0x77d3c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox::.ctor()
0x77d41  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::calendarCheckedListCombo
0x77d46  ldarg.0
0x77d47  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::.ctor()
0x77d4c  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboHowOften
0x77d51  ldarg.0
0x77d52  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::.ctor()
0x77d57  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxDayOfTheWeek
0x77d5c  ldarg.0
0x77d5d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x77d62  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77d67  ldarg.0
0x77d68  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77d6d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x77d72  ldarg.0
0x77d73  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x77d78  dup
0x77d79  ldarg.0
0x77d7a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::labelMonths
0x77d7f  ldstr    aLabelmonths// "labelMonths"
0x77d84  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x77d89  ldarg.0
0x77d8a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::labelMonths
0x77d8f  ldstr    aLabelmonths// "labelMonths"
0x77d94  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x77d99  ldarg.0
0x77d9a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77d9f  ldarg.0
0x77da0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxMonths
0x77da5  ldc.i4.2
0x77da6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x77dab  dup
0x77dac  ldarg.0
0x77dad  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxMonths
0x77db2  ldstr    aCheckedlistcom_0// "checkedListComboBoxMonths"
0x77db7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x77dbc  ldarg.0
0x77dbd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxMonths
0x77dc2  ldstr    aCheckedlistcom_0// "checkedListComboBoxMonths"
0x77dc7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x77dcc  ldarg.0
0x77dcd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxMonths
0x77dd2  ldarg.0
0x77dd3  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::ControlsLostFocus(object sender, class [mscorlib]System.EventArgs e)
0x77dd9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x77dde  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_LostFocus(class [mscorlib]System.EventHandler)
0x77de3  dup
0x77de4  ldarg.0
0x77de5  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonMonth
0x77dea  ldstr    aRadiobuttonmon_0// "radioButtonMonth"
0x77def  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x77df4  ldarg.0
0x77df5  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonMonth
0x77dfa  ldc.i4.1
0x77dfb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x77e00  ldarg.0
0x77e01  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonMonth
0x77e06  ldstr    aRadiobuttonmon_0// "radioButtonMonth"
0x77e0b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x77e10  ldarg.0
0x77e11  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonMonth
0x77e16  ldc.i4.1
0x77e17  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x77e1c  ldarg.0
0x77e1d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonMonth
0x77e22  ldarg.0
0x77e23  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonDayOfMonth_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x77e29  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x77e2e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x77e33  dup
0x77e34  ldarg.0
0x77e35  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonDayOfWeek
0x77e3a  ldstr    aRadiobuttonday// "radioButtonDayOfWeek"
0x77e3f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x77e44  ldarg.0
0x77e45  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonDayOfWeek
0x77e4a  ldstr    aRadiobuttonday// "radioButtonDayOfWeek"
0x77e4f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x77e54  ldarg.0
0x77e55  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonDayOfWeek
0x77e5a  ldarg.0
0x77e5b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonDayOfWeek_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x77e61  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x77e66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x77e6b  ldarg.0
0x77e6c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::calendarCheckedListCombo
0x77e71  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0x77e76  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x77e7b  ldarg.0
0x77e7c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::calendarCheckedListCombo
0x77e81  ldc.i4.2
0x77e82  callvirt instance void [System.Windows.Forms]System.Windows.Forms.UserControl::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x77e87  ldarg.0
0x77e88  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77e8d  ldarg.0
0x77e8e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::calendarCheckedListCombo
0x77e93  ldc.i4.2
0x77e94  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x77e99  dup
0x77e9a  ldarg.0
0x77e9b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::calendarCheckedListCombo
0x77ea0  ldstr    aCalendarchecke_1// "calendarCheckedListCombo"
0x77ea5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x77eaa  ldarg.0
0x77eab  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::calendarCheckedListCombo
0x77eb0  ldstr    aCalendarchecke_1// "calendarCheckedListCombo"
0x77eb5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x77eba  ldarg.0
0x77ebb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::calendarCheckedListCombo
0x77ec0  ldarg.0
0x77ec1  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::ControlsLostFocus(object sender, class [mscorlib]System.EventArgs e)
0x77ec7  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x77ecc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_LostFocus(class [mscorlib]System.EventHandler)
0x77ed1  dup
0x77ed2  ldarg.0
0x77ed3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboHowOften
0x77ed8  ldstr    aCheckedlistcom_1// "checkedListComboHowOften"
0x77edd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x77ee2  ldarg.0
0x77ee3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboHowOften
0x77ee8  ldstr    aCheckedlistcom_1// "checkedListComboHowOften"
0x77eed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x77ef2  ldarg.0
0x77ef3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboHowOften
0x77ef8  ldarg.0
0x77ef9  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::ControlsLostFocus(object sender, class [mscorlib]System.EventArgs e)
0x77eff  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x77f04  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_LostFocus(class [mscorlib]System.EventHandler)
0x77f09  dup
0x77f0a  ldarg.0
0x77f0b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxDayOfTheWeek
0x77f10  ldstr    aCheckedlistcom_2// "checkedListComboBoxDayOfTheWeek"
0x77f15  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x77f1a  ldarg.0
0x77f1b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxDayOfTheWeek
0x77f20  ldstr    aCheckedlistcom_2// "checkedListComboBoxDayOfTheWeek"
0x77f25  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x77f2a  ldarg.0
0x77f2b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxDayOfTheWeek
0x77f30  ldarg.0
0x77f31  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::ControlsLostFocus(object sender, class [mscorlib]System.EventArgs e)
0x77f37  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x77f3c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_LostFocus(class [mscorlib]System.EventHandler)
0x77f41  dup
0x77f42  ldarg.0
0x77f43  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77f48  ldstr    aTablelayoutpan_19// "tableLayoutPanelMonthly"
0x77f4d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x77f52  ldarg.0
0x77f53  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77f58  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x77f5d  ldarg.0
0x77f5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonDayOfWeek
0x77f63  ldc.i4.0
0x77f64  ldc.i4.2
0x77f65  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x77f6a  ldarg.0
0x77f6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77f70  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x77f75  ldarg.0
0x77f76  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::labelMonths
0x77f7b  ldc.i4.0
0x77f7c  ldc.i4.0
0x77f7d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x77f82  ldarg.0
0x77f83  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77f88  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x77f8d  ldarg.0
0x77f8e  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::radioButtonMonth
0x77f93  ldc.i4.0
0x77f94  ldc.i4.1
0x77f95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x77f9a  ldarg.0
0x77f9b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77fa0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x77fa5  ldarg.0
0x77fa6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboHowOften
0x77fab  ldc.i4.1
0x77fac  ldc.i4.2
0x77fad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x77fb2  ldarg.0
0x77fb3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77fb8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x77fbd  ldarg.0
0x77fbe  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CalendarCheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::calendarCheckedListCombo
0x77fc3  ldc.i4.1
0x77fc4  ldc.i4.1
0x77fc5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x77fca  ldarg.0
0x77fcb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77fd0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x77fd5  ldarg.0
0x77fd6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxMonths
0x77fdb  ldc.i4.1
0x77fdc  ldc.i4.0
0x77fdd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x77fe2  ldarg.0
0x77fe3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x77fe8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x77fed  ldarg.0
0x77fee  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::checkedListComboBoxDayOfTheWeek
0x77ff3  ldc.i4.2
0x77ff4  ldc.i4.2
0x77ff5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x77ffa  ldarg.0
0x77ffb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x78000  ldstr    aTablelayoutpan_19// "tableLayoutPanelMonthly"
0x78005  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7800a  ldarg.0
0x7800b  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x78010  ldarg.0
0x78011  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x78016  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7801b  ldarg.0
0x7801c  ldstr    aThis// "$this"
0x78021  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x78026  ldarg.0
0x78027  ldstr    aControlonsched_1// "ControlOnScheduleMonthly"
0x7802c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x78031  ldarg.0
0x78032  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x78037  ldc.i4.0
0x78038  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x7803d  ldarg.0
0x7803e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::tableLayoutPanelMonthly
0x78043  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x78048  ldarg.0
0x78049  ldc.i4.0
0x7804a  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x7804f  ret
```
