# Microsoft.VisualStudio.Setup.Services.RestartManager::.cctor

- ea: `0x43ed0`
- end: `0x43f49`
- name: `Microsoft.VisualStudio.Setup.Services.RestartManager::.cctor`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x43eee`: `PendingFileRenameOperations`
- `0x43ed0`: `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Auto Update\RebootRequired`
- `0x43eda`: `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\RebootPending`

## pseudocode

```c

```

## disassembly

```asm
0x43ed0  ldstr    aHklmSoftwareMi// "HKLM\\SOFTWARE\\Microsoft\\Windows\\Cur"...
0x43ed5  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::WURestartRequiredKey
0x43eda  ldstr    aHklmSoftwareMi_0// "HKLM\\SOFTWARE\\Microsoft\\Windows\\Cur"...
0x43edf  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::CBSRestartRequiredKey
0x43ee4  ldstr    aHklmSystemCurr// "HKLM\\SYSTEM\\CurrentControlSet\\Contro"...
0x43ee9  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::PendingFileRenameOperationsKey
0x43eee  ldstr    aPendingfileren// "PendingFileRenameOperations"
0x43ef3  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::PendingFileRenameOperationsValue
0x43ef8  ldstr    asc_99144// "!\\??\\"
0x43efd  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::PendingFileRenameValuePrefix
0x43f02  ldstr    aReboot// "Reboot"
0x43f07  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::HardRebootRegistryKeyName
0x43f0c  ldstr    aSoftreboot// "SoftReboot"
0x43f11  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::SoftRebootRegistryKeyName
0x43f16  ldsfld   string Microsoft.VisualStudio.Setup.Services.PolicyService::RegistryKeyPath
0x43f1b  ldstr    asc_8155E// "\\"
0x43f20  ldsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::HardRebootRegistryKeyName
0x43f25  call     string [mscorlib]System.String::Concat(string, string, string)
0x43f2a  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::HardRebootRegistryKeyPath
0x43f2f  ldsfld   string Microsoft.VisualStudio.Setup.Services.PolicyService::RegistryKeyPath
0x43f34  ldstr    asc_8155E// "\\"
0x43f39  ldsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::SoftRebootRegistryKeyName
0x43f3e  call     string [mscorlib]System.String::Concat(string, string, string)
0x43f43  stsfld   string Microsoft.VisualStudio.Setup.Services.RestartManager::SoftRebootRegistryKeyPath
0x43f48  ret
```
