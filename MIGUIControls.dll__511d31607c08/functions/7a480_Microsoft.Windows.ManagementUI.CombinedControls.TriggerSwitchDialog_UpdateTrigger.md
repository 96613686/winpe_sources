# Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::UpdateTrigger

- ea: `0x7a480`
- end: `0x7a79f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::UpdateTrigger`
- size: `799`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x79a10`
- `0x7a440`

## callees

- `0x12ed0`
- `0x605b0`
- `0x60920`
- `0x62490`
- `0x74f00`
- `0x760e0`
- `0x76220`
- `0x76240`
- `0x78cd0`
- `0x78d00`
- `0x7a480`
- `0x7a7d0`
- `0x7a820`
- `0x7ad50`
- `0x7b390`
- `0x7c4f0`
- `0x7c500`
- `0x7c520`
- `0x7c530`
- `0x7c550`
- `0x7c560`
- `0x7c580`
- `0x7c590`
- `0x7c5b0`
- `0x7c5c0`

## string_xrefs

- `0x7a4e4`: `ComboEntryWeekly`
- `0x7a5a8`: `ComboEntryWeekly`
- `0x7a4cc`: `ComboEntryMonthly`
- `0x7a590`: `ComboEntryMonthly`
- `0x7a4b4`: `ComboEntryDaily`
- `0x7a578`: `ComboEntryDaily`
- `0x7a6e3`: `ComboEntryOnEvent`
- `0x7a49c`: `ComboEntryOneTime`
- `0x7a560`: `ComboEntryOneTime`
- `0x7a5f2`: `ComboEntryOnIdle`
- `0x7a650`: `ComboEntryOnTSConnect`
- `0x7a685`: `ComboEntryOnTSDisconnect`
- `0x7a732`: `ComboEntryOnLock`
- `0x7a764`: `ComboEntryOnUnlock`
- `0x7a6ba`: `ComboEntryAtStartUp`
- `0x7a70c`: `ComboEntryImmediate`
- `0x7a61b`: `ComboEntryAtLogOn`
- `0x7a4fc`: `ComboEntryOnSchedule`
- `0x7a5c0`: `ComboEntryOnSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x7a480  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIIdleTrigger::.ctor()
0x7a485  stloc.0
0x7a486  ldc.i4.0
0x7a487  stloc.1
0x7a488  ldc.i4.0
0x7a489  stloc.2
0x7a48a  ldarg.0
0x7a48b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x7a490  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::TimeSpanFormatsAreValid()
0x7a495  stloc.2
0x7a496  ldarg.0
0x7a497  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a49c  ldstr    aComboentryonet// "ComboEntryOneTime"
0x7a4a1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a4a6  ldc.i4.0
0x7a4a7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a4ac  brfalse.s loc_7A50E
0x7a4ae  ldarg.0
0x7a4af  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a4b4  ldstr    aComboentrydail// "ComboEntryDaily"
0x7a4b9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a4be  ldc.i4.0
0x7a4bf  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a4c4  brfalse.s loc_7A50E
0x7a4c6  ldarg.0
0x7a4c7  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a4cc  ldstr    aComboentrymont// "ComboEntryMonthly"
0x7a4d1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a4d6  ldc.i4.0
0x7a4d7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a4dc  brfalse.s loc_7A50E
0x7a4de  ldarg.0
0x7a4df  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a4e4  ldstr    aComboentryweek// "ComboEntryWeekly"
0x7a4e9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a4ee  ldc.i4.0
0x7a4ef  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a4f4  brfalse.s loc_7A50E
0x7a4f6  ldarg.0
0x7a4f7  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a4fc  ldstr    aComboentryonsc// "ComboEntryOnSchedule"
0x7a501  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a506  ldc.i4.0
0x7a507  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a50c  brtrue.s loc_7A54B
0x7a50e  ldc.i4.1
0x7a50f  stloc.1
0x7a510  ldarg.0
0x7a511  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x7a516  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::get_CurrentTrigger()
0x7a51b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_AdvancedSettings()
0x7a520  ldarg.0
0x7a521  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x7a526  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::get_IsStartTimeUtc()
0x7a52b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings::set_IsActiveOnTimeUtc(bool value)
0x7a530  ldarg.0
0x7a531  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x7a536  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::get_TriggerSettings()
0x7a53b  ldarg.0
0x7a53c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x7a541  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::get_IsStartTimeUtc()
0x7a546  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAdvancedTriggerSettings::set_IsActiveOnTimeUtc(bool value)
0x7a54b  ldarg.0
0x7a54c  ldloca.s 0
0x7a54e  ldloc.1
0x7a54f  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::UpdateSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger& triggerToUpdate, bool flagOverrideActiveOnDate)
0x7a554  ldloc.2
0x7a555  brfalse  loc_7A797
0x7a55a  ldarg.0
0x7a55b  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a560  ldstr    aComboentryonet// "ComboEntryOneTime"
0x7a565  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a56a  ldc.i4.0
0x7a56b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a570  brfalse.s loc_7A5D2
0x7a572  ldarg.0
0x7a573  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a578  ldstr    aComboentrydail// "ComboEntryDaily"
0x7a57d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a582  ldc.i4.0
0x7a583  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a588  brfalse.s loc_7A5D2
0x7a58a  ldarg.0
0x7a58b  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a590  ldstr    aComboentrymont// "ComboEntryMonthly"
0x7a595  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a59a  ldc.i4.0
0x7a59b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a5a0  brfalse.s loc_7A5D2
0x7a5a2  ldarg.0
0x7a5a3  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a5a8  ldstr    aComboentryweek// "ComboEntryWeekly"
0x7a5ad  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a5b2  ldc.i4.0
0x7a5b3  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a5b8  brfalse.s loc_7A5D2
0x7a5ba  ldarg.0
0x7a5bb  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a5c0  ldstr    aComboentryonsc// "ComboEntryOnSchedule"
0x7a5c5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a5ca  ldc.i4.0
0x7a5cb  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a5d0  brtrue.s loc_7A5EC
0x7a5d2  ldarg.0
0x7a5d3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x7a5d8  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::get_CurrentTrigger()
0x7a5dd  stloc.0
0x7a5de  ldarg.0
0x7a5df  ldloca.s 0
0x7a5e1  ldloc.1
0x7a5e2  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::UpdateSettings(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger& triggerToUpdate, bool flagOverrideActiveOnDate)
0x7a5e7  br       loc_7A78E
0x7a5ec  ldarg.0
0x7a5ed  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a5f2  ldstr    aComboentryonid// "ComboEntryOnIdle"
0x7a5f7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a5fc  ldc.i4.0
0x7a5fd  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a602  brtrue.s loc_7A615
0x7a604  ldarg.0
0x7a605  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x7a60a  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger::get_CurrentTrigger()
0x7a60f  stloc.0
0x7a610  br       loc_7A78E
0x7a615  ldarg.0
0x7a616  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a61b  ldstr    aComboentryatlo// "ComboEntryAtLogOn"
0x7a620  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a625  ldc.i4.0
0x7a626  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a62b  brtrue.s loc_7A64A
0x7a62d  ldarg.0
0x7a62e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a633  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::UpdateLogonTriggerDataWithUserInput()
0x7a638  pop
0x7a639  ldarg.0
0x7a63a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a63f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UILogonTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetLogonTriggerData()
0x7a644  stloc.0
0x7a645  br       loc_7A78E
0x7a64a  ldarg.0
0x7a64b  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a650  ldstr    aComboentryonts// "ComboEntryOnTSConnect"
0x7a655  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a65a  ldc.i4.0
0x7a65b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a660  brtrue.s loc_7A67F
0x7a662  ldarg.0
0x7a663  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a668  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::UpdateTSConnectTriggerDataWithUserInput()
0x7a66d  pop
0x7a66e  ldarg.0
0x7a66f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a674  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetTSConnectTriggerData()
0x7a679  stloc.0
0x7a67a  br       loc_7A78E
0x7a67f  ldarg.0
0x7a680  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a685  ldstr    aComboentryonts_0// "ComboEntryOnTSDisconnect"
0x7a68a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a68f  ldc.i4.0
0x7a690  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a695  brtrue.s loc_7A6B4
0x7a697  ldarg.0
0x7a698  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a69d  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::UpdateCurrentDisconnectTriggerDataWithUserInput()
0x7a6a2  pop
0x7a6a3  ldarg.0
0x7a6a4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a6a9  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetCurrentDisconnectTriggerData()
0x7a6ae  stloc.0
0x7a6af  br       loc_7A78E
0x7a6b4  ldarg.0
0x7a6b5  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a6ba  ldstr    aComboentryatst// "ComboEntryAtStartUp"
0x7a6bf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a6c4  ldc.i4.0
0x7a6c5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a6ca  brtrue.s loc_7A6DD
0x7a6cc  ldarg.0
0x7a6cd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x7a6d2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAtStartupTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::get_CurrentStartTrigger()
0x7a6d7  stloc.0
0x7a6d8  br       loc_7A78E
0x7a6dd  ldarg.0
0x7a6de  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a6e3  ldstr    aComboentryonev// "ComboEntryOnEvent"
0x7a6e8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a6ed  ldc.i4.0
0x7a6ee  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a6f3  brtrue.s loc_7A706
0x7a6f5  ldarg.0
0x7a6f6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x7a6fb  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet::get_CurrentTrigger()
0x7a700  stloc.0
0x7a701  br       loc_7A78E
0x7a706  ldarg.0
0x7a707  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a70c  ldstr    aComboentryimme// "ComboEntryImmediate"
0x7a711  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a716  ldc.i4.0
0x7a717  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a71c  brtrue.s loc_7A72C
0x7a71e  ldarg.0
0x7a71f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x7a724  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIImmediateTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::get_CurrentImmediateTrigger()
0x7a729  stloc.0
0x7a72a  br.s     loc_7A78E
0x7a72c  ldarg.0
0x7a72d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a732  ldstr    aComboentryonlo// "ComboEntryOnLock"
0x7a737  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a73c  ldc.i4.0
0x7a73d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a742  brtrue.s loc_7A75E
0x7a744  ldarg.0
0x7a745  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a74a  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::UpdateCurrentLockTriggerDataWithUserInput()
0x7a74f  pop
0x7a750  ldarg.0
0x7a751  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a756  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetCurrentLockTriggerData()
0x7a75b  stloc.0
0x7a75c  br.s     loc_7A78E
0x7a75e  ldarg.0
0x7a75f  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x7a764  ldstr    aComboentryonun// "ComboEntryOnUnlock"
0x7a769  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a76e  ldc.i4.0
0x7a76f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a774  brtrue.s loc_7A78E
0x7a776  ldarg.0
0x7a777  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a77c  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::UpdateCurrentUnlockTriggerWithUserInput()
0x7a781  pop
0x7a782  ldarg.0
0x7a783  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a788  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetCurrentUnlockTriggerData()
0x7a78d  stloc.0
0x7a78e  ldarg.0
0x7a78f  ldloca.s 0
0x7a791  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::ValidateTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger& triggerToValidate)
0x7a796  stloc.2
0x7a797  ldloc.2
0x7a798  brfalse.s loc_7A79D
0x7a79a  ldarg.2
0x7a79b  ldloc.0
0x7a79c  stind.ref
0x7a79d  ldloc.2
0x7a79e  ret
```
