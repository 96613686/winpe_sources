# Microsoft.Windows.ManagementUI.CombinedControls.UIAction::SetEmail

- ea: `0x5fb30`
- end: `0x5fc10`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UIAction::SetEmail`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x6af70`

## callees

- `0x12ed0`
- `0x5f4c0`
- `0x5f4e0`
- `0x5f500`
- `0x5f520`
- `0x5f550`
- `0x5f570`
- `0x5f590`
- `0x5f5c0`
- `0x5f610`
- `0x5f680`
- `0x5f850`
- `0x5f860`
- `0x5f870`
- `0x5f890`
- `0x5f8c0`
- `0x5f8f0`
- `0x5f910`
- `0x5f920`
- `0x5f930`
- `0x5f940`
- `0x5f950`
- `0x5fb30`
- `0x602e0`

## string_xrefs

- `0x5fbce`: `ComboEntrySendEmailAction`

## pseudocode

```c

```

## disassembly

```asm
0x5fb30  ldarg.0
0x5fb31  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_Id()
0x5fb36  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5fb3b  brfalse.s loc_5FB48
0x5fb3d  ldarg.0
0x5fb3e  call     string Microsoft.Windows.ManagementUI.CombinedControls.IDGenerator::GenerateId()
0x5fb43  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_Id(string value)
0x5fb48  ldarg.0
0x5fb49  ldarg.1
0x5fb4a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_UserDefinedId(string value)
0x5fb4f  ldarg.0
0x5fb50  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fb55  ldarg.2
0x5fb56  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_From(string value)
0x5fb5b  ldarg.0
0x5fb5c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fb61  ldarg.3
0x5fb62  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_To(string value)
0x5fb67  ldarg.0
0x5fb68  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fb6d  ldarg.s  4
0x5fb6f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_Subject(string value)
0x5fb74  ldarg.0
0x5fb75  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fb7a  ldarg.s  5
0x5fb7c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_OriginalSubject(string value)
0x5fb81  ldarg.0
0x5fb82  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fb87  ldarg.s  6
0x5fb89  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_Body(string value)
0x5fb8e  ldarg.0
0x5fb8f  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fb94  ldarg.s  7
0x5fb96  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_OriginalBody(string value)
0x5fb9b  ldarg.0
0x5fb9c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fba1  ldarg.s  8
0x5fba3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_Attachment(string value)
0x5fba8  ldarg.0
0x5fba9  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fbae  ldarg.s  9
0x5fbb0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_Server(string value)
0x5fbb5  ldarg.0
0x5fbb6  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fbbb  ldc.i4.0
0x5fbbc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_IsSubjectChanged(bool value)
0x5fbc1  ldarg.0
0x5fbc2  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fbc7  ldc.i4.0
0x5fbc8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_IsBodyChanged(bool value)
0x5fbcd  ldarg.0
0x5fbce  ldstr    aComboentrysend// "ComboEntrySendEmailAction"
0x5fbd3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5fbd8  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayType(string value)
0x5fbdd  ldarg.0
0x5fbde  ldc.i4.6
0x5fbdf  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_ActionType(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType value)
0x5fbe4  ldarg.0
0x5fbe5  ldarg.3
0x5fbe6  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayPath(string value)
0x5fbeb  ldarg.0
0x5fbec  ldarg.s  4
0x5fbee  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayArgs(string value)
0x5fbf3  ldarg.0
0x5fbf4  ldarg.0
0x5fbf5  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_DisplayPath()
0x5fbfa  ldstr    asc_AAAB6// " "
0x5fbff  ldarg.0
0x5fc00  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_DisplayArgs()
0x5fc05  call     string [mscorlib]System.String::Concat(string, string, string)
0x5fc0a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayDescription(string value)
0x5fc0f  ret
```
