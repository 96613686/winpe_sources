# Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::InitializeComponent

- ea: `0x8a650`
- end: `0x8a833`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::InitializeComponent`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a440`

## callees

- `0x187d0`
- `0x187e0`
- `0x76ea0`

## string_xrefs

- `0x8a6c0`: `controlOnScheduleDaily1`
- `0x8a6d0`: `controlOnScheduleDaily1`

## pseudocode

```c

```

## disassembly

```asm
0x8a650  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl
0x8a655  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8a65a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x8a65f  ldarg.0
0x8a660  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily::.ctor()
0x8a665  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::controlOnScheduleDaily1
0x8a66a  ldarg.0
0x8a66b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker::.ctor()
0x8a670  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::dateTimePickerStartTimeUser
0x8a675  ldarg.0
0x8a676  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8a67b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::labelStart
0x8a680  ldarg.0
0x8a681  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x8a686  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::checkBoxIsUtcTime
0x8a68b  ldarg.0
0x8a68c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x8a691  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a696  ldarg.0
0x8a697  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a69c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8a6a1  ldarg.0
0x8a6a2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8a6a7  ldarg.0
0x8a6a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a6ad  ldarg.0
0x8a6ae  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::controlOnScheduleDaily1
0x8a6b3  ldc.i4.3
0x8a6b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x8a6b9  dup
0x8a6ba  ldarg.0
0x8a6bb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::controlOnScheduleDaily1
0x8a6c0  ldstr    aControlonsched_5// "controlOnScheduleDaily1"
0x8a6c5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8a6ca  ldarg.0
0x8a6cb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::controlOnScheduleDaily1
0x8a6d0  ldstr    aControlonsched_5// "controlOnScheduleDaily1"
0x8a6d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8a6da  dup
0x8a6db  ldarg.0
0x8a6dc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::dateTimePickerStartTimeUser
0x8a6e1  ldstr    aDatetimepicker_3// "dateTimePickerStartTimeUser"
0x8a6e6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8a6eb  ldarg.0
0x8a6ec  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::dateTimePickerStartTimeUser
0x8a6f1  ldstr    aDatetimepicker_3// "dateTimePickerStartTimeUser"
0x8a6f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8a6fb  ldarg.0
0x8a6fc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::dateTimePickerStartTimeUser
0x8a701  ldc.i4   0x7D6
0x8a706  ldc.i4.4
0x8a707  ldc.i4.s 0x19
0x8a709  ldc.i4.s 0x12
0x8a70b  ldc.i4.s 9
0x8a70d  ldc.i4.s 0x18
0x8a70f  ldc.i4   0x32B
0x8a714  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, int32)
0x8a719  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker::set_Value(valuetype [mscorlib]System.DateTime value)
0x8a71e  dup
0x8a71f  ldarg.0
0x8a720  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::labelStart
0x8a725  ldstr    aLabelstart// "labelStart"
0x8a72a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8a72f  ldarg.0
0x8a730  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::labelStart
0x8a735  ldstr    aLabelstart// "labelStart"
0x8a73a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8a73f  dup
0x8a740  ldarg.0
0x8a741  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::checkBoxIsUtcTime
0x8a746  ldstr    aCheckboxisutct// "checkBoxIsUtcTime"
0x8a74b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8a750  ldarg.0
0x8a751  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::checkBoxIsUtcTime
0x8a756  ldstr    aCheckboxisutct// "checkBoxIsUtcTime"
0x8a75b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8a760  ldarg.0
0x8a761  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::checkBoxIsUtcTime
0x8a766  ldc.i4.1
0x8a767  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8a76c  dup
0x8a76d  ldarg.0
0x8a76e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a773  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x8a778  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8a77d  ldarg.0
0x8a77e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a783  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8a788  ldarg.0
0x8a789  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::controlOnScheduleDaily1
0x8a78e  ldc.i4.0
0x8a78f  ldc.i4.1
0x8a790  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8a795  ldarg.0
0x8a796  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a79b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8a7a0  ldarg.0
0x8a7a1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::dateTimePickerStartTimeUser
0x8a7a6  ldc.i4.1
0x8a7a7  ldc.i4.0
0x8a7a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8a7ad  ldarg.0
0x8a7ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a7b3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8a7b8  ldarg.0
0x8a7b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::checkBoxIsUtcTime
0x8a7be  ldc.i4.2
0x8a7bf  ldc.i4.0
0x8a7c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8a7c5  ldarg.0
0x8a7c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a7cb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8a7d0  ldarg.0
0x8a7d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::labelStart
0x8a7d6  ldc.i4.0
0x8a7d7  ldc.i4.0
0x8a7d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8a7dd  ldarg.0
0x8a7de  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a7e3  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x8a7e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8a7ed  ldarg.0
0x8a7ee  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x8a7f3  ldarg.0
0x8a7f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a7f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x8a7fe  ldarg.0
0x8a7ff  ldstr    aThis// "$this"
0x8a804  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8a809  ldarg.0
0x8a80a  ldstr    aWizardtriggerd// "WizardTriggerDailyControl"
0x8a80f  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8a814  ldarg.0
0x8a815  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a81a  ldc.i4.0
0x8a81b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x8a820  ldarg.0
0x8a821  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerDailyControl::tableLayoutPanel
0x8a826  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x8a82b  ldarg.0
0x8a82c  ldc.i4.0
0x8a82d  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x8a832  ret
```
