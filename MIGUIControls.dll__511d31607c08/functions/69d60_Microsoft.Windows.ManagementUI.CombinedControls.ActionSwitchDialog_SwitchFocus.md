# Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::SwitchFocus

- ea: `0x69d60`
- end: `0x69dd3`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::SwitchFocus`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x69fe0`

## callees

- `0x12ed0`
- `0x69990`
- `0x69d60`

## string_xrefs

- `0x69d66`: `ComboEntryStartProgramAction`
- `0x69d92`: `ComboEntrySendEmailAction`
- `0x69db5`: `ComboEntrySendMessageAction`

## pseudocode

```c

```

## disassembly

```asm
0x69d60  ldarg.0
0x69d61  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::stringSelectedAction
0x69d66  ldstr    aComboentrystar// "ComboEntryStartProgramAction"
0x69d6b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69d70  ldc.i4.0
0x69d71  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69d76  brtrue.s loc_69D83
0x69d78  ldarg.0
0x69d79  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlExecutableActionControl
0x69d7e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl::SetFocus()
0x69d83  ldc.i4.1
0x69d84  ldarg.0
0x69d85  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::taskVersion
0x69d8a  bge.s    loc_69DD2
0x69d8c  ldarg.0
0x69d8d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::stringSelectedAction
0x69d92  ldstr    aComboentrysend// "ComboEntrySendEmailAction"
0x69d97  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69d9c  ldc.i4.0
0x69d9d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69da2  brtrue.s loc_69DAF
0x69da4  ldarg.0
0x69da5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlEmailAction
0x69daa  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl::SetFocus()
0x69daf  ldarg.0
0x69db0  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::stringSelectedAction
0x69db5  ldstr    aComboentrysend_0// "ComboEntrySendMessageAction"
0x69dba  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69dbf  ldc.i4.0
0x69dc0  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69dc5  brtrue.s loc_69DD2
0x69dc7  ldarg.0
0x69dc8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlNotificationAction Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::controlNotificationAction
0x69dcd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseUIActionControl::SetFocus()
0x69dd2  ret
```
