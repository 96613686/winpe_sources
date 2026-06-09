# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::InitializeVersion

- ea: `0x72460`
- end: `0x72637`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::InitializeVersion`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x72860`

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
- `0x72460`

## string_xrefs

- `0x724c6`: `ComboEntryVersion3`
- `0x725ad`: `ComboEntryVersion3`
- `0x724f8`: `ComboEntryVersion2`
- `0x725d4`: `ComboEntryVersion2`
- `0x72534`: `ComboEntryVersion1`
- `0x725fc`: `ComboEntryVersion1`
- `0x72562`: `ComboEntryVersionAt`
- `0x72611`: `ComboEntryVersionAt`

## pseudocode

```c

```

## disassembly

```asm
0x72460  ldarg.0
0x72461  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x72466  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::ClearComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo)
0x7246b  ldc.i4.0
0x7246c  stloc.0
0x7246d  ldc.i4.0
0x7246e  stloc.1
0x7246f  ldc.i4.0
0x72470  stloc.2
0x72471  ldc.i4.0
0x72472  stloc.3
0x72473  ldc.i4.0
0x72474  stloc.s  4
0x72476  ldc.i4.0
0x72477  stloc.s  5
0x72479  ldc.i4.0
0x7247a  stloc.s  6
0x7247c  ldc.i4   0x10004
0x72481  ldarg.0
0x72482  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72487  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x7248c  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x72491  bgt.s    loc_724A9
0x72493  ldarg.0
0x72494  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x72499  call     string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetBranding()
0x7249e  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x724a3  ldloc.1
0x724a4  dup
0x724a5  ldc.i4.1
0x724a6  add
0x724a7  stloc.1
0x724a8  stloc.2
0x724a9  ldc.i4   0x10003
0x724ae  ldarg.0
0x724af  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x724b4  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x724b9  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x724be  bgt.s    loc_724DB
0x724c0  ldarg.0
0x724c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x724c6  ldstr    aComboentryvers// "ComboEntryVersion3"
0x724cb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x724d0  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x724d5  ldloc.1
0x724d6  dup
0x724d7  ldc.i4.1
0x724d8  add
0x724d9  stloc.1
0x724da  stloc.3
0x724db  ldc.i4   0x10002
0x724e0  ldarg.0
0x724e1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x724e6  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x724eb  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x724f0  bgt.s    loc_7250E
0x724f2  ldarg.0
0x724f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x724f8  ldstr    aComboentryvers_0// "ComboEntryVersion2"
0x724fd  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x72502  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x72507  ldloc.1
0x72508  dup
0x72509  ldc.i4.1
0x7250a  add
0x7250b  stloc.1
0x7250c  stloc.s  4
0x7250e  ldc.i4.1
0x7250f  ldarg.0
0x72510  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72515  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x7251a  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x7251f  beq.s    loc_7252E
0x72521  ldarg.0
0x72522  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72527  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_IsNew()
0x7252c  brfalse.s loc_7254A
0x7252e  ldarg.0
0x7252f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x72534  ldstr    aComboentryvers_1// "ComboEntryVersion1"
0x72539  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7253e  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x72543  ldloc.1
0x72544  dup
0x72545  ldc.i4.1
0x72546  add
0x72547  stloc.1
0x72548  stloc.s  5
0x7254a  ldarg.0
0x7254b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72550  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x72555  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x7255a  brtrue.s loc_72574
0x7255c  ldarg.0
0x7255d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x72562  ldstr    aComboentryvers_2// "ComboEntryVersionAt"
0x72567  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7256c  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x72571  ldloc.1
0x72572  stloc.s  6
0x72574  ldc.i4.4
0x72575  ldarg.0
0x72576  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x7257b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x72580  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x72585  bne.un.s loc_72599
0x72587  ldarg.0
0x72588  call     string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetBranding()
0x7258d  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::stringSelectedVersion
0x72592  ldloc.2
0x72593  stloc.0
0x72594  br       loc_72623
0x72599  ldc.i4.3
0x7259a  ldarg.0
0x7259b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x725a0  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x725a5  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x725aa  bne.un.s loc_725C0
0x725ac  ldarg.0
0x725ad  ldstr    aComboentryvers// "ComboEntryVersion3"
0x725b2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x725b7  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::stringSelectedVersion
0x725bc  ldloc.3
0x725bd  stloc.0
0x725be  br.s     loc_72623
0x725c0  ldc.i4.2
0x725c1  ldarg.0
0x725c2  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x725c7  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x725cc  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x725d1  bne.un.s loc_725E8
0x725d3  ldarg.0
0x725d4  ldstr    aComboentryvers_0// "ComboEntryVersion2"
0x725d9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x725de  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::stringSelectedVersion
0x725e3  ldloc.s  4
0x725e5  stloc.0
0x725e6  br.s     loc_72623
0x725e8  ldc.i4.1
0x725e9  ldarg.0
0x725ea  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x725ef  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x725f4  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x725f9  bne.un.s loc_72610
0x725fb  ldarg.0
0x725fc  ldstr    aComboentryvers_1// "ComboEntryVersion1"
0x72601  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x72606  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::stringSelectedVersion
0x7260b  ldloc.s  5
0x7260d  stloc.0
0x7260e  br.s     loc_72623
0x72610  ldarg.0
0x72611  ldstr    aComboentryvers_2// "ComboEntryVersionAt"
0x72616  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7261b  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::stringSelectedVersion
0x72620  ldloc.s  6
0x72622  stloc.0
0x72623  ldarg.0
0x72624  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x72629  ldloc.0
0x7262a  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x7262f  ldarg.0
0x72630  ldc.i4.1
0x72631  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagInitializedVersion
0x72636  ret
```
