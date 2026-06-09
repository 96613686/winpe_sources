# Microsoft.Windows.ManagementUI.CombinedControls.UITask::EnableTask

- ea: `0x65510`
- end: `0x655d1`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::EnableTask`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x80df0`

## callees

- `0x12ed0`
- `0x133f0`
- `0x5d760`
- `0x62f20`
- `0x62f30`
- `0x645c0`
- `0x646c0`
- `0x65510`
- `0x67e80`
- `0x83b70`

## string_xrefs

- `0x65553`: `MessageTaskDoesNotExist`
- `0x65596`: `MessageTaskEnableException`
- `0x655a7`: `MessageTaskDisableException`

## pseudocode

```c

```

## disassembly

```asm
0x65510  ldc.i4.0
0x65511  stloc.0
0x65512  ldarg.0
0x65513  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_AdvancedSettings()
0x65518  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::get_Enabled()
0x6551d  pop
0x6551e  ldarg.0
0x6551f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x65524  brfalse.s loc_65540
0x65526  ldarg.0
0x65527  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x6552c  ldarg.1
0x6552d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask::set_Enabled(bool value)
0x65532  ldarg.0
0x65533  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_AdvancedSettings()
0x65538  ldarg.1
0x65539  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::set_Enabled(bool value)
0x6553e  ldc.i4.1
0x6553f  stloc.0
0x65540  leave    loc_655CF
0x65545  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6554a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x6554f  leave.s  loc_655CF
0x65551  pop
0x65552  ldnull
0x65553  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x65558  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6555d  ldc.i4.2
0x6555e  newarr   [mscorlib]System.Object
0x65563  dup
0x65564  ldc.i4.0
0x65565  ldarg.0
0x65566  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x6556b  stelem.ref
0x6556c  dup
0x6556d  ldc.i4.1
0x6556e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x65573  stelem.ref
0x65574  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x65579  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x6557e  leave.s  loc_655CF
0x65580  pop
0x65581  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x65586  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6558b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x65590  leave.s  loc_655CF
0x65592  pop
0x65593  ldarg.1
0x65594  brfalse.s loc_655A7
0x65596  ldstr    aMessagetaskena// "MessageTaskEnableException"
0x6559b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x655a0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x655a5  br.s     loc_655B6
0x655a7  ldstr    aMessagetaskdis// "MessageTaskDisableException"
0x655ac  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x655b1  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x655b6  ldc.i4.1
0x655b7  stloc.0
0x655b8  leave.s  loc_655CF
0x655ba  stloc.1
0x655bb  ldarg.0
0x655bc  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x655c1  ldloc.1
0x655c2  ldarg.0
0x655c3  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x655c8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x655cd  leave.s  loc_655CF
0x655cf  ldloc.0
0x655d0  ret
```
