# Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::Initialize

- ea: `0x69a90`
- end: `0x69c9f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::Initialize`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x68ff0`

## callees

- `0x12ed0`
- `0x13670`
- `0x137d0`
- `0x5f8e0`
- `0x5f8f0`
- `0x69a90`
- `0x69e30`
- `0x6a530`
- `0x6a550`
- `0x6a570`
- `0x6ad20`
- `0x6b6e0`

## string_xrefs

- `0x69b31`: `ComboEntryStartProgramAction`
- `0x69c67`: `ComboEntryStartProgramAction`
- `0x69bf0`: `ComboEntrySendEmailAction`
- `0x69c05`: `ComboEntrySendMessageAction`

## pseudocode

```c

```

## disassembly

```asm
0x69a90  ldarg.0
0x69a91  ldarg.2
0x69a92  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x69a97  ldarg.0
0x69a98  ldarg.0
0x69a99  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonCancel
0x69a9e  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_CancelButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x69aa3  ldarg.0
0x69aa4  ldarg.0
0x69aa5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonOk
0x69aaa  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_AcceptButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x69aaf  ldarg.0
0x69ab0  ldarg.s  4
0x69ab2  stfld    class DisplayActionDelegate Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::actionDisplayDelegate
0x69ab7  ldarg.0
0x69ab8  ldarg.3
0x69ab9  stfld    valuetype UserChoice Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::userAction
0x69abe  ldarg.0
0x69abf  ldarg.s  5
0x69ac1  stfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::taskVersion
0x69ac6  ldarg.0
0x69ac7  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::.ctor()
0x69acc  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69ad1  ldarg.0
0x69ad2  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69ad7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::Initialize()
0x69adc  ldarg.0
0x69add  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69ae2  ldarg.0
0x69ae3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69ae8  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_Size()
0x69aed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x69af2  ldarg.0
0x69af3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69af8  ldc.i4.0
0x69af9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x69afe  ldarg.0
0x69aff  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69b04  ldc.i4.5
0x69b05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x69b0a  ldarg.0
0x69b0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69b10  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x69b15  ldarg.0
0x69b16  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69b1b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x69b20  ldarg.0
0x69b21  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69b26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x69b2b  ldarg.0
0x69b2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x69b31  ldstr    aComboentrystar// "ComboEntryStartProgramAction"
0x69b36  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69b3b  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x69b40  ldc.i4.1
0x69b41  ldarg.0
0x69b42  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::taskVersion
0x69b47  bge      loc_69C14
0x69b4c  ldarg.0
0x69b4d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction::.ctor()
0x69b52  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69b57  ldarg.0
0x69b58  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69b5d  ldarg.0
0x69b5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69b63  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_Size()
0x69b68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x69b6d  ldarg.0
0x69b6e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69b73  ldc.i4.0
0x69b74  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x69b79  ldarg.0
0x69b7a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69b7f  ldc.i4.5
0x69b80  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x69b85  ldarg.0
0x69b86  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69b8b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x69b90  ldarg.0
0x69b91  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69b96  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x69b9b  ldarg.0
0x69b9c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction::.ctor()
0x69ba1  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69ba6  ldarg.0
0x69ba7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69bac  ldarg.0
0x69bad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69bb2  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_Size()
0x69bb7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x69bbc  ldarg.0
0x69bbd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69bc2  ldc.i4.0
0x69bc3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x69bc8  ldarg.0
0x69bc9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69bce  ldc.i4.5
0x69bcf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x69bd4  ldarg.0
0x69bd5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69bda  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x69bdf  ldarg.0
0x69be0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69be5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x69bea  ldarg.0
0x69beb  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x69bf0  ldstr    aComboentrysend// "ComboEntrySendEmailAction"
0x69bf5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69bfa  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x69bff  ldarg.0
0x69c00  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x69c05  ldstr    aComboentrysend_0// "ComboEntrySendMessageAction"
0x69c0a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69c0f  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x69c14  ldarg.0
0x69c15  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69c1a  ldc.i4.0
0x69c1b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x69c20  ldarg.0
0x69c21  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x69c26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x69c2b  ldarg.0
0x69c2c  ldc.i4.1
0x69c2d  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::flagInitializedAction
0x69c32  ldarg.1
0x69c33  brtrue.s loc_69C48
0x69c35  ldarg.0
0x69c36  ldarg.0
0x69c37  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69c3c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::get_CurrentAction()
0x69c41  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69c46  br.s     loc_69C4F
0x69c48  ldarg.0
0x69c49  ldarg.1
0x69c4a  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69c4f  ldarg.0
0x69c50  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69c55  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_DisplayType()
0x69c5a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x69c5f  brfalse.s loc_69C76
0x69c61  ldarg.0
0x69c62  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69c67  ldstr    aComboentrystar// "ComboEntryStartProgramAction"
0x69c6c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69c71  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayType(string value)
0x69c76  ldarg.0
0x69c77  ldarg.0
0x69c78  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69c7d  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_DisplayType()
0x69c82  ldc.i4.0
0x69c83  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::SwitchAction(string selectedAction, bool newAction)
0x69c88  ldarg.0
0x69c89  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x69c8e  ldarg.0
0x69c8f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69c94  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_DisplayType()
0x69c99  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl, string val)
0x69c9e  ret
```
