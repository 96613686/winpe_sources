# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::InitializeTriggers

- ea: `0x76550`
- end: `0x7668d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::InitializeTriggers`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x76230`
- `0x76250`

## callees

- `0x12ed0`
- `0x136c0`
- `0x14040`
- `0x60580`
- `0x605a0`
- `0x608e0`
- `0x60920`
- `0x76550`
- `0x767b0`
- `0x76e50`
- `0x771c0`
- `0x78070`
- `0x78bb0`
- `0x78bc0`

## string_xrefs

- `0x7661f`: `ComboEntryWeekly`
- `0x76656`: `ComboEntryMonthly`
- `0x765e8`: `ComboEntryDaily`
- `0x76597`: `ComboEntryOneTime`

## pseudocode

```c

```

## disassembly

```asm
0x76550  ldarg.1
0x76551  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_AdvancedSettings()
0x76556  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings::get_ActiveOn()
0x7655b  stloc.0
0x7655c  ldloc.0
0x7655d  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x76562  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x76567  brfalse.s loc_7656F
0x76569  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x7656e  stloc.0
0x7656f  ldarg.0
0x76570  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::datePickerStart
0x76575  ldloc.0
0x76576  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetDateTime(class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker dateTimePicker, valuetype [mscorlib]System.DateTime value)
0x7657b  ldarg.0
0x7657c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::checkBoxUtcTime
0x76581  ldarg.1
0x76582  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_AdvancedSettings()
0x76587  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings::get_IsActiveOnTimeUtc()
0x7658c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0x76591  ldarg.1
0x76592  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_DisplayType()
0x76597  ldstr    aComboentryonet// "ComboEntryOneTime"
0x7659c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x765a1  ldc.i4.0
0x765a2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x765a7  brtrue.s loc_765E2
0x765a9  ldarg.0
0x765aa  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlOneTime
0x765af  ldloc.0
0x765b0  ldarg.0
0x765b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::checkBoxUtcTime
0x765b6  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x765bb  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime::SetStartTime(valuetype [mscorlib]System.DateTime startTime, bool isUtcTime)
0x765c0  ldarg.0
0x765c1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlOneTime
0x765c6  ldarg.1
0x765c7  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITimeTrigger
0x765cc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UITimeTrigger value)
0x765d1  ldarg.0
0x765d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::radioButtonOneTime
0x765d7  ldc.i4.1
0x765d8  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheck(class [System.Windows.Forms]System.Windows.Forms.RadioButton button, bool set)
0x765dd  br       loc_76680
0x765e2  ldarg.1
0x765e3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_DisplayType()
0x765e8  ldstr    aComboentrydail// "ComboEntryDaily"
0x765ed  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x765f2  ldc.i4.0
0x765f3  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x765f8  brtrue.s loc_76619
0x765fa  ldarg.0
0x765fb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlDaily
0x76600  ldarg.1
0x76601  castclass Microsoft.Windows.ManagementUI.CombinedControls.UIDailyTrigger
0x76606  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UIDailyTrigger value)
0x7660b  ldarg.0
0x7660c  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::radioButtonDaily
0x76611  ldc.i4.1
0x76612  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheck(class [System.Windows.Forms]System.Windows.Forms.RadioButton button, bool set)
0x76617  br.s     loc_76680
0x76619  ldarg.1
0x7661a  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_DisplayType()
0x7661f  ldstr    aComboentryweek// "ComboEntryWeekly"
0x76624  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x76629  ldc.i4.0
0x7662a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7662f  brtrue.s loc_76650
0x76631  ldarg.0
0x76632  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleWeekly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlWeekly
0x76637  ldarg.1
0x76638  castclass Microsoft.Windows.ManagementUI.CombinedControls.UIWeeklyTrigger
0x7663d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleWeekly::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UIWeeklyTrigger value)
0x76642  ldarg.0
0x76643  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::radioButtonWeekly
0x76648  ldc.i4.1
0x76649  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheck(class [System.Windows.Forms]System.Windows.Forms.RadioButton button, bool set)
0x7664e  br.s     loc_76680
0x76650  ldarg.1
0x76651  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_DisplayType()
0x76656  ldstr    aComboentrymont// "ComboEntryMonthly"
0x7665b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x76660  ldc.i4.0
0x76661  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x76666  brtrue.s loc_76680
0x76668  ldarg.0
0x76669  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlMonthly
0x7666e  ldarg.1
0x7666f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger value)
0x76674  ldarg.0
0x76675  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::radioButtonMonthly
0x7667a  ldc.i4.1
0x7667b  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheck(class [System.Windows.Forms]System.Windows.Forms.RadioButton button, bool set)
0x76680  ldarg.0
0x76681  ldarg.1
0x76682  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_DisplayType()
0x76687  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::SwitchSchedule(string selected)
0x7668c  ret
```
