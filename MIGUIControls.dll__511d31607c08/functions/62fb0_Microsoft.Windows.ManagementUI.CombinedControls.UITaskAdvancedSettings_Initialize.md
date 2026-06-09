# Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::Initialize

- ea: `0x62fb0`
- end: `0x62ffb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::Initialize`
- size: `75`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x65790`
- `0x6dba0`
- `0x6eda0`

## callees

- `0x12ed0`
- `0x63000`
- `0x633f0`

## string_xrefs

- `0x62fb1`: `ComboEntryIgnoreNewInstance`
- `0x62fc2`: `ComboEntryRunInstancesInParallel`
- `0x62fd3`: `ComboEntryQueueNewInstance`
- `0x62fe4`: `ComboEntryStopExistingInstance`

## pseudocode

```c

```

## disassembly

```asm
0x62fb0  ldarg.0
0x62fb1  ldstr    aComboentryigno// "ComboEntryIgnoreNewInstance"
0x62fb6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62fbb  ldc.i4.2
0x62fbc  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::Add(string label, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesPolicy value)
0x62fc1  ldarg.0
0x62fc2  ldstr    aComboentryruni// "ComboEntryRunInstancesInParallel"
0x62fc7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62fcc  ldc.i4.0
0x62fcd  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::Add(string label, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesPolicy value)
0x62fd2  ldarg.0
0x62fd3  ldstr    aComboentryqueu// "ComboEntryQueueNewInstance"
0x62fd8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62fdd  ldc.i4.1
0x62fde  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::Add(string label, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesPolicy value)
0x62fe3  ldarg.0
0x62fe4  ldstr    aComboentrystop// "ComboEntryStopExistingInstance"
0x62fe9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x62fee  ldc.i4.3
0x62fef  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::Add(string label, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesPolicy value)
0x62ff4  ldarg.0
0x62ff5  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::Reset()
0x62ffa  ret
```
