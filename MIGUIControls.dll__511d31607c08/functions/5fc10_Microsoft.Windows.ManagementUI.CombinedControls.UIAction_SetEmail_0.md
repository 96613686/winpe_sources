# Microsoft.Windows.ManagementUI.CombinedControls.UIAction::SetEmail_0

- ea: `0x5fc10`
- end: `0x5fcf0`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UIAction::SetEmail_0`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x5fcf0`

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
- `0x5f660`
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
- `0x5fc10`
- `0x602e0`

## string_xrefs

- `0x5fcae`: `ComboEntrySendEmailAction`

## pseudocode

```c

```

## disassembly

```asm
0x5fc10  ldarg.0
0x5fc11  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_Id()
0x5fc16  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5fc1b  brfalse.s loc_5FC28
0x5fc1d  ldarg.0
0x5fc1e  call     string Microsoft.Windows.ManagementUI.CombinedControls.IDGenerator::GenerateId()
0x5fc23  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_Id(string value)
0x5fc28  ldarg.0
0x5fc29  ldarg.1
0x5fc2a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_UserDefinedId(string value)
0x5fc2f  ldarg.0
0x5fc30  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc35  ldarg.2
0x5fc36  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_From(string value)
0x5fc3b  ldarg.0
0x5fc3c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc41  ldarg.3
0x5fc42  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_To(string value)
0x5fc47  ldarg.0
0x5fc48  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc4d  ldarg.s  4
0x5fc4f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_Subject(string value)
0x5fc54  ldarg.0
0x5fc55  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc5a  ldarg.s  5
0x5fc5c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_OriginalSubject(string value)
0x5fc61  ldarg.0
0x5fc62  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc67  ldarg.s  6
0x5fc69  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_Body(string value)
0x5fc6e  ldarg.0
0x5fc6f  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc74  ldarg.s  7
0x5fc76  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_OriginalBody(string value)
0x5fc7b  ldarg.0
0x5fc7c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc81  ldarg.s  8
0x5fc83  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_AttachmentArray(string[] value)
0x5fc88  ldarg.0
0x5fc89  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc8e  ldarg.s  9
0x5fc90  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_Server(string value)
0x5fc95  ldarg.0
0x5fc96  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fc9b  ldc.i4.0
0x5fc9c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_IsSubjectChanged(bool value)
0x5fca1  ldarg.0
0x5fca2  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_EmailActionData()
0x5fca7  ldc.i4.0
0x5fca8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIEmailActionData::set_IsBodyChanged(bool value)
0x5fcad  ldarg.0
0x5fcae  ldstr    aComboentrysend// "ComboEntrySendEmailAction"
0x5fcb3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5fcb8  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayType(string value)
0x5fcbd  ldarg.0
0x5fcbe  ldc.i4.6
0x5fcbf  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_ActionType(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType value)
0x5fcc4  ldarg.0
0x5fcc5  ldarg.3
0x5fcc6  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayPath(string value)
0x5fccb  ldarg.0
0x5fccc  ldarg.s  4
0x5fcce  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayArgs(string value)
0x5fcd3  ldarg.0
0x5fcd4  ldarg.0
0x5fcd5  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_DisplayPath()
0x5fcda  ldstr    asc_AAAB6// " "
0x5fcdf  ldarg.0
0x5fce0  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_DisplayArgs()
0x5fce5  call     string [mscorlib]System.String::Concat(string, string, string)
0x5fcea  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::set_DisplayDescription(string value)
0x5fcef  ret
```
