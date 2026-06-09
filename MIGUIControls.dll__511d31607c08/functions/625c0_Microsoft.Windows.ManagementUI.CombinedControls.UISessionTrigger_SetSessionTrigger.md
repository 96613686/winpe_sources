# Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::SetSessionTrigger

- ea: `0x625c0`
- end: `0x627bb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::SetSessionTrigger`
- size: `507`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x627c0`
- `0x7c7e0`

## callees

- `0x12ed0`
- `0x608f0`
- `0x60910`
- `0x60ce0`
- `0x60e40`
- `0x62550`
- `0x62560`
- `0x62570`
- `0x62590`
- `0x625c0`

## string_xrefs

- `0x62639`: `ComboEntryOnTSConnect`
- `0x62671`: `ComboEntryOnTSConnect`
- `0x626a9`: `ComboEntryOnTSDisconnect`
- `0x626e1`: `ComboEntryOnTSDisconnect`
- `0x62713`: `ComboEntryOnLock`
- `0x62745`: `ComboEntryOnUnlock`

## pseudocode

```c

```

## disassembly

```asm
0x625c0  ldarg.0
0x625c1  ldc.i4.s 0xB
0x625c3  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::SetBaseTriggerProperties(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskTriggerType inType)
0x625c8  ldarg.0
0x625c9  ldarg.2
0x625ca  stfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskSessionStateChangeType Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::sessionState
0x625cf  ldarg.1
0x625d0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x625d5  brfalse.s loc_625E7
0x625d7  ldarg.0
0x625d8  ldc.i4.0
0x625d9  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::set_DisplaySpecificUser(bool value)
0x625de  ldarg.0
0x625df  ldc.i4.1
0x625e0  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::set_DisplayAnyUser(bool value)
0x625e5  br.s     loc_625F5
0x625e7  ldarg.0
0x625e8  ldc.i4.1
0x625e9  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::set_DisplaySpecificUser(bool value)
0x625ee  ldarg.0
0x625ef  ldc.i4.0
0x625f0  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::set_DisplayAnyUser(bool value)
0x625f5  ldarg.0
0x625f6  ldarg.1
0x625f7  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::set_User(string value)
0x625fc  ldsfld   string [mscorlib]System.String::Empty
0x62601  stloc.0
0x62602  ldc.i4.1
0x62603  stloc.1
0x62604  ldarg.0
0x62605  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskSessionStateChangeType Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::sessionState
0x6260a  stloc.2
0x6260b  ldloc.2
0x6260c  ldc.i4.1
0x6260d  sub
0x6260e  switch   loc_62670, loc_626E0, loc_62638, loc_626A8, loc_62776, loc_62776, loc_62712, loc_62744
0x62633  br       loc_62776
0x62638  ldarg.0
0x62639  ldstr    aComboentryonts// "ComboEntryOnTSConnect"
0x6263e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62643  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_DisplayType(string value)
0x62648  ldarg.0
0x62649  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::get_DisplayAnyUser()
0x6264e  brfalse.s loc_62660
0x62650  ldstr    aTriggerformatt_11// "TriggerFormattingSessionTriggerConnectA"...
0x62655  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6265a  stloc.0
0x6265b  br       loc_62778
0x62660  ldstr    aTriggerformatt_12// "TriggerFormattingSessionTriggerConnectM"...
0x62665  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6266a  stloc.0
0x6266b  br       loc_62778
0x62670  ldarg.0
0x62671  ldstr    aComboentryonts// "ComboEntryOnTSConnect"
0x62676  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6267b  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_DisplayType(string value)
0x62680  ldarg.0
0x62681  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::get_DisplayAnyUser()
0x62686  brfalse.s loc_62698
0x62688  ldstr    aTriggerformatt_13// "TriggerFormattingSessionTriggerConnectA"...
0x6268d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62692  stloc.0
0x62693  br       loc_62778
0x62698  ldstr    aTriggerformatt_14// "TriggerFormattingSessionTriggerConnectM"...
0x6269d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x626a2  stloc.0
0x626a3  br       loc_62778
0x626a8  ldarg.0
0x626a9  ldstr    aComboentryonts_0// "ComboEntryOnTSDisconnect"
0x626ae  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x626b3  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_DisplayType(string value)
0x626b8  ldarg.0
0x626b9  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::get_DisplayAnyUser()
0x626be  brfalse.s loc_626D0
0x626c0  ldstr    aTriggerformatt_15// "TriggerFormattingSessionTriggerDisconne"...
0x626c5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x626ca  stloc.0
0x626cb  br       loc_62778
0x626d0  ldstr    aTriggerformatt_16// "TriggerFormattingSessionTriggerDisconne"...
0x626d5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x626da  stloc.0
0x626db  br       loc_62778
0x626e0  ldarg.0
0x626e1  ldstr    aComboentryonts_0// "ComboEntryOnTSDisconnect"
0x626e6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x626eb  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_DisplayType(string value)
0x626f0  ldarg.0
0x626f1  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::get_DisplayAnyUser()
0x626f6  brfalse.s loc_62705
0x626f8  ldstr    aTriggerformatt_17// "TriggerFormattingSessionTriggerDisconne"...
0x626fd  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62702  stloc.0
0x62703  br.s     loc_62778
0x62705  ldstr    aTriggerformatt_18// "TriggerFormattingSessionTriggerDisconne"...
0x6270a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6270f  stloc.0
0x62710  br.s     loc_62778
0x62712  ldarg.0
0x62713  ldstr    aComboentryonlo// "ComboEntryOnLock"
0x62718  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6271d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_DisplayType(string value)
0x62722  ldarg.0
0x62723  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::get_DisplayAnyUser()
0x62728  brfalse.s loc_62737
0x6272a  ldstr    aTriggerformatt_19// "TriggerFormattingSessionTriggerLockAnyU"...
0x6272f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62734  stloc.0
0x62735  br.s     loc_62778
0x62737  ldstr    aTriggerformatt_20// "TriggerFormattingSessionTriggerLockMult"...
0x6273c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62741  stloc.0
0x62742  br.s     loc_62778
0x62744  ldarg.0
0x62745  ldstr    aComboentryonun// "ComboEntryOnUnlock"
0x6274a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6274f  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_DisplayType(string value)
0x62754  ldarg.0
0x62755  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::get_DisplayAnyUser()
0x6275a  brfalse.s loc_62769
0x6275c  ldstr    aTriggerformatt_21// "TriggerFormattingSessionTriggerUnlockAn"...
0x62761  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62766  stloc.0
0x62767  br.s     loc_62778
0x62769  ldstr    aTriggerformatt_22// "TriggerFormattingSessionTriggerUnlockMu"...
0x6276e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62773  stloc.0
0x62774  br.s     loc_62778
0x62776  ldc.i4.0
0x62777  stloc.1
0x62778  ldloc.1
0x62779  brfalse.s loc_627B4
0x6277b  ldarg.0
0x6277c  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UISessionTrigger::get_DisplayAnyUser()
0x62781  brtrue.s loc_627AD
0x62783  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x62788  ldtoken  [mscorlib]System.String
0x6278d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x62792  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x62797  castclass [mscorlib]System.IFormatProvider
0x6279c  ldloc.0
0x6279d  ldc.i4.1
0x6279e  newarr   [mscorlib]System.Object
0x627a3  dup
0x627a4  ldc.i4.0
0x627a5  ldarg.1
0x627a6  stelem.ref
0x627a7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x627ac  stloc.0
0x627ad  ldarg.0
0x627ae  ldloc.0
0x627af  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::set_DisplayDescription(string value)
0x627b4  ldarg.0
0x627b5  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::AppendAdvancedSettingsInfoForDisplay()
0x627ba  ret
```
