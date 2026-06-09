# Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::SavePreviousAdvancedSettings

- ea: `0x79d30`
- end: `0x79f53`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::SavePreviousAdvancedSettings`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x79f60`

## callees

- `0x12ed0`
- `0x60930`
- `0x74f00`
- `0x760e0`
- `0x76220`
- `0x78cd0`
- `0x78d00`
- `0x79d30`
- `0x7ad50`
- `0x7c3c0`

## string_xrefs

- `0x79d84`: `ComboEntryWeekly`
- `0x79d71`: `ComboEntryMonthly`
- `0x79d5e`: `ComboEntryDaily`
- `0x79e1f`: `ComboEntryOnEvent`
- `0x79d4b`: `ComboEntryOneTime`
- `0x79e7d`: `ComboEntryOnIdle`
- `0x79eac`: `ComboEntryOnTSConnect`
- `0x79ed6`: `ComboEntryOnTSDisconnect`
- `0x79f00`: `ComboEntryOnLock`
- `0x79f2a`: `ComboEntryOnUnlock`
- `0x79df0`: `ComboEntryAtStartUp`
- `0x79e4e`: `ComboEntryImmediate`
- `0x79dc6`: `ComboEntryAtLogOn`
- `0x79d97`: `ComboEntryOnSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x79d30  ldarg.2
0x79d31  brfalse.s loc_79D4A
0x79d33  ldarg.0
0x79d34  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x79d39  ldarg.0
0x79d3a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79d3f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79d44  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79d49  ret
0x79d4a  ldarg.1
0x79d4b  ldstr    aComboentryonet// "ComboEntryOneTime"
0x79d50  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79d55  ldc.i4.0
0x79d56  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79d5b  brfalse.s loc_79DA9
0x79d5d  ldarg.1
0x79d5e  ldstr    aComboentrydail// "ComboEntryDaily"
0x79d63  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79d68  ldc.i4.0
0x79d69  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79d6e  brfalse.s loc_79DA9
0x79d70  ldarg.1
0x79d71  ldstr    aComboentrymont// "ComboEntryMonthly"
0x79d76  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79d7b  ldc.i4.0
0x79d7c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79d81  brfalse.s loc_79DA9
0x79d83  ldarg.1
0x79d84  ldstr    aComboentryweek// "ComboEntryWeekly"
0x79d89  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79d8e  ldc.i4.0
0x79d8f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79d94  brfalse.s loc_79DA9
0x79d96  ldarg.1
0x79d97  ldstr    aComboentryonsc// "ComboEntryOnSchedule"
0x79d9c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79da1  ldc.i4.0
0x79da2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79da7  brtrue.s loc_79DC5
0x79da9  ldarg.0
0x79daa  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x79daf  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::get_CurrentTrigger()
0x79db4  ldarg.0
0x79db5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79dba  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79dbf  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79dc4  ret
0x79dc5  ldarg.1
0x79dc6  ldstr    aComboentryatlo// "ComboEntryAtLogOn"
0x79dcb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79dd0  ldc.i4.0
0x79dd1  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79dd6  brtrue.s loc_79DEF
0x79dd8  ldarg.0
0x79dd9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79dde  ldarg.0
0x79ddf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79de4  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79de9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79dee  ret
0x79def  ldarg.1
0x79df0  ldstr    aComboentryatst// "ComboEntryAtStartUp"
0x79df5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79dfa  ldc.i4.0
0x79dfb  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79e00  brtrue.s loc_79E1E
0x79e02  ldarg.0
0x79e03  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x79e08  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAtStartupTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::get_CurrentStartTrigger()
0x79e0d  ldarg.0
0x79e0e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79e13  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79e18  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79e1d  ret
0x79e1e  ldarg.1
0x79e1f  ldstr    aComboentryonev// "ComboEntryOnEvent"
0x79e24  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79e29  ldc.i4.0
0x79e2a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79e2f  brtrue.s loc_79E4D
0x79e31  ldarg.0
0x79e32  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x79e37  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet::get_CurrentTrigger()
0x79e3c  ldarg.0
0x79e3d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79e42  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79e47  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79e4c  ret
0x79e4d  ldarg.1
0x79e4e  ldstr    aComboentryimme// "ComboEntryImmediate"
0x79e53  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79e58  ldc.i4.0
0x79e59  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79e5e  brtrue.s loc_79E7C
0x79e60  ldarg.0
0x79e61  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x79e66  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIImmediateTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::get_CurrentImmediateTrigger()
0x79e6b  ldarg.0
0x79e6c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79e71  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79e76  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79e7b  ret
0x79e7c  ldarg.1
0x79e7d  ldstr    aComboentryonid// "ComboEntryOnIdle"
0x79e82  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79e87  ldc.i4.0
0x79e88  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79e8d  brtrue.s loc_79EAB
0x79e8f  ldarg.0
0x79e90  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x79e95  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger::get_CurrentTrigger()
0x79e9a  ldarg.0
0x79e9b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79ea0  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79ea5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79eaa  ret
0x79eab  ldarg.1
0x79eac  ldstr    aComboentryonts// "ComboEntryOnTSConnect"
0x79eb1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79eb6  ldc.i4.0
0x79eb7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79ebc  brtrue.s loc_79ED5
0x79ebe  ldarg.0
0x79ebf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79ec4  ldarg.0
0x79ec5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79eca  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79ecf  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79ed4  ret
0x79ed5  ldarg.1
0x79ed6  ldstr    aComboentryonts_0// "ComboEntryOnTSDisconnect"
0x79edb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79ee0  ldc.i4.0
0x79ee1  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79ee6  brtrue.s loc_79EFF
0x79ee8  ldarg.0
0x79ee9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79eee  ldarg.0
0x79eef  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79ef4  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79ef9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79efe  ret
0x79eff  ldarg.1
0x79f00  ldstr    aComboentryonlo// "ComboEntryOnLock"
0x79f05  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79f0a  ldc.i4.0
0x79f0b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79f10  brtrue.s loc_79F29
0x79f12  ldarg.0
0x79f13  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79f18  ldarg.0
0x79f19  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79f1e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79f23  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79f28  ret
0x79f29  ldarg.1
0x79f2a  ldstr    aComboentryonun// "ComboEntryOnUnlock"
0x79f2f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79f34  ldc.i4.0
0x79f35  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79f3a  brtrue.s loc_79F52
0x79f3c  ldarg.0
0x79f3d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x79f42  ldarg.0
0x79f43  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x79f48  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x79f4d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::set_AdvancedSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings value)
0x79f52  ret
```
