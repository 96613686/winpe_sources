# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::InitializeVersion

- ea: `0x73d10`
- end: `0x73ee7`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::InitializeVersion`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x73fb0`

## callees

- `0x12ed0`
- `0x137d0`
- `0x137e0`
- `0x13800`
- `0x63e50`
- `0x64630`
- `0x646f0`
- `0x64710`
- `0x67c70`
- `0x67d30`
- `0x73d10`

## string_xrefs

- `0x73d76`: `ComboEntryVersion3`
- `0x73e5d`: `ComboEntryVersion3`
- `0x73da8`: `ComboEntryVersion2`
- `0x73e84`: `ComboEntryVersion2`
- `0x73de4`: `ComboEntryVersion1`
- `0x73eac`: `ComboEntryVersion1`
- `0x73e12`: `ComboEntryVersionAt`
- `0x73ec1`: `ComboEntryVersionAt`

## pseudocode

```c

```

## disassembly

```asm
0x73d10  ldarg.0
0x73d11  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x73d16  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::ClearComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo)
0x73d1b  ldc.i4.0
0x73d1c  stloc.0
0x73d1d  ldc.i4.0
0x73d1e  stloc.1
0x73d1f  ldc.i4.0
0x73d20  stloc.2
0x73d21  ldc.i4.0
0x73d22  stloc.3
0x73d23  ldc.i4.0
0x73d24  stloc.s  4
0x73d26  ldc.i4.0
0x73d27  stloc.s  5
0x73d29  ldc.i4.0
0x73d2a  stloc.s  6
0x73d2c  ldc.i4   0x10004
0x73d31  ldarg.0
0x73d32  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73d37  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x73d3c  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x73d41  bgt.s    loc_73D59
0x73d43  ldarg.0
0x73d44  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x73d49  call     string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetBranding()
0x73d4e  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x73d53  ldloc.1
0x73d54  dup
0x73d55  ldc.i4.1
0x73d56  add
0x73d57  stloc.1
0x73d58  stloc.2
0x73d59  ldc.i4   0x10003
0x73d5e  ldarg.0
0x73d5f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73d64  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x73d69  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x73d6e  bgt.s    loc_73D8B
0x73d70  ldarg.0
0x73d71  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x73d76  ldstr    aComboentryvers// "ComboEntryVersion3"
0x73d7b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73d80  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x73d85  ldloc.1
0x73d86  dup
0x73d87  ldc.i4.1
0x73d88  add
0x73d89  stloc.1
0x73d8a  stloc.3
0x73d8b  ldc.i4   0x10002
0x73d90  ldarg.0
0x73d91  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73d96  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x73d9b  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x73da0  bgt.s    loc_73DBE
0x73da2  ldarg.0
0x73da3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x73da8  ldstr    aComboentryvers_0// "ComboEntryVersion2"
0x73dad  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73db2  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x73db7  ldloc.1
0x73db8  dup
0x73db9  ldc.i4.1
0x73dba  add
0x73dbb  stloc.1
0x73dbc  stloc.s  4
0x73dbe  ldc.i4.1
0x73dbf  ldarg.0
0x73dc0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73dc5  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x73dca  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x73dcf  beq.s    loc_73DDE
0x73dd1  ldarg.0
0x73dd2  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73dd7  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_IsNew()
0x73ddc  brfalse.s loc_73DFA
0x73dde  ldarg.0
0x73ddf  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x73de4  ldstr    aComboentryvers_1// "ComboEntryVersion1"
0x73de9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73dee  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x73df3  ldloc.1
0x73df4  dup
0x73df5  ldc.i4.1
0x73df6  add
0x73df7  stloc.1
0x73df8  stloc.s  5
0x73dfa  ldarg.0
0x73dfb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73e00  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x73e05  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x73e0a  brtrue.s loc_73E24
0x73e0c  ldarg.0
0x73e0d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x73e12  ldstr    aComboentryvers_2// "ComboEntryVersionAt"
0x73e17  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73e1c  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x73e21  ldloc.1
0x73e22  stloc.s  6
0x73e24  ldc.i4.4
0x73e25  ldarg.0
0x73e26  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73e2b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x73e30  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x73e35  bne.un.s loc_73E49
0x73e37  ldarg.0
0x73e38  call     string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetBranding()
0x73e3d  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::stringSelectedVersion
0x73e42  ldloc.2
0x73e43  stloc.0
0x73e44  br       loc_73ED3
0x73e49  ldc.i4.3
0x73e4a  ldarg.0
0x73e4b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73e50  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x73e55  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x73e5a  bne.un.s loc_73E70
0x73e5c  ldarg.0
0x73e5d  ldstr    aComboentryvers// "ComboEntryVersion3"
0x73e62  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73e67  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::stringSelectedVersion
0x73e6c  ldloc.3
0x73e6d  stloc.0
0x73e6e  br.s     loc_73ED3
0x73e70  ldc.i4.2
0x73e71  ldarg.0
0x73e72  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73e77  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x73e7c  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x73e81  bne.un.s loc_73E98
0x73e83  ldarg.0
0x73e84  ldstr    aComboentryvers_0// "ComboEntryVersion2"
0x73e89  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73e8e  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::stringSelectedVersion
0x73e93  ldloc.s  4
0x73e95  stloc.0
0x73e96  br.s     loc_73ED3
0x73e98  ldc.i4.1
0x73e99  ldarg.0
0x73e9a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x73e9f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x73ea4  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x73ea9  bne.un.s loc_73EC0
0x73eab  ldarg.0
0x73eac  ldstr    aComboentryvers_1// "ComboEntryVersion1"
0x73eb1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73eb6  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::stringSelectedVersion
0x73ebb  ldloc.s  5
0x73ebd  stloc.0
0x73ebe  br.s     loc_73ED3
0x73ec0  ldarg.0
0x73ec1  ldstr    aComboentryvers_2// "ComboEntryVersionAt"
0x73ec6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73ecb  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::stringSelectedVersion
0x73ed0  ldloc.s  6
0x73ed2  stloc.0
0x73ed3  ldarg.0
0x73ed4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x73ed9  ldloc.0
0x73eda  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x73edf  ldarg.0
0x73ee0  ldc.i4.1
0x73ee1  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::flagInitializedVersion
0x73ee6  ret
```
