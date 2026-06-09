# Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::UpdateAction

- ea: `0x69cc0`
- end: `0x69d57`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::UpdateAction`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x69de0`

## callees

- `0x12ed0`
- `0x69cc0`
- `0x6a530`
- `0x6a810`
- `0x6ad00`
- `0x6b6c0`

## string_xrefs

- `0x69cc8`: `ComboEntryStartProgramAction`
- `0x69d09`: `ComboEntrySendEmailAction`
- `0x69d32`: `ComboEntrySendMessageAction`

## pseudocode

```c

```

## disassembly

```asm
0x69cc0  ldc.i4.1
0x69cc1  stloc.0
0x69cc2  ldarg.0
0x69cc3  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::stringSelectedAction
0x69cc8  ldstr    aComboentrystar// "ComboEntryStartProgramAction"
0x69ccd  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69cd2  ldc.i4.0
0x69cd3  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69cd8  brtrue.s loc_69CFA
0x69cda  ldarg.0
0x69cdb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69ce0  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::UpdateAction()
0x69ce5  stloc.0
0x69ce6  ldloc.0
0x69ce7  brfalse.s loc_69CFA
0x69ce9  ldarg.0
0x69cea  ldarg.0
0x69ceb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69cf0  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::get_CurrentAction()
0x69cf5  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69cfa  ldc.i4.1
0x69cfb  ldarg.0
0x69cfc  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::taskVersion
0x69d01  bge.s    loc_69D55
0x69d03  ldarg.0
0x69d04  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::stringSelectedAction
0x69d09  ldstr    aComboentrysend// "ComboEntrySendEmailAction"
0x69d0e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69d13  ldc.i4.0
0x69d14  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69d19  brtrue.s loc_69D2C
0x69d1b  ldarg.0
0x69d1c  ldarg.0
0x69d1d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69d22  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction::get_CurrentAction()
0x69d27  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69d2c  ldarg.0
0x69d2d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::stringSelectedAction
0x69d32  ldstr    aComboentrysend_0// "ComboEntrySendMessageAction"
0x69d37  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69d3c  ldc.i4.0
0x69d3d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69d42  brtrue.s loc_69D55
0x69d44  ldarg.0
0x69d45  ldarg.0
0x69d46  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69d4b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction::get_CurrentAction()
0x69d50  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::uiActionCurrent
0x69d55  ldloc.0
0x69d56  ret
```
