# Microsoft.Windows.ManagementUI.CombinedControls.UITask::ValidateSectionInterdependencies

- ea: `0x64f00`
- end: `0x65001`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::ValidateSectionInterdependencies`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x65010`

## callees

- `0x12ed0`
- `0x1b9a0`
- `0x60110`
- `0x62c50`
- `0x62f40`
- `0x64640`
- `0x64660`
- `0x646c0`
- `0x64f00`

## string_xrefs

- `0x64fef`: `UITaskAdvancedSettings`
- `0x64f21`: `UITaskRegistrationInfo`
- `0x64f8f`: `UITaskRegistrationInfo`
- `0x64fe0`: `TSValidationMsgDeleteExpiredRequiresEndBoundary`
- `0x64ff4`: `DeleteExpiredTaskAfter`

## pseudocode

```c

```

## disassembly

```asm
0x64f00  call     char[] [mscorlib]System.IO.Path::GetInvalidFileNameChars()
0x64f05  ldarg.0
0x64f06  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.UITask::stringTaskName
0x64f0b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64f10  brfalse.s loc_64F32
0x64f12  ldstr    aTsvalidationms_22// "TSValidationMsgMissingRequiredFields"
0x64f17  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64f1c  ldc.i4   0x80041318
0x64f21  ldstr    aUitaskregistra// "UITaskRegistrationInfo"
0x64f26  ldstr    aName// "Name"
0x64f2b  ldnull
0x64f2c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64f31  throw
0x64f32  ldarg.0
0x64f33  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x64f38  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UIActionList::get_ActionsList()
0x64f3d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x64f42  brtrue.s loc_64F64
0x64f44  ldstr    aTsvalidationms_22// "TSValidationMsgMissingRequiredFields"
0x64f49  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64f4e  ldc.i4   0x80041318
0x64f53  ldstr    aUiactionlist// "UIActionList"
0x64f58  ldstr    aCount// "Count"
0x64f5d  ldnull
0x64f5e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64f63  throw
0x64f64  stloc.0
0x64f65  ldc.i4.0
0x64f66  stloc.1
0x64f67  br.s     loc_64FB6
0x64f69  ldloc.0
0x64f6a  ldloc.1
0x64f6b  ldelem.u2
0x64f6c  stloc.2
0x64f6d  ldc.i4.0
0x64f6e  stloc.3
0x64f6f  br.s     loc_64FA4
0x64f71  ldloc.2
0x64f72  ldarg.0
0x64f73  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.UITask::stringTaskName
0x64f78  ldloc.3
0x64f79  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x64f7e  bne.un.s loc_64FA0
0x64f80  ldstr    aMessageinvalid// "MessageInvalidCharacter"
0x64f85  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64f8a  ldc.i4   0x80041318
0x64f8f  ldstr    aUitaskregistra// "UITaskRegistrationInfo"
0x64f94  ldstr    aName// "Name"
0x64f99  ldnull
0x64f9a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64f9f  throw
0x64fa0  ldloc.3
0x64fa1  ldc.i4.1
0x64fa2  add
0x64fa3  stloc.3
0x64fa4  ldloc.3
0x64fa5  ldarg.0
0x64fa6  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.UITask::stringTaskName
0x64fab  callvirt instance int32 [mscorlib]System.String::get_Length()
0x64fb0  blt.s    loc_64F71
0x64fb2  ldloc.1
0x64fb3  ldc.i4.1
0x64fb4  add
0x64fb5  stloc.1
0x64fb6  ldloc.1
0x64fb7  ldloc.0
0x64fb8  ldlen
0x64fb9  conv.i4
0x64fba  blt.s    loc_64F69
0x64fbc  ldarg.0
0x64fbd  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITriggerList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TriggerList()
0x64fc2  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITriggerList::EndBoundaryIsSet()
0x64fc7  brtrue.s loc_65000
0x64fc9  ldarg.0
0x64fca  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_AdvancedSettings()
0x64fcf  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::get_DeleteExpiredTaskAfter()
0x64fd4  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MinValue
0x64fd9  call     int32 [mscorlib]System.TimeSpan::Compare(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x64fde  brfalse.s loc_65000
0x64fe0  ldstr    aTsvalidationms_23// "TSValidationMsgDeleteExpiredRequiresEnd"...
0x64fe5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64fea  ldc.i4   0x80041318
0x64fef  ldstr    aUitaskadvanced// "UITaskAdvancedSettings"
0x64ff4  ldstr    aDeleteexpiredt// "DeleteExpiredTaskAfter"
0x64ff9  ldnull
0x64ffa  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x64fff  throw
0x65000  ret
```
