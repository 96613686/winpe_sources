# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::UpdateTrigger

- ea: `0x76690`
- end: `0x7678a`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::UpdateTrigger`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x76220`

## callees

- `0x12ed0`
- `0x136e0`
- `0x76690`
- `0x76e40`
- `0x76e80`
- `0x77190`
- `0x77200`
- `0x78060`
- `0x78080`
- `0x78ba0`
- `0x78bc0`

## string_xrefs

- `0x76718`: `ComboEntryWeekly`
- `0x76753`: `ComboEntryMonthly`
- `0x766dd`: `ComboEntryDaily`
- `0x766a2`: `ComboEntryOneTime`

## pseudocode

```c

```

## disassembly

```asm
0x76690  ldarg.0
0x76691  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::datePickerStart
0x76696  call     valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::GetDateTimeValue(class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker dateTimePicker)
0x7669b  stloc.0
0x7669c  ldarg.0
0x7669d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x766a2  ldstr    aComboentryonet// "ComboEntryOneTime"
0x766a7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x766ac  ldc.i4.0
0x766ad  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x766b2  brtrue.s loc_766D7
0x766b4  ldarg.0
0x766b5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlOneTime
0x766ba  ldloc.0
0x766bb  ldarg.0
0x766bc  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::checkBoxUtcTime
0x766c1  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x766c6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime::SetStartTime(valuetype [mscorlib]System.DateTime startTime, bool isUtcTime)
0x766cb  ldarg.0
0x766cc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlOneTime
0x766d1  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITimeTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime::get_CurrentTrigger()
0x766d6  ret
0x766d7  ldarg.0
0x766d8  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x766dd  ldstr    aComboentrydail// "ComboEntryDaily"
0x766e2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x766e7  ldc.i4.0
0x766e8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x766ed  brtrue.s loc_76712
0x766ef  ldarg.0
0x766f0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlDaily
0x766f5  ldloc.0
0x766f6  ldarg.0
0x766f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::checkBoxUtcTime
0x766fc  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x76701  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily::SetStartTime(valuetype [mscorlib]System.DateTime startTime, bool isUtcTime)
0x76706  ldarg.0
0x76707  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlDaily
0x7670c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIDailyTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily::get_CurrentTrigger()
0x76711  ret
0x76712  ldarg.0
0x76713  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x76718  ldstr    aComboentryweek// "ComboEntryWeekly"
0x7671d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x76722  ldc.i4.0
0x76723  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x76728  brtrue.s loc_7674D
0x7672a  ldarg.0
0x7672b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleWeekly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlWeekly
0x76730  ldloc.0
0x76731  ldarg.0
0x76732  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::checkBoxUtcTime
0x76737  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x7673c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleWeekly::SetStartTime(valuetype [mscorlib]System.DateTime startTime, bool isUtcTime)
0x76741  ldarg.0
0x76742  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleWeekly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlWeekly
0x76747  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIWeeklyTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleWeekly::get_CurrentTrigger()
0x7674c  ret
0x7674d  ldarg.0
0x7674e  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x76753  ldstr    aComboentrymont// "ComboEntryMonthly"
0x76758  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7675d  ldc.i4.0
0x7675e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x76763  brtrue.s loc_76788
0x76765  ldarg.0
0x76766  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlMonthly
0x7676b  ldloc.0
0x7676c  ldarg.0
0x7676d  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::checkBoxUtcTime
0x76772  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x76777  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::SetStartTime(valuetype [mscorlib]System.DateTime startTime, bool isStartTimeUtc)
0x7677c  ldarg.0
0x7677d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlMonthly
0x76782  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::get_CurrentTrigger()
0x76787  ret
0x76788  ldnull
0x76789  ret
```
