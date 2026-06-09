# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::SwitchSchedule

- ea: `0x767b0`
- end: `0x768b6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::SwitchSchedule`
- size: `262`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x76550`
- `0x768c0`
- `0x768e0`
- `0x76900`
- `0x76920`

## callees

- `0x12ed0`
- `0x14500`
- `0x14550`
- `0x145b0`
- `0x74dd0`
- `0x76790`
- `0x767b0`

## string_xrefs

- `0x76800`: `ComboEntryWeekly`
- `0x76823`: `ComboEntryMonthly`
- `0x767dd`: `ComboEntryDaily`
- `0x767ba`: `ComboEntryOneTime`

## pseudocode

```c

```

## disassembly

```asm
0x767b0  ldnull
0x767b1  stloc.0
0x767b2  ldarg.0
0x767b3  ldarg.1
0x767b4  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::stringCurrentSelection
0x767b9  ldarg.1
0x767ba  ldstr    aComboentryonet// "ComboEntryOneTime"
0x767bf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x767c4  ldc.i4.0
0x767c5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x767ca  brtrue.s loc_767DC
0x767cc  ldarg.0
0x767cd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleOneTime Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlOneTime
0x767d2  stloc.0
0x767d3  ldloc.0
0x767d4  ldc.i4.0
0x767d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x767da  br.s     loc_76843
0x767dc  ldarg.1
0x767dd  ldstr    aComboentrydail// "ComboEntryDaily"
0x767e2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x767e7  ldc.i4.0
0x767e8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x767ed  brtrue.s loc_767FF
0x767ef  ldarg.0
0x767f0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleDaily Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlDaily
0x767f5  stloc.0
0x767f6  ldloc.0
0x767f7  ldc.i4.1
0x767f8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x767fd  br.s     loc_76843
0x767ff  ldarg.1
0x76800  ldstr    aComboentryweek// "ComboEntryWeekly"
0x76805  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7680a  ldc.i4.0
0x7680b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x76810  brtrue.s loc_76822
0x76812  ldarg.0
0x76813  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleWeekly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlWeekly
0x76818  stloc.0
0x76819  ldloc.0
0x7681a  ldc.i4.1
0x7681b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x76820  br.s     loc_76843
0x76822  ldarg.1
0x76823  ldstr    aComboentrymont// "ComboEntryMonthly"
0x76828  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7682d  ldc.i4.0
0x7682e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x76833  brtrue.s loc_76843
0x76835  ldarg.0
0x76836  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleMonthly Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::controlMonthly
0x7683b  stloc.0
0x7683c  ldloc.0
0x7683d  ldc.i4.1
0x7683e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x76843  ldloc.0
0x76844  brfalse.s loc_768B5
0x76846  ldloc.0
0x76847  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataHandler Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_RequiredData()
0x7684c  ldarg.0
0x7684d  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::ParentControlDataHandler(bool requiredDataExists)
0x76853  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler::.ctor(object object, native int method)
0x76858  ldloc.0
0x76859  dup
0x7685a  ldvirtftn instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::RequiredDataEntered()
0x76860  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataEntered::.ctor(object object, native int method)
0x76865  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataHandler::RegisterParentToNotify(class Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler inParentToInform, class Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataEntered inChild)
0x7686a  ldarg.0
0x7686b  ldc.i4.1
0x7686c  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::ShowStartDateAndTime(bool visible)
0x76871  ldarg.0
0x76872  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::currentBaseControl
0x76877  brfalse.s loc_76885
0x76879  ldarg.0
0x7687a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::currentBaseControl
0x7687f  ldc.i4.0
0x76880  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x76885  ldarg.0
0x76886  ldloc.0
0x76887  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::currentBaseControl
0x7688c  ldarg.0
0x7688d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::currentBaseControl
0x76892  ldc.i4.0
0x76893  ldc.i4.0
0x76894  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x76899  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7689e  ldarg.0
0x7689f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::currentBaseControl
0x768a4  ldc.i4.1
0x768a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x768aa  ldarg.0
0x768ab  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::currentBaseControl
0x768b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::BringToFront()
0x768b5  ret
```
