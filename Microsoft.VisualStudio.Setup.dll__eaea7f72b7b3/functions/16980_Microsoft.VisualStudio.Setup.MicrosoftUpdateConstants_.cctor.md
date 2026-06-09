# Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::.cctor

- ea: `0x16980`
- end: `0x16a93`
- name: `Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::.cctor`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x16980`: `AllowMUUpdateService`
- `0x1698a`: `AdministratorUpdatesEnabled`
- `0x16994`: `AdministratorUpdatesOptOut`
- `0x1699e`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU`
- `0x169a8`: `SOFTWARE\Microsoft\PolicyManager\current\device\Update`
- `0x16a08`: `SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
- `0x16a14`: `SOFTWARE\WOW6432Node\Microsoft\WindowsUpdate\UX\Settings`

## pseudocode

```c

```

## disassembly

```asm
0x16980  ldstr    aAllowmuupdates// "AllowMUUpdateService"
0x16985  stsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AllowMUUpdateServiceEnabledRegValue
0x1698a  ldstr    aAdministratoru// "AdministratorUpdatesEnabled"
0x1698f  stsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AdministratorUpdatesEnabledRegValue
0x16994  ldstr    aAdministratoru_0// "AdministratorUpdatesOptOut"
0x16999  stsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AdministratorUpdatesOptOutRegValue
0x1699e  ldstr    aSoftwarePolici// "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x169a3  stsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::ActiveDirectoryRegKey
0x169a8  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\PolicyManager\\cur"...
0x169ad  stsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AzureActiveDirectoryRegKey
0x169b2  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x169b7  dup
0x169b8  ldstr    aSoftwarePolici_0// "SOFTWARE\\Policies\\Microsoft\\VisualSt"...
0x169bd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x169c2  pop
0x169c3  dup
0x169c4  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\VisualStudio\\Setu"...
0x169c9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x169ce  pop
0x169cf  dup
0x169d0  ldstr    aSoftwareWow643// "SOFTWARE\\WOW6432Node\\Microsoft\\Visua"...
0x169d5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x169da  pop
0x169db  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::EnterpriseDefaultRegKeyPaths
0x169e0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x169e5  dup
0x169e6  ldsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AzureActiveDirectoryRegKey
0x169eb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x169f0  pop
0x169f1  dup
0x169f2  ldsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::ActiveDirectoryRegKey
0x169f7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x169fc  pop
0x169fd  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::EnterpriseMUUpdateServiceDefaultRegKeyPaths
0x16a02  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x16a07  dup
0x16a08  ldstr    aSoftwareMicros_1// "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x16a0d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x16a12  pop
0x16a13  dup
0x16a14  ldstr    aSoftwareWow643_0// "SOFTWARE\\WOW6432Node\\Microsoft\\Windo"...
0x16a19  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x16a1e  pop
0x16a1f  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::UXSettingsRegistryPaths
0x16a24  ldc.i4   0x3E9
0x16a29  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::VSInstallerRelatedProcessRunningExitCode
0x16a2e  ldc.i4   0x3EA
0x16a33  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::VSPausedInstallExitCode
0x16a38  ldc.i4   0x3EB
0x16a3d  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::VSIsRunningExitCode
0x16a42  ldc.i4   0x3EC
0x16a47  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::NoInternetExitCode
0x16a4c  ldc.i4   0x3ED
0x16a51  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AdministratorUpdatesEnabledRegValueZeroOrNotSetExitCode
0x16a56  ldc.i4   0x3EE
0x16a5b  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AdministratorUpdatesOptOutRegValueSetExitCode
0x16a60  ldc.i4   0x3EF
0x16a65  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::VSInstallerMissingExitCode
0x16a6a  ldc.i4   0x3F1
0x16a6f  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::LayoutMissingPackagesExitCode
0x16a74  ldc.i4   0x3F2
0x16a79  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::LayoutUnauthorizedAccessExitCode
0x16a7e  ldc.i4   0xBC2
0x16a83  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::SystemRebootRequiredExitCode
0x16a88  ldc.i4   0x41A
0x16a8d  stsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::VSthroughMUUpdatesOptOutRegValueSetExitCode
0x16a92  ret
```
