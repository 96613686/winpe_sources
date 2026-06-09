# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::SwitchVersion

- ea: `0x72900`
- end: `0x729f2`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::SwitchVersion`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x73290`

## callees

- `0x12ed0`
- `0x14620`
- `0x146b0`
- `0x63e50`
- `0x63e60`
- `0x64630`
- `0x67d30`
- `0x72900`
- `0x72e00`

## string_xrefs

- `0x72939`: `ComboEntryVersion3`
- `0x7295f`: `ComboEntryVersion2`
- `0x72985`: `ComboEntryVersion1`

## pseudocode

```c

```

## disassembly

```asm
0x72900  ldarg.0
0x72901  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::flagInitializedVersion
0x72906  brfalse  loc_729BB
0x7290b  ldarg.0
0x7290c  ldarg.1
0x7290d  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::stringSelectedVersion
0x72912  call     string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetBranding()
0x72917  stloc.0
0x72918  ldarg.1
0x72919  ldloc.0
0x7291a  ldc.i4.0
0x7291b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x72920  brtrue.s loc_72938
0x72922  ldarg.0
0x72923  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72928  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x7292d  ldc.i4.4
0x7292e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x72933  br       loc_729BB
0x72938  ldarg.1
0x72939  ldstr    aComboentryvers// "ComboEntryVersion3"
0x7293e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x72943  ldc.i4.0
0x72944  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x72949  brtrue.s loc_7295E
0x7294b  ldarg.0
0x7294c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72951  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x72956  ldc.i4.3
0x72957  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x7295c  br.s     loc_729BB
0x7295e  ldarg.1
0x7295f  ldstr    aComboentryvers_0// "ComboEntryVersion2"
0x72964  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x72969  ldc.i4.0
0x7296a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7296f  brtrue.s loc_72984
0x72971  ldarg.0
0x72972  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x72977  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x7297c  ldc.i4.2
0x7297d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x72982  br.s     loc_729BB
0x72984  ldarg.1
0x72985  ldstr    aComboentryvers_1// "ComboEntryVersion1"
0x7298a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7298f  ldc.i4.0
0x72990  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x72995  brtrue.s loc_729AA
0x72997  ldarg.0
0x72998  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x7299d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x729a2  ldc.i4.1
0x729a3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x729a8  br.s     loc_729BB
0x729aa  ldarg.0
0x729ab  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x729b0  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x729b5  ldc.i4.0
0x729b6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Compatibility(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility value)
0x729bb  ldarg.2
0x729bc  brfalse.s loc_729F1
0x729be  ldarg.0
0x729bf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.VersionDataHandler Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::versionData
0x729c4  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.VersionDataHandler::get_Initialized()
0x729c9  brfalse.s loc_729EB
0x729cb  ldarg.0
0x729cc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.VersionDataHandler Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::versionData
0x729d1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SetVersionData Microsoft.Windows.ManagementUI.CombinedControls.VersionDataHandler::setVersionDataInParent
0x729d6  ldarg.0
0x729d7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x729dc  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x729e1  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::get_Compatibility()
0x729e6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SetVersionData::Invoke(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility taskVersion)
0x729eb  ldarg.0
0x729ec  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::DataToControls()
0x729f1  ret
```
