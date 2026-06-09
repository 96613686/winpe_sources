# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::SetControlValues

- ea: `0x72e10`
- end: `0x72ffc`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::SetControlValues`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x72e00`

## callees

- `0x12ed0`
- `0x13670`
- `0x13790`
- `0x5d740`
- `0x5ebd0`
- `0x5ed20`
- `0x5ed70`
- `0x5f130`
- `0x63b10`
- `0x63b80`
- `0x63e70`
- `0x645c0`
- `0x64630`
- `0x64680`
- `0x67010`
- `0x728a0`
- `0x72a00`
- `0x72a10`
- `0x72e10`
- `0x73090`

## string_xrefs

- `0x72e2f`: `GeneralTaskInfoChangeUser`

## pseudocode

```c

```

## disassembly

```asm
0x72e10  ldarg.0
0x72e11  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72e16  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_Parent()
0x72e1b  isinst   Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder
0x72e20  stloc.1
0x72e21  ldarg.0
0x72e22  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagUserIsAnAdmin
0x72e27  brtrue.s loc_72E3E
0x72e29  ldarg.0
0x72e2a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::buttonSetUserOrGroup
0x72e2f  ldstr    aGeneraltaskinf// "GeneralTaskInfoChangeUser"
0x72e34  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x72e39  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x72e3e  ldarg.0
0x72e3f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelAuthorText
0x72e44  ldarg.0
0x72e45  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72e4a  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x72e4f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Author()
0x72e54  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl, string val)
0x72e59  ldarg.0
0x72e5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxLocation
0x72e5f  ldloc.1
0x72e60  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Path()
0x72e65  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl, string val)
0x72e6a  ldarg.0
0x72e6b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72e70  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72e75  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::SetDefaultUserIfNeeded()
0x72e7a  ldarg.0
0x72e7b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72e80  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72e85  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserLogonType()
0x72e8a  ldc.i4.5
0x72e8b  bne.un.s loc_72EA4
0x72e8d  ldarg.0
0x72e8e  ldc.i4.0
0x72e8f  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagRunOnlyWhenUserIsLoggedOn
0x72e94  ldarg.0
0x72e95  ldc.i4.1
0x72e96  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsServiceAccount
0x72e9b  ldarg.0
0x72e9c  ldc.i4.0
0x72e9d  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsGroup
0x72ea2  br.s     loc_72F0D
0x72ea4  ldarg.0
0x72ea5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72eaa  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72eaf  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserLogonType()
0x72eb4  ldc.i4.4
0x72eb5  bne.un.s loc_72ECE
0x72eb7  ldarg.0
0x72eb8  ldc.i4.1
0x72eb9  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagRunOnlyWhenUserIsLoggedOn
0x72ebe  ldarg.0
0x72ebf  ldc.i4.0
0x72ec0  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsServiceAccount
0x72ec5  ldarg.0
0x72ec6  ldc.i4.1
0x72ec7  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsGroup
0x72ecc  br.s     loc_72F0D
0x72ece  ldarg.0
0x72ecf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72ed4  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72ed9  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserLogonType()
0x72ede  ldc.i4.3
0x72edf  bne.un.s loc_72EF8
0x72ee1  ldarg.0
0x72ee2  ldc.i4.1
0x72ee3  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagRunOnlyWhenUserIsLoggedOn
0x72ee8  ldarg.0
0x72ee9  ldc.i4.0
0x72eea  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsServiceAccount
0x72eef  ldarg.0
0x72ef0  ldc.i4.0
0x72ef1  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsGroup
0x72ef6  br.s     loc_72F0D
0x72ef8  ldarg.0
0x72ef9  ldc.i4.0
0x72efa  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagRunOnlyWhenUserIsLoggedOn
0x72eff  ldarg.0
0x72f00  ldc.i4.0
0x72f01  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsServiceAccount
0x72f06  ldarg.0
0x72f07  ldc.i4.0
0x72f08  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsGroup
0x72f0d  ldarg.0
0x72f0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName
0x72f13  ldarg.0
0x72f14  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72f19  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x72f1e  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl, string val)
0x72f23  ldarg.0
0x72f24  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxDescription
0x72f29  ldarg.0
0x72f2a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72f2f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x72f34  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Description()
0x72f39  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl, string val)
0x72f3e  ldarg.0
0x72f3f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72f44  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x72f49  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Hidden()
0x72f4e  stloc.0
0x72f4f  ldarg.0
0x72f50  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxHidden
0x72f55  ldloc.0
0x72f56  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheckBox(class [System.Windows.Forms]System.Windows.Forms.CheckBox button, bool set)
0x72f5b  ldarg.0
0x72f5c  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::ExecutorDataToControls()
0x72f61  ldarg.0
0x72f62  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsGroup
0x72f67  brtrue.s loc_72F8D
0x72f69  ldarg.0
0x72f6a  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsServiceAccount
0x72f6f  brtrue.s loc_72F8D
0x72f71  ldarg.0
0x72f72  ldarg.0
0x72f73  ldarg.0
0x72f74  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72f79  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72f7e  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserName()
0x72f83  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::UserIsExecutor(string executor)
0x72f88  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagExecutorIsCurrentUser
0x72f8d  ldarg.0
0x72f8e  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagRunOnlyWhenUserIsLoggedOn
0x72f93  brfalse.s loc_72F9D
0x72f95  ldarg.0
0x72f96  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::CheckUpdateLoggedOnUser()
0x72f9b  br.s     loc_72FD0
0x72f9d  ldarg.0
0x72f9e  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::CheckUserLoggedOnOrNot()
0x72fa3  ldarg.0
0x72fa4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72fa9  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72fae  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserLogonType()
0x72fb3  ldc.i4.2
0x72fb4  bne.un.s loc_72FC4
0x72fb6  ldarg.0
0x72fb7  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxS4U
0x72fbc  ldc.i4.1
0x72fbd  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheckBox(class [System.Windows.Forms]System.Windows.Forms.CheckBox button, bool set)
0x72fc2  br.s     loc_72FD0
0x72fc4  ldarg.0
0x72fc5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxS4U
0x72fca  ldc.i4.0
0x72fcb  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheckBox(class [System.Windows.Forms]System.Windows.Forms.CheckBox button, bool set)
0x72fd0  ldarg.0
0x72fd1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72fd6  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x72fdb  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskRunlevelType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_RunLevel()
0x72fe0  brtrue.s loc_72FEF
0x72fe2  ldarg.0
0x72fe3  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxRunElevated
0x72fe8  ldc.i4.0
0x72fe9  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheckBox(class [System.Windows.Forms]System.Windows.Forms.CheckBox button, bool set)
0x72fee  ret
0x72fef  ldarg.0
0x72ff0  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxRunElevated
0x72ff5  ldc.i4.1
0x72ff6  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetCheckBox(class [System.Windows.Forms]System.Windows.Forms.CheckBox button, bool set)
0x72ffb  ret
```
