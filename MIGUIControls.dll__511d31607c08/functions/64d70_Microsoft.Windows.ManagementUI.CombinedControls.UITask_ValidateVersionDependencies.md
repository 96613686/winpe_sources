# Microsoft.Windows.ManagementUI.CombinedControls.UITask::ValidateVersionDependencies

- ea: `0x64d70`
- end: `0x64eff`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::ValidateVersionDependencies`
- size: `399`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x65010`
- `0x8a150`
- `0x8a560`
- `0x8aca0`

## callees

- `0x12ed0`
- `0x1b9a0`
- `0x5d760`
- `0x5ed70`
- `0x60140`
- `0x60220`
- `0x608a0`
- `0x62ca0`
- `0x62d00`
- `0x63e50`
- `0x64630`
- `0x64640`
- `0x64660`
- `0x64680`
- `0x64d70`
- `0x67c70`

## string_xrefs

- `0x64d7d`: `TSValidationMsgAtTaskMustBeUpgraded`
- `0x64d8c`: `UITaskRegistrationInfo`
- `0x64dff`: `UITaskRegistrationInfo`
- `0x64e2c`: `UITaskRegistrationInfo`
- `0x64e59`: `UITaskRegistrationInfo`
- `0x64eed`: `UITaskRegistrationInfo`
- `0x64d91`: `Compatibility`
- `0x64e04`: `Compatibility`
- `0x64e31`: `Compatibility`
- `0x64e5e`: `Compatibility`
- `0x64ef2`: `Compatibility`
- `0x64ecd`: `UITaskUser`
- `0x64ed2`: `TaskLogonType`

## pseudocode

```c

```

## disassembly

```asm
0x64d70  ldarg.0
0x64d71  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x64d76  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x64d7b  brtrue.s loc_64D9D
0x64d7d  ldstr    aTsvalidationms_14// "TSValidationMsgAtTaskMustBeUpgraded"
0x64d82  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64d87  ldc.i4   0x80041318
0x64d8c  ldstr    aUitaskregistra// "UITaskRegistrationInfo"
0x64d91  ldstr    aCompatibility// "Compatibility"
0x64d96  ldnull
0x64d97  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64d9c  throw
0x64d9d  ldc.i4.2
0x64d9e  ldarg.0
0x64d9f  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x64da4  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x64da9  ble      loc_64EFE
0x64dae  ldnull
0x64daf  stloc.0
0x64db0  ldc.i4.1
0x64db1  ldarg.0
0x64db2  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x64db7  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UIActionList::get_Count()
0x64dbc  bge.s    loc_64E10
0x64dbe  ldc.i4   0x10002
0x64dc3  ldarg.0
0x64dc4  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64dc9  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x64dce  ble.s    loc_64DF0
0x64dd0  ldstr    aTsvalidationms_15// "TSValidationMsgMaximumV1SystemActionCou"...
0x64dd5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64dda  ldc.i4   0x80041318
0x64ddf  ldstr    aUiactionlist// "UIActionList"
0x64de4  ldstr    aCount// "Count"
0x64de9  ldnull
0x64dea  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64def  throw
0x64df0  ldstr    aTsvalidationms_16// "TSValidationMsgMaximumV1ActionCount"
0x64df5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64dfa  ldc.i4   0x80041318
0x64dff  ldstr    aUitaskregistra// "UITaskRegistrationInfo"
0x64e04  ldstr    aCompatibility// "Compatibility"
0x64e09  ldnull
0x64e0a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64e0f  throw
0x64e10  ldarg.0
0x64e11  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x64e16  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UIActionList::ContainsVistaAction()
0x64e1b  brfalse.s loc_64E3D
0x64e1d  ldstr    aTsvalidationms_17// "TSValidationMsgContainsVistaAction"
0x64e22  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64e27  ldc.i4   0x80041318
0x64e2c  ldstr    aUitaskregistra// "UITaskRegistrationInfo"
0x64e31  ldstr    aCompatibility// "Compatibility"
0x64e36  ldnull
0x64e37  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64e3c  throw
0x64e3d  ldarg.0
0x64e3e  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITriggerList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TriggerList()
0x64e43  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITriggerList::ContainsVistaTrigger()
0x64e48  brfalse.s loc_64E6A
0x64e4a  ldstr    aTsvalidationms_18// "TSValidationMsgContainsVistaTrigger"
0x64e4f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64e54  ldc.i4   0x80041318
0x64e59  ldstr    aUitaskregistra// "UITaskRegistrationInfo"
0x64e5e  ldstr    aCompatibility// "Compatibility"
0x64e63  ldnull
0x64e64  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64e69  throw
0x64e6a  ldarg.0
0x64e6b  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITriggerList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TriggerList()
0x64e70  ldloca.s 0
0x64e72  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITriggerList::ContainsMonthlyScheduleWithLastDaySet(class Microsoft.Windows.ManagementUI.CombinedControls.UIMonthlyTrigger& trigger)
0x64e77  brfalse.s loc_64E9E
0x64e79  ldstr    aTsvalidationms_19// "TSValidationMsgNoLastDayOfMonth"
0x64e7e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64e83  ldc.i4   0x80041318
0x64e88  ldstr    aUimonthlytrigg// "UIMonthlyTrigger"
0x64e8d  ldstr    aDaysofmonth// "DaysOfMonth"
0x64e92  ldloc.0
0x64e93  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_Id()
0x64e98  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64e9d  throw
0x64e9e  ldc.i4.4
0x64e9f  ldarg.0
0x64ea0  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x64ea5  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserLogonType()
0x64eaa  bne.un.s loc_64EFE
0x64eac  ldc.i4   0x10002
0x64eb1  ldarg.0
0x64eb2  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64eb7  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x64ebc  ble.s    loc_64EDE
0x64ebe  ldstr    aTsvalidationms_20// "TSValidationMsgPreVistaSystemGroupPrinc"...
0x64ec3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64ec8  ldc.i4   0x80041318
0x64ecd  ldstr    aUitaskuser// "UITaskUser"
0x64ed2  ldstr    aTasklogontype// "TaskLogonType"
0x64ed7  ldnull
0x64ed8  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64edd  throw
0x64ede  ldstr    aTsvalidationms_21// "TSValidationMsgPreVistaGroupPrincipal"
0x64ee3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64ee8  ldc.i4   0x80041318
0x64eed  ldstr    aUitaskregistra// "UITaskRegistrationInfo"
0x64ef2  ldstr    aCompatibility// "Compatibility"
0x64ef7  ldnull
0x64ef8  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64efd  throw
0x64efe  ret
```
