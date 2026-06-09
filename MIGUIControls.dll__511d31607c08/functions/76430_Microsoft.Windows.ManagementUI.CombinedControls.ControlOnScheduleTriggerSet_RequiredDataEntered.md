# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::RequiredDataEntered

- ea: `0x76430`
- end: `0x764ca`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::RequiredDataEntered`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x12ed0`
- `0x74e30`
- `0x76430`

## string_xrefs

- `0x76484`: `ComboEntryWeekly`
- `0x764aa`: `ComboEntryMonthly`
- `0x7645e`: `ComboEntryDaily`
- `0x76438`: `ComboEntryOneTime`

## pseudocode

```c

```

## disassembly

```asm
0x76430  ldc.i4.0
0x76431  stloc.0
0x76432  ldarg.0
0x76433  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x76438  ldstr    aComboentryonet// "ComboEntryOneTime"
0x7643d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x76442  ldc.i4.0
0x76443  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x76448  brtrue.s loc_76458
0x7644a  ldarg.0
0x7644b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlOneTime
0x76450  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::RequiredDataEntered()
0x76455  stloc.0
0x76456  br.s     loc_764C8
0x76458  ldarg.0
0x76459  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x7645e  ldstr    aComboentrydail// "ComboEntryDaily"
0x76463  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x76468  ldc.i4.0
0x76469  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7646e  brtrue.s loc_7647E
0x76470  ldarg.0
0x76471  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlDaily
0x76476  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::RequiredDataEntered()
0x7647b  stloc.0
0x7647c  br.s     loc_764C8
0x7647e  ldarg.0
0x7647f  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x76484  ldstr    aComboentryweek// "ComboEntryWeekly"
0x76489  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7648e  ldc.i4.0
0x7648f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x76494  brtrue.s loc_764A4
0x76496  ldarg.0
0x76497  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleWeekly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlWeekly
0x7649c  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::RequiredDataEntered()
0x764a1  stloc.0
0x764a2  br.s     loc_764C8
0x764a4  ldarg.0
0x764a5  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x764aa  ldstr    aComboentrymont// "ComboEntryMonthly"
0x764af  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x764b4  ldc.i4.0
0x764b5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x764ba  brtrue.s loc_764C8
0x764bc  ldarg.0
0x764bd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlMonthly
0x764c2  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::RequiredDataEntered()
0x764c7  stloc.0
0x764c8  ldloc.0
0x764c9  ret
```
