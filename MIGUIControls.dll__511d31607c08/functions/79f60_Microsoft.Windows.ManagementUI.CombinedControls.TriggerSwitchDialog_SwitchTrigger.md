# Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::SwitchTrigger

- ea: `0x79f60`
- end: `0x7a43b`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::SwitchTrigger`
- size: `1243`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x79a30`
- `0x7a860`

## callees

- `0x12ed0`
- `0x14500`
- `0x14550`
- `0x145b0`
- `0x60920`
- `0x74dd0`
- `0x74e10`
- `0x74f00`
- `0x74f10`
- `0x760e0`
- `0x760f0`
- `0x76220`
- `0x76230`
- `0x78cd0`
- `0x78cf0`
- `0x78d00`
- `0x78d20`
- `0x79d30`
- `0x79f60`
- `0x7ad80`
- `0x7ada0`
- `0x7adb0`
- `0x7afd0`
- `0x7c480`
- `0x7c500`
- `0x7c510`
- `0x7c530`
- `0x7c540`
- `0x7c560`
- `0x7c570`
- `0x7c590`
- `0x7c5a0`
- `0x7c5c0`
- `0x7c5d0`

## string_xrefs

- `0x79fb2`: `ComboEntryWeekly`
- `0x7a364`: `ComboEntryWeekly`
- `0x79f9f`: `ComboEntryMonthly`
- `0x7a351`: `ComboEntryMonthly`
- `0x79f8c`: `ComboEntryDaily`
- `0x7a33e`: `ComboEntryDaily`
- `0x7a0b0`: `ComboEntryOnEvent`
- `0x79f79`: `ComboEntryOneTime`
- `0x7a32b`: `ComboEntryOneTime`
- `0x7a14a`: `ComboEntryOnIdle`
- `0x7a197`: `ComboEntryOnTSConnect`
- `0x7a1ed`: `ComboEntryOnTSDisconnect`
- `0x7a243`: `ComboEntryOnLock`
- `0x7a296`: `ComboEntryOnUnlock`
- `0x7a063`: `ComboEntryAtStartUp`
- `0x7a0fd`: `ComboEntryImmediate`
- `0x7a00d`: `ComboEntryAtLogOn`
- `0x79fc5`: `ComboEntryOnSchedule`
- `0x7a377`: `ComboEntryOnSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x79f60  ldc.i4.0
0x79f61  stloc.0
0x79f62  ldnull
0x79f63  stloc.1
0x79f64  ldarg.0
0x79f65  ldarg.0
0x79f66  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x79f6b  ldarg.2
0x79f6c  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::SavePreviousAdvancedSettings(string selectedTrigger, bool newTrigger)
0x79f71  ldarg.0
0x79f72  ldarg.1
0x79f73  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::stringCurrentTriggerType
0x79f78  ldarg.1
0x79f79  ldstr    aComboentryonet// "ComboEntryOneTime"
0x79f7e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79f83  ldc.i4.0
0x79f84  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79f89  brfalse.s loc_79FD7
0x79f8b  ldarg.1
0x79f8c  ldstr    aComboentrydail// "ComboEntryDaily"
0x79f91  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79f96  ldc.i4.0
0x79f97  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79f9c  brfalse.s loc_79FD7
0x79f9e  ldarg.1
0x79f9f  ldstr    aComboentrymont// "ComboEntryMonthly"
0x79fa4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79fa9  ldc.i4.0
0x79faa  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79faf  brfalse.s loc_79FD7
0x79fb1  ldarg.1
0x79fb2  ldstr    aComboentryweek// "ComboEntryWeekly"
0x79fb7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79fbc  ldc.i4.0
0x79fbd  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79fc2  brfalse.s loc_79FD7
0x79fc4  ldarg.1
0x79fc5  ldstr    aComboentryonsc// "ComboEntryOnSchedule"
0x79fca  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79fcf  ldc.i4.0
0x79fd0  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x79fd5  brtrue.s loc_7A00C
0x79fd7  ldarg.2
0x79fd8  brtrue.s loc_79FED
0x79fda  ldarg.0
0x79fdb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x79fe0  ldarg.0
0x79fe1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x79fe6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger value)
0x79feb  br.s     loc_79FFE
0x79fed  ldarg.0
0x79fee  ldarg.0
0x79fef  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x79ff4  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet::get_CurrentTrigger()
0x79ff9  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x79ffe  ldarg.0
0x79fff  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnScheduleTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlScheduleTriggerSet
0x7a004  stloc.1
0x7a005  ldc.i4.2
0x7a006  stloc.0
0x7a007  br       loc_7A2E6
0x7a00c  ldarg.1
0x7a00d  ldstr    aComboentryatlo// "ComboEntryAtLogOn"
0x7a012  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a017  ldc.i4.0
0x7a018  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a01d  brtrue.s loc_7A062
0x7a01f  ldarg.2
0x7a020  brfalse.s loc_7A033
0x7a022  ldarg.0
0x7a023  ldarg.0
0x7a024  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a029  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UILogonTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetLogonTriggerData()
0x7a02e  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a033  ldarg.0
0x7a034  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a039  ldarg.0
0x7a03a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a03f  castclass Microsoft.Windows.ManagementUI.CombinedControls.UILogonTrigger
0x7a044  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::SetLogonTriggerData(class Microsoft.Windows.ManagementUI.CombinedControls.UILogonTrigger value)
0x7a049  ldarg.0
0x7a04a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a04f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::InitializeControl()
0x7a054  ldarg.0
0x7a055  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a05a  stloc.1
0x7a05b  ldc.i4.1
0x7a05c  stloc.0
0x7a05d  br       loc_7A2E6
0x7a062  ldarg.1
0x7a063  ldstr    aComboentryatst// "ComboEntryAtStartUp"
0x7a068  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a06d  ldc.i4.0
0x7a06e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a073  brtrue.s loc_7A0AF
0x7a075  ldarg.2
0x7a076  brtrue.s loc_7A090
0x7a078  ldarg.0
0x7a079  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x7a07e  ldarg.0
0x7a07f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a084  castclass Microsoft.Windows.ManagementUI.CombinedControls.UIAtStartupTrigger
0x7a089  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::set_CurrentStartTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UIAtStartupTrigger value)
0x7a08e  br.s     loc_7A0A1
0x7a090  ldarg.0
0x7a091  ldarg.0
0x7a092  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x7a097  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIAtStartupTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::get_CurrentStartTrigger()
0x7a09c  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a0a1  ldarg.0
0x7a0a2  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x7a0a7  stloc.1
0x7a0a8  ldc.i4.1
0x7a0a9  stloc.0
0x7a0aa  br       loc_7A2E6
0x7a0af  ldarg.1
0x7a0b0  ldstr    aComboentryonev// "ComboEntryOnEvent"
0x7a0b5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a0ba  ldc.i4.0
0x7a0bb  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a0c0  brtrue.s loc_7A0FC
0x7a0c2  ldarg.2
0x7a0c3  brtrue.s loc_7A0DD
0x7a0c5  ldarg.0
0x7a0c6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x7a0cb  ldarg.0
0x7a0cc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a0d1  castclass Microsoft.Windows.ManagementUI.CombinedControls.UIEventTrigger
0x7a0d6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UIEventTrigger value)
0x7a0db  br.s     loc_7A0EE
0x7a0dd  ldarg.0
0x7a0de  ldarg.0
0x7a0df  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x7a0e4  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet::get_CurrentTrigger()
0x7a0e9  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a0ee  ldarg.0
0x7a0ef  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventTriggerSet Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlEventTrigger
0x7a0f4  stloc.1
0x7a0f5  ldc.i4.1
0x7a0f6  stloc.0
0x7a0f7  br       loc_7A2E6
0x7a0fc  ldarg.1
0x7a0fd  ldstr    aComboentryimme// "ComboEntryImmediate"
0x7a102  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a107  ldc.i4.0
0x7a108  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a10d  brtrue.s loc_7A149
0x7a10f  ldarg.2
0x7a110  brtrue.s loc_7A12A
0x7a112  ldarg.0
0x7a113  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x7a118  ldarg.0
0x7a119  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a11e  castclass Microsoft.Windows.ManagementUI.CombinedControls.UIImmediateTrigger
0x7a123  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::set_CurrentImmediateTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UIImmediateTrigger value)
0x7a128  br.s     loc_7A13B
0x7a12a  ldarg.0
0x7a12b  ldarg.0
0x7a12c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x7a131  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIImmediateTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger::get_CurrentImmediateTrigger()
0x7a136  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a13b  ldarg.0
0x7a13c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnNoFurtherActionTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlNoFurtherActionTrigger
0x7a141  stloc.1
0x7a142  ldc.i4.1
0x7a143  stloc.0
0x7a144  br       loc_7A2E6
0x7a149  ldarg.1
0x7a14a  ldstr    aComboentryonid// "ComboEntryOnIdle"
0x7a14f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a154  ldc.i4.0
0x7a155  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a15a  brtrue.s loc_7A196
0x7a15c  ldarg.2
0x7a15d  brtrue.s loc_7A177
0x7a15f  ldarg.0
0x7a160  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x7a165  ldarg.0
0x7a166  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a16b  castclass Microsoft.Windows.ManagementUI.CombinedControls.UIIdleTrigger
0x7a170  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger::set_CurrentTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UIIdleTrigger value)
0x7a175  br.s     loc_7A188
0x7a177  ldarg.0
0x7a178  ldarg.0
0x7a179  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x7a17e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger::get_CurrentTrigger()
0x7a183  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a188  ldarg.0
0x7a189  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlOnIdleTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlOnIdleTrigger
0x7a18e  stloc.1
0x7a18f  ldc.i4.0
0x7a190  stloc.0
0x7a191  br       loc_7A2E6
0x7a196  ldarg.1
0x7a197  ldstr    aComboentryonts// "ComboEntryOnTSConnect"
0x7a19c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a1a1  ldc.i4.0
0x7a1a2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a1a7  brtrue.s loc_7A1EC
0x7a1a9  ldarg.2
0x7a1aa  brfalse.s loc_7A1BD
0x7a1ac  ldarg.0
0x7a1ad  ldarg.0
0x7a1ae  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a1b3  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetTSConnectTriggerData()
0x7a1b8  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a1bd  ldarg.0
0x7a1be  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a1c3  ldarg.0
0x7a1c4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a1c9  castclass Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger
0x7a1ce  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::SetTSConnectTriggerData(class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger value)
0x7a1d3  ldarg.0
0x7a1d4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a1d9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::InitializeControl()
0x7a1de  ldarg.0
0x7a1df  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a1e4  stloc.1
0x7a1e5  ldc.i4.1
0x7a1e6  stloc.0
0x7a1e7  br       loc_7A2E6
0x7a1ec  ldarg.1
0x7a1ed  ldstr    aComboentryonts_0// "ComboEntryOnTSDisconnect"
0x7a1f2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a1f7  ldc.i4.0
0x7a1f8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a1fd  brtrue.s loc_7A242
0x7a1ff  ldarg.2
0x7a200  brfalse.s loc_7A213
0x7a202  ldarg.0
0x7a203  ldarg.0
0x7a204  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a209  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetCurrentDisconnectTriggerData()
0x7a20e  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a213  ldarg.0
0x7a214  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a219  ldarg.0
0x7a21a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a21f  castclass Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger
0x7a224  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::SetDisconnectTriggerData(class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger value)
0x7a229  ldarg.0
0x7a22a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a22f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::InitializeControl()
0x7a234  ldarg.0
0x7a235  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a23a  stloc.1
0x7a23b  ldc.i4.1
0x7a23c  stloc.0
0x7a23d  br       loc_7A2E6
0x7a242  ldarg.1
0x7a243  ldstr    aComboentryonlo// "ComboEntryOnLock"
0x7a248  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a24d  ldc.i4.0
0x7a24e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a253  brtrue.s loc_7A295
0x7a255  ldarg.2
0x7a256  brfalse.s loc_7A269
0x7a258  ldarg.0
0x7a259  ldarg.0
0x7a25a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a25f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetCurrentLockTriggerData()
0x7a264  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a269  ldarg.0
0x7a26a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a26f  ldarg.0
0x7a270  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a275  castclass Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger
0x7a27a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::SetCurrentLockTriggerData(class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger value)
0x7a27f  ldarg.0
0x7a280  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a285  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::InitializeControl()
0x7a28a  ldarg.0
0x7a28b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a290  stloc.1
0x7a291  ldc.i4.1
0x7a292  stloc.0
0x7a293  br.s     loc_7A2E6
0x7a295  ldarg.1
0x7a296  ldstr    aComboentryonun// "ComboEntryOnUnlock"
0x7a29b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7a2a0  ldc.i4.0
0x7a2a1  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7a2a6  brtrue.s loc_7A2E6
0x7a2a8  ldarg.2
0x7a2a9  brfalse.s loc_7A2BC
0x7a2ab  ldarg.0
0x7a2ac  ldarg.0
0x7a2ad  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a2b2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::GetCurrentUnlockTriggerData()
0x7a2b7  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a2bc  ldarg.0
0x7a2bd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a2c2  ldarg.0
0x7a2c3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::uiTriggerCurrentTrigger
0x7a2c8  castclass Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger
0x7a2cd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::SetCurrentUnlockTriggerData(class Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger value)
0x7a2d2  ldarg.0
0x7a2d3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlUserTrigger
0x7a2d8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlUserTrigger::InitializeControl()
0x7a2dd  ldarg.0
  ... truncated ...
```
