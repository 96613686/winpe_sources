# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::SwitchVersion

- ea: `0x74050`
- end: `0x74140`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::SwitchVersion`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x14620`
- `0x146b0`
- `0x63e50`
- `0x63e60`
- `0x64630`
- `0x67d30`
- `0x74050`
- `0x74290`

## string_xrefs

- `0x74087`: `ComboEntryVersion3`
- `0x740ad`: `ComboEntryVersion2`
- `0x740d3`: `ComboEntryVersion1`

## pseudocode

```c

```

## disassembly

```asm
0x74050  ldarg.0
0x74051  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::flagInitializedVersion
0x74056  brfalse  loc_74109
0x7405b  ldarg.0
0x7405c  ldarg.1
0x7405d  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::stringSelectedVersion
0x74062  ldarg.1
0x74063  call     string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetBranding()
0x74068  ldc.i4.0
0x74069  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7406e  brtrue.s loc_74086
0x74070  ldarg.0
0x74071  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x74076  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x7407b  ldc.i4.4
0x7407c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x74081  br       loc_74109
0x74086  ldarg.1
0x74087  ldstr    aComboentryvers// "ComboEntryVersion3"
0x7408c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x74091  ldc.i4.0
0x74092  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x74097  brtrue.s loc_740AC
0x74099  ldarg.0
0x7409a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x7409f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x740a4  ldc.i4.3
0x740a5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x740aa  br.s     loc_74109
0x740ac  ldarg.1
0x740ad  ldstr    aComboentryvers_0// "ComboEntryVersion2"
0x740b2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x740b7  ldc.i4.0
0x740b8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x740bd  brtrue.s loc_740D2
0x740bf  ldarg.0
0x740c0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x740c5  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x740ca  ldc.i4.2
0x740cb  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x740d0  br.s     loc_74109
0x740d2  ldarg.1
0x740d3  ldstr    aComboentryvers_1// "ComboEntryVersion1"
0x740d8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x740dd  ldc.i4.0
0x740de  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x740e3  brtrue.s loc_740F8
0x740e5  ldarg.0
0x740e6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x740eb  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x740f0  ldc.i4.1
0x740f1  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x740f6  br.s     loc_74109
0x740f8  ldarg.0
0x740f9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x740fe  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x74103  ldc.i4.0
0x74104  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x74109  ldarg.2
0x7410a  brfalse.s loc_7413F
0x7410c  ldarg.0
0x7410d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.VersionDataHandler Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::versionData
0x74112  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.VersionDataHandler::get_Initialized()
0x74117  brfalse.s loc_74139
0x74119  ldarg.0
0x7411a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.VersionDataHandler Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::versionData
0x7411f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SetVersionData Microsoft.Windows.ManagementUI.CombinedControls.VersionDataHandler::setVersionDataInParent
0x74124  ldarg.0
0x74125  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x7412a  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x7412f  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x74134  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SetVersionData::Invoke(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility taskVersion)
0x74139  ldarg.0
0x7413a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::DataToControls()
0x7413f  ret
```
