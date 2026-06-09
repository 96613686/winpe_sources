# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::InvokeObjectPicker

- ea: `0x72a70`
- end: `0x72c53`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::InvokeObjectPicker`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x722f0`
- `0x730b0`

## callees

- `0x12ed0`
- `0x13440`
- `0x5ebe0`
- `0x5ec70`
- `0x5ed70`
- `0x5ed80`
- `0x5edd0`
- `0x64680`
- `0x723a0`
- `0x72a70`
- `0x72cb0`
- `0x72e00`
- `0x73090`
- `0xa0490`
- `0xa04b0`
- `0xa0510`
- `0xa1150`

## string_xrefs

- `0x72c41`: `ApplicationTaskScheduler`
- `0x72b50`: `msDS-GroupManagedServiceAccount`

## pseudocode

```c

```

## disassembly

```asm
0x72a70  ldc.i4.2
0x72a71  stloc.1
0x72a72  ldarg.0
0x72a73  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagUserIsAnAdmin
0x72a78  brfalse.s loc_72A7F
0x72a7a  ldloc.1
0x72a7b  ldc.i4.s 0xC
0x72a7d  or
0x72a7e  stloc.1
0x72a7f  ldarg.0
0x72a80  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::buttonSetUserOrGroup
0x72a85  callvirt instance native int [System.Windows.Forms]System.Windows.Forms.Control::get_Handle()
0x72a8a  ldloc.1
0x72a8b  ldarg.1
0x72a8c  call     valuetype PickerObject[] ObjectPickerWrapper::ShowObjectPicker(native int parentHandle, valuetype ObjectPickerTypes showTypes, string targetComputerName)
0x72a91  stloc.0
0x72a92  ldloc.0
0x72a93  brfalse  loc_72C2F
0x72a98  ldloc.0
0x72a99  ldlen
0x72a9a  brfalse  loc_72C2F
0x72a9f  ldarg.0
0x72aa0  ldc.i4.4
0x72aa1  ldloc.0
0x72aa2  ldc.i4.0
0x72aa3  ldelema  PickerObject
0x72aa8  call     instance valuetype ObjectPickerTypes PickerObject::get_ObjectType()
0x72aad  ceq
0x72aaf  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsGroup
0x72ab4  ldarg.0
0x72ab5  ldloc.0
0x72ab6  ldc.i4.0
0x72ab7  ldelema  PickerObject
0x72abc  call     instance string PickerObject::get_ObjectName()
0x72ac1  ldarg.1
0x72ac2  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::SetExecutorFlags(string executor, string computerName)
0x72ac7  ldarg.0
0x72ac8  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsServiceAccount
0x72acd  brfalse.s loc_72B0F
0x72acf  ldarg.0
0x72ad0  ldc.i4.0
0x72ad1  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsGroup
0x72ad6  ldarg.0
0x72ad7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72adc  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72ae1  ldloc.0
0x72ae2  ldc.i4.0
0x72ae3  ldelema  PickerObject
0x72ae8  call     instance string PickerObject::get_ObjectName()
0x72aed  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_UserName(string value)
0x72af2  ldarg.0
0x72af3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72af8  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72afd  ldc.i4.5
0x72afe  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_UserLogonType(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType value)
0x72b03  ldarg.0
0x72b04  ldc.i4.0
0x72b05  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsCurrentUser
0x72b0a  br       loc_72C23
0x72b0f  ldarg.0
0x72b10  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsGroup
0x72b15  brfalse.s loc_72B50
0x72b17  ldarg.0
0x72b18  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72b1d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72b22  ldloc.0
0x72b23  ldc.i4.0
0x72b24  ldelema  PickerObject
0x72b29  call     instance string PickerObject::get_ObjectName()
0x72b2e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_UserGroup(string value)
0x72b33  ldarg.0
0x72b34  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72b39  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72b3e  ldc.i4.4
0x72b3f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_UserLogonType(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType value)
0x72b44  ldarg.0
0x72b45  ldc.i4.0
0x72b46  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsCurrentUser
0x72b4b  br       loc_72C23
0x72b50  ldstr    aMsdsGroupmanag// "msDS-GroupManagedServiceAccount"
0x72b55  ldloc.0
0x72b56  ldc.i4.0
0x72b57  ldelema  PickerObject
0x72b5c  call     instance string PickerObject::get_Class()
0x72b61  ldc.i4.3
0x72b62  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x72b67  ldarg.0
0x72b68  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72b6d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72b72  ldloc.0
0x72b73  ldc.i4.0
0x72b74  ldelema  PickerObject
0x72b79  call     instance string PickerObject::get_ObjectName()
0x72b7e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_UserName(string value)
0x72b83  brfalse.s loc_72BB0
0x72b85  ldarg.0
0x72b86  ldc.i4.0
0x72b87  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsCurrentUser
0x72b8c  ldarg.0
0x72b8d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72b92  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72b97  ldc.i4.1
0x72b98  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_UserLogonType(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType value)
0x72b9d  ldarg.0
0x72b9e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72ba3  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72ba8  ldc.i4.1
0x72ba9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_IsGroupManagedServiceAccount(bool value)
0x72bae  br.s     loc_72C23
0x72bb0  ldarg.0
0x72bb1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72bb6  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72bbb  ldc.i4.0
0x72bbc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_IsGroupManagedServiceAccount(bool value)
0x72bc1  ldarg.0
0x72bc2  ldarg.0
0x72bc3  ldloc.0
0x72bc4  ldc.i4.0
0x72bc5  ldelema  PickerObject
0x72bca  call     instance string PickerObject::get_ObjectName()
0x72bcf  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::UserIsExecutor(string executor)
0x72bd4  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsCurrentUser
0x72bd9  ldarg.0
0x72bda  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72bdf  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72be4  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserLogonType()
0x72be9  ldc.i4.4
0x72bea  bne.un.s loc_72BFF
0x72bec  ldarg.0
0x72bed  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72bf2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72bf7  ldc.i4.3
0x72bf8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_UserLogonType(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType value)
0x72bfd  br.s     loc_72C23
0x72bff  ldarg.0
0x72c00  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72c05  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72c0a  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserLogonType()
0x72c0f  ldc.i4.5
0x72c10  bne.un.s loc_72C23
0x72c12  ldarg.0
0x72c13  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72c18  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72c1d  ldc.i4.1
0x72c1e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::set_UserLogonType(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType value)
0x72c23  ldarg.0
0x72c24  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::DataToControls()
0x72c29  ldarg.0
0x72c2a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::ControlsToData()
0x72c2f  leave.s  loc_72C52
0x72c31  pop
0x72c32  leave.s  loc_72C52
0x72c34  stloc.2
0x72c35  ldarg.0
0x72c36  call     instance class [System.Windows.Forms]System.Windows.Forms.Form [System.Windows.Forms]System.Windows.Forms.ContainerControl::get_ParentForm()
0x72c3b  ldloc.2
0x72c3c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x72c41  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x72c46  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x72c4b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x72c50  leave.s  loc_72C52
0x72c52  ret
```
