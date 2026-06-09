# System.Deployment.Application.ShellExposure::RemovePins

- ea: `0x1de90`
- end: `0x1decf`
- name: `System.Deployment.Application.ShellExposure::RemovePins`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1f5f0`

## callees

- `0x17d40`
- `0x1de90`
- `0x1df50`
- `0x1ece0`
- `0x2c1e0`
- `0x2c520`

## string_xrefs

- `0x1de90`: `Attempting to remove shell pins.`

## pseudocode

```c

```

## disassembly

```asm
0x1de90  ldstr    aAttemptingToRe// "Attempting to remove shell pins."
0x1de95  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1de9a  ldarg.0
0x1de9b  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1dea0  stloc.0
0x1dea1  ldloc.0
0x1dea2  call     class ShellExposureInformation ShellExposureInformation::CreateShellExposureInformation(class System.Deployment.Application.DefinitionIdentity subscriptionIdentity)
0x1dea7  stloc.1
0x1dea8  ldloc.1
0x1dea9  brtrue.s loc_1DEB6
0x1deab  ldstr    aShellexposurei// "shellExposureInformation is null."
0x1deb0  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1deb5  ret
0x1deb6  ldloc.1
0x1deb7  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1debc  call     bool [mscorlib]System.IO.File::Exists(string)
0x1dec1  brfalse.s loc_1DECE
0x1dec3  ldloc.1
0x1dec4  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1dec9  call     void System.Deployment.Application.ShellExposure::UnpinShortcut(string shortcutPath)
0x1dece  ret
```
