# System.Deployment.Application.ShellExposure::GenerateAppShortcut

- ea: `0x1dba0`
- end: `0x1dc5b`
- name: `System.Deployment.Application.ShellExposure::GenerateAppShortcut`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1d970`

## callees

- `0x17d40`
- `0x1dba0`
- `0x1ece0`
- `0x1ede0`
- `0x1eee0`
- `0x24010`
- `0x24b90`
- `0x2c520`
- `0x2c540`

## string_xrefs

- `0x1dbdf`: `Shortcut file created: `
- `0x1dc45`: `Desktop Shortcut file created: `

## pseudocode

```c

```

## disassembly

```asm
0x1dba0  ldarg.1
0x1dba1  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1dba6  ldc.i4.0
0x1dba7  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x1dbac  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(string, bool, class [mscorlib]System.Text.Encoding)
0x1dbb1  stloc.0
0x1dbb2  ldloc.0
0x1dbb3  ldstr    a01_0// "{0}#{1}"
0x1dbb8  ldarg.0
0x1dbb9  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1dbbe  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1dbc3  ldarg.0
0x1dbc4  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1dbc9  callvirt instance string [mscorlib]System.Object::ToString()
0x1dbce  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x1dbd3  leave.s  loc_1DBDF
0x1dbd5  ldloc.0
0x1dbd6  brfalse.s loc_1DBDE
0x1dbd8  ldloc.0
0x1dbd9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dbde  endfinally
0x1dbdf  ldstr    aShortcutFileCr// "Shortcut file created: "
0x1dbe4  ldarg.1
0x1dbe5  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1dbea  call     string [mscorlib]System.String::Concat(string, string)
0x1dbef  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1dbf4  ldarg.0
0x1dbf5  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1dbfa  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x1dbff  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_CreateDesktopShortcut()
0x1dc04  brfalse.s loc_1DC5A
0x1dc06  ldarg.1
0x1dc07  callvirt instance string ShellExposureInformation::get_DesktopShortcutPath()
0x1dc0c  ldc.i4.0
0x1dc0d  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x1dc12  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(string, bool, class [mscorlib]System.Text.Encoding)
0x1dc17  stloc.1
0x1dc18  ldloc.1
0x1dc19  ldstr    a01_0// "{0}#{1}"
0x1dc1e  ldarg.0
0x1dc1f  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1dc24  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1dc29  ldarg.0
0x1dc2a  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1dc2f  callvirt instance string [mscorlib]System.Object::ToString()
0x1dc34  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x1dc39  leave.s  loc_1DC45
0x1dc3b  ldloc.1
0x1dc3c  brfalse.s loc_1DC44
0x1dc3e  ldloc.1
0x1dc3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dc44  endfinally
0x1dc45  ldstr    aDesktopShortcu// "Desktop Shortcut file created: "
0x1dc4a  ldarg.1
0x1dc4b  callvirt instance string ShellExposureInformation::get_DesktopShortcutPath()
0x1dc50  call     string [mscorlib]System.String::Concat(string, string)
0x1dc55  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1dc5a  ret
```
