# Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::SwitchAction

- ea: `0x69e30`
- end: `0x69f94`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::SwitchAction`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x69a90`
- `0x69fc0`

## callees

- `0x12ed0`
- `0x14500`
- `0x14550`
- `0x145b0`
- `0x69980`
- `0x69990`
- `0x69e30`
- `0x6a530`
- `0x6a540`
- `0x6ad00`
- `0x6ad10`
- `0x6b6c0`
- `0x6b6d0`

## string_xrefs

- `0x69e45`: `ComboEntryStartProgramAction`
- `0x69e8b`: `ComboEntrySendEmailAction`
- `0x69ed7`: `ComboEntrySendMessageAction`

## pseudocode

```c

```

## disassembly

```asm
0x69e30  ldarg.0
0x69e31  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::flagInitializedAction
0x69e36  brfalse  loc_69F93
0x69e3b  ldnull
0x69e3c  stloc.0
0x69e3d  ldarg.0
0x69e3e  ldarg.1
0x69e3f  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::stringSelectedAction
0x69e44  ldarg.1
0x69e45  ldstr    aComboentrystar// "ComboEntryStartProgramAction"
0x69e4a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69e4f  ldc.i4.0
0x69e50  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69e55  brtrue.s loc_69E8A
0x69e57  ldarg.2
0x69e58  brtrue.s loc_69E6D
0x69e5a  ldarg.0
0x69e5b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69e60  ldarg.0
0x69e61  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69e66  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::set_CurrentAction(class Microsoft.Windows.ManagementUI.CombinedControls.UIAction value)
0x69e6b  br.s     loc_69E7E
0x69e6d  ldarg.0
0x69e6e  ldarg.0
0x69e6f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69e74  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::get_CurrentAction()
0x69e79  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69e7e  ldarg.0
0x69e7f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69e84  stloc.0
0x69e85  br       loc_69F20
0x69e8a  ldarg.1
0x69e8b  ldstr    aComboentrysend// "ComboEntrySendEmailAction"
0x69e90  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69e95  ldc.i4.0
0x69e96  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69e9b  brtrue.s loc_69ED6
0x69e9d  ldc.i4.1
0x69e9e  ldarg.0
0x69e9f  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::taskVersion
0x69ea4  bge.s    loc_69F20
0x69ea6  ldarg.2
0x69ea7  brtrue.s loc_69EBC
0x69ea9  ldarg.0
0x69eaa  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69eaf  ldarg.0
0x69eb0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69eb5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction::set_CurrentAction(class Microsoft.Windows.ManagementUI.CombinedControls.UIAction value)
0x69eba  br.s     loc_69ECD
0x69ebc  ldarg.0
0x69ebd  ldarg.0
0x69ebe  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69ec3  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction::get_CurrentAction()
0x69ec8  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69ecd  ldarg.0
0x69ece  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69ed3  stloc.0
0x69ed4  br.s     loc_69F20
0x69ed6  ldarg.1
0x69ed7  ldstr    aComboentrysend_0// "ComboEntrySendMessageAction"
0x69edc  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69ee1  ldc.i4.0
0x69ee2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69ee7  brtrue.s loc_69F20
0x69ee9  ldc.i4.1
0x69eea  ldarg.0
0x69eeb  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::taskVersion
0x69ef0  bge.s    loc_69F20
0x69ef2  ldarg.2
0x69ef3  brtrue.s loc_69F08
0x69ef5  ldarg.0
0x69ef6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69efb  ldarg.0
0x69efc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69f01  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction::set_CurrentAction(class Microsoft.Windows.ManagementUI.CombinedControls.UIAction value)
0x69f06  br.s     loc_69F19
0x69f08  ldarg.0
0x69f09  ldarg.0
0x69f0a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69f0f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction::get_CurrentAction()
0x69f14  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69f19  ldarg.0
0x69f1a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69f1f  stloc.0
0x69f20  ldloc.0
0x69f21  brfalse.s loc_69F93
0x69f23  ldarg.0
0x69f24  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::currentSelectedControl
0x69f29  brfalse.s loc_69F36
0x69f2b  ldarg.0
0x69f2c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::currentSelectedControl
0x69f31  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Hide()
0x69f36  ldarg.0
0x69f37  ldloc.0
0x69f38  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::currentSelectedControl
0x69f3d  ldarg.0
0x69f3e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::currentSelectedControl
0x69f43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Show()
0x69f48  ldarg.0
0x69f49  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::currentSelectedControl
0x69f4e  ldc.i4.0
0x69f4f  ldc.i4.0
0x69f50  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x69f55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x69f5a  ldarg.0
0x69f5b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::currentSelectedControl
0x69f60  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataHandler Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl::get_RequiredData()
0x69f65  ldarg.0
0x69f66  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::ParentControlDataHandler(bool requiredDataExists)
0x69f6c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler::.ctor(object object, native int method)
0x69f71  ldarg.0
0x69f72  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::currentSelectedControl
0x69f77  dup
0x69f78  ldvirtftn instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl::RequiredDataEntered()
0x69f7e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataEntered::.ctor(object object, native int method)
0x69f83  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataHandler::RegisterParentToNotify(class Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler inParentToInform, class Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataEntered inChild)
0x69f88  ldarg.0
0x69f89  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::currentSelectedControl
0x69f8e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl::SetFocus()
0x69f93  ret
```
