# Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::.ctor

- ea: `0x79a50`
- end: `0x79d0d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::.ctor`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x79290`

## callees

- `0x12ed0`
- `0x13670`
- `0x137b0`
- `0x608e0`
- `0x63e50`
- `0x64630`
- `0x74df0`
- `0x74f20`
- `0x74fe0`
- `0x76100`
- `0x76220`
- `0x76250`
- `0x78d30`
- `0x79a30`
- `0x79a50`
- `0x7a7a0`
- `0x7a8a0`
- `0x7c300`
- `0x7c420`

## string_xrefs

- `0x79c73`: `ComboEntryOnEvent`
- `0x79c4b`: `ComboEntryOnIdle`
- `0x79c8d`: `ComboEntryOnTSConnect`
- `0x79c9a`: `ComboEntryOnTSDisconnect`
- `0x79ca7`: `ComboEntryOnLock`
- `0x79cb4`: `ComboEntryOnUnlock`
- `0x79c3e`: `ComboEntryAtStartUp`
- `0x79c80`: `ComboEntryImmediate`
- `0x79c31`: `ComboEntryAtLogOn`
- `0x79c24`: `ComboEntryOnSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x79a50  ldarg.0
0x79a51  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::.ctor()
0x79a56  ldarg.0
0x79a57  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::InitializeComponent()
0x79a5c  ldarg.0
0x79a5d  ldc.i4.1
0x79a5e  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::flagDuringInitialization
0x79a63  ldarg.0
0x79a64  ldarg.2
0x79a65  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x79a6a  ldarg.0
0x79a6b  ldarg.3
0x79a6c  stfld    valuetype UserChoice Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::userChoiceAction
0x79a71  ldarg.0
0x79a72  ldarg.s  4
0x79a74  stfld    class DisplayTriggerDelegate Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::triggerDisplayDelegate
0x79a79  ldarg.0
0x79a7a  ldarg.s  5
0x79a7c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x79a81  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x79a86  stfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::taskVersion
0x79a8b  ldarg.0
0x79a8c  ldarg.0
0x79a8d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonCancel
0x79a92  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_CancelButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x79a97  ldarg.0
0x79a98  ldarg.0
0x79a99  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonOK
0x79a9e  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_AcceptButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x79aa3  ldarg.0
0x79aa4  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79aa9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x79aae  ldarg.0
0x79aaf  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::.ctor()
0x79ab4  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x79ab9  ldarg.0
0x79aba  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x79abf  ldc.i4.5
0x79ac0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x79ac5  ldarg.0
0x79ac6  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79acb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x79ad0  ldarg.0
0x79ad1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x79ad6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x79adb  ldarg.0
0x79adc  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger::.ctor()
0x79ae1  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x79ae6  ldarg.0
0x79ae7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x79aec  ldc.i4.5
0x79aed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x79af2  ldarg.0
0x79af3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x79af8  ldc.i4.0
0x79af9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x79afe  ldarg.0
0x79aff  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79b04  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x79b09  ldarg.0
0x79b0a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x79b0f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x79b14  ldarg.0
0x79b15  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::.ctor()
0x79b1a  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79b1f  ldarg.0
0x79b20  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79b25  ldarg.s  5
0x79b27  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::set_CurrentTask(class Microsoft.Windows.ManagementUI.CombinedControls.UITask value)
0x79b2c  ldarg.0
0x79b2d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79b32  ldarg.0
0x79b33  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::taskVersion
0x79b38  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::set_TaskVersion(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x79b3d  ldarg.0
0x79b3e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79b43  ldc.i4.5
0x79b44  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x79b49  ldarg.0
0x79b4a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79b4f  ldc.i4.0
0x79b50  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x79b55  ldarg.0
0x79b56  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79b5b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x79b60  ldarg.0
0x79b61  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79b66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x79b6b  ldc.i4.1
0x79b6c  ldarg.0
0x79b6d  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::taskVersion
0x79b72  bge.s    loc_79BBA
0x79b74  ldarg.0
0x79b75  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet::.ctor()
0x79b7a  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x79b7f  ldarg.0
0x79b80  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x79b85  ldc.i4.5
0x79b86  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x79b8b  ldarg.0
0x79b8c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x79b91  ldc.i4.0
0x79b92  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x79b97  ldarg.0
0x79b98  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x79b9d  ldarg.s  5
0x79b9f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UITask inCurrentTask)
0x79ba4  ldarg.0
0x79ba5  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79baa  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x79baf  ldarg.0
0x79bb0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x79bb5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x79bba  ldarg.0
0x79bbb  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::.ctor()
0x79bc0  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x79bc5  ldarg.0
0x79bc6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x79bcb  ldc.i4.5
0x79bcc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x79bd1  ldarg.0
0x79bd2  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x79bd7  ldc.i4.0
0x79bd8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x79bdd  ldarg.0
0x79bde  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79be3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x79be8  ldarg.0
0x79be9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x79bee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x79bf3  ldarg.0
0x79bf4  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79bf9  ldc.i4.5
0x79bfa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x79bff  ldarg.0
0x79c00  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79c05  ldc.i4.0
0x79c06  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x79c0b  ldarg.0
0x79c0c  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x79c11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x79c16  ldarg.0
0x79c17  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x79c1c  ldc.i4.4
0x79c1d  newarr   [mscorlib]System.Object
0x79c22  dup
0x79c23  ldc.i4.0
0x79c24  ldstr    aComboentryonsc// "ComboEntryOnSchedule"
0x79c29  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79c2e  stelem.ref
0x79c2f  dup
0x79c30  ldc.i4.1
0x79c31  ldstr    aComboentryatlo// "ComboEntryAtLogOn"
0x79c36  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79c3b  stelem.ref
0x79c3c  dup
0x79c3d  ldc.i4.2
0x79c3e  ldstr    aComboentryatst// "ComboEntryAtStartUp"
0x79c43  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79c48  stelem.ref
0x79c49  dup
0x79c4a  ldc.i4.3
0x79c4b  ldstr    aComboentryonid// "ComboEntryOnIdle"
0x79c50  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79c55  stelem.ref
0x79c56  ldc.i4.0
0x79c57  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddRangeToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object[] objects, int32 defaultIndex)
0x79c5c  ldc.i4.1
0x79c5d  ldarg.0
0x79c5e  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::taskVersion
0x79c63  bge.s    loc_79CC5
0x79c65  ldarg.0
0x79c66  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x79c6b  ldc.i4.6
0x79c6c  newarr   [mscorlib]System.Object
0x79c71  dup
0x79c72  ldc.i4.0
0x79c73  ldstr    aComboentryonev// "ComboEntryOnEvent"
0x79c78  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79c7d  stelem.ref
0x79c7e  dup
0x79c7f  ldc.i4.1
0x79c80  ldstr    aComboentryimme// "ComboEntryImmediate"
0x79c85  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79c8a  stelem.ref
0x79c8b  dup
0x79c8c  ldc.i4.2
0x79c8d  ldstr    aComboentryonts// "ComboEntryOnTSConnect"
0x79c92  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79c97  stelem.ref
0x79c98  dup
0x79c99  ldc.i4.3
0x79c9a  ldstr    aComboentryonts_0// "ComboEntryOnTSDisconnect"
0x79c9f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79ca4  stelem.ref
0x79ca5  dup
0x79ca6  ldc.i4.4
0x79ca7  ldstr    aComboentryonlo// "ComboEntryOnLock"
0x79cac  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79cb1  stelem.ref
0x79cb2  dup
0x79cb3  ldc.i4.5
0x79cb4  ldstr    aComboentryonun// "ComboEntryOnUnlock"
0x79cb9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79cbe  stelem.ref
0x79cbf  ldc.i4.0
0x79cc0  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddRangeToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object[] objects, int32 defaultIndex)
0x79cc5  ldarg.1
0x79cc6  brtrue.s loc_79CDB
0x79cc8  ldarg.0
0x79cc9  ldarg.0
0x79cca  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x79ccf  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::get_CurrentTrigger()
0x79cd4  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger value)
0x79cd9  br.s     loc_79CE2
0x79cdb  ldarg.0
0x79cdc  ldarg.1
0x79cdd  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger value)
0x79ce2  ldarg.0
0x79ce3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x79ce8  ldarg.0
0x79ce9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x79cee  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_DisplayType()
0x79cf3  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl, string val)
0x79cf8  ldarg.s  6
0x79cfa  brfalse.s loc_79D05
0x79cfc  ldarg.0
0x79cfd  ldarg.s  6
0x79cff  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::HandleDataValidationError(class Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException e)
0x79d04  pop
0x79d05  ldarg.0
0x79d06  ldc.i4.0
0x79d07  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::flagDuringInitialization
0x79d0c  ret
```
