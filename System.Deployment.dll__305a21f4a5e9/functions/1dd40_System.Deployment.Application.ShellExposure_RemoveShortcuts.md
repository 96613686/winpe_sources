# System.Deployment.Application.ShellExposure::RemoveShortcuts

- ea: `0x1dd40`
- end: `0x1de8c`
- name: `System.Deployment.Application.ShellExposure::RemoveShortcuts`
- size: `332`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1d5f0`
- `0x1d970`

## callees

- `0x14700`
- `0x17d40`
- `0x1dd40`
- `0x23020`
- `0x2c500`
- `0x2c510`
- `0x2c520`
- `0x2c530`
- `0x2c540`

## string_xrefs

- `0x1de01`: `Removed shortcut entries : `

## pseudocode

```c

```

## disassembly

```asm
0x1dd40  ldarg.0
0x1dd41  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1dd46  call     bool [mscorlib]System.IO.File::Exists(string)
0x1dd4b  brfalse.s loc_1DD58
0x1dd4d  ldarg.0
0x1dd4e  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1dd53  call     void [mscorlib]System.IO.File::Delete(string)
0x1dd58  ldarg.0
0x1dd59  callvirt instance string ShellExposureInformation::get_SupportShortcutPath()
0x1dd5e  call     bool [mscorlib]System.IO.File::Exists(string)
0x1dd63  brfalse.s loc_1DD70
0x1dd65  ldarg.0
0x1dd66  callvirt instance string ShellExposureInformation::get_SupportShortcutPath()
0x1dd6b  call     void [mscorlib]System.IO.File::Delete(string)
0x1dd70  ldarg.0
0x1dd71  callvirt instance string ShellExposureInformation::get_DesktopShortcutPath()
0x1dd76  call     bool [mscorlib]System.IO.File::Exists(string)
0x1dd7b  brfalse.s loc_1DD88
0x1dd7d  ldarg.0
0x1dd7e  callvirt instance string ShellExposureInformation::get_DesktopShortcutPath()
0x1dd83  call     void [mscorlib]System.IO.File::Delete(string)
0x1dd88  ldarg.0
0x1dd89  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1dd8e  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1dd93  brfalse.s loc_1DDC0
0x1dd95  ldarg.0
0x1dd96  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1dd9b  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x1dda0  stloc.0
0x1dda1  ldarg.0
0x1dda2  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1dda7  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x1ddac  stloc.1
0x1ddad  ldloc.0
0x1ddae  ldlen
0x1ddaf  brtrue.s loc_1DDC0
0x1ddb1  ldloc.1
0x1ddb2  ldlen
0x1ddb3  brtrue.s loc_1DDC0
0x1ddb5  ldarg.0
0x1ddb6  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1ddbb  call     void [mscorlib]System.IO.Directory::Delete(string)
0x1ddc0  ldarg.0
0x1ddc1  callvirt instance string ShellExposureInformation::get_ApplicationRootFolderPath()
0x1ddc6  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1ddcb  brfalse.s loc_1DDF8
0x1ddcd  ldarg.0
0x1ddce  callvirt instance string ShellExposureInformation::get_ApplicationRootFolderPath()
0x1ddd3  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x1ddd8  stloc.2
0x1ddd9  ldarg.0
0x1ddda  callvirt instance string ShellExposureInformation::get_ApplicationRootFolderPath()
0x1dddf  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x1dde4  stloc.3
0x1dde5  ldloc.2
0x1dde6  ldlen
0x1dde7  brtrue.s loc_1DDF8
0x1dde9  ldloc.3
0x1ddea  ldlen
0x1ddeb  brtrue.s loc_1DDF8
0x1dded  ldarg.0
0x1ddee  callvirt instance string ShellExposureInformation::get_ApplicationRootFolderPath()
0x1ddf3  call     void [mscorlib]System.IO.Directory::Delete(string)
0x1ddf8  ldc.i4.s 0xA
0x1ddfa  newarr   [mscorlib]System.String
0x1ddff  dup
0x1de00  ldc.i4.0
0x1de01  ldstr    aRemovedShortcu// "Removed shortcut entries : "
0x1de06  stelem.ref
0x1de07  dup
0x1de08  ldc.i4.1
0x1de09  ldarg.0
0x1de0a  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1de0f  stelem.ref
0x1de10  dup
0x1de11  ldc.i4.2
0x1de12  ldstr    asc_308B8// ","
0x1de17  stelem.ref
0x1de18  dup
0x1de19  ldc.i4.3
0x1de1a  ldarg.0
0x1de1b  callvirt instance string ShellExposureInformation::get_SupportShortcutPath()
0x1de20  stelem.ref
0x1de21  dup
0x1de22  ldc.i4.4
0x1de23  ldstr    asc_308B8// ","
0x1de28  stelem.ref
0x1de29  dup
0x1de2a  ldc.i4.5
0x1de2b  ldarg.0
0x1de2c  callvirt instance string ShellExposureInformation::get_DesktopShortcutPath()
0x1de31  stelem.ref
0x1de32  dup
0x1de33  ldc.i4.6
0x1de34  ldstr    asc_308B8// ","
0x1de39  stelem.ref
0x1de3a  dup
0x1de3b  ldc.i4.7
0x1de3c  ldarg.0
0x1de3d  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1de42  stelem.ref
0x1de43  dup
0x1de44  ldc.i4.8
0x1de45  ldstr    asc_308B8// ","
0x1de4a  stelem.ref
0x1de4b  dup
0x1de4c  ldc.i4.s 9
0x1de4e  ldarg.0
0x1de4f  callvirt instance string ShellExposureInformation::get_ApplicationRootFolderPath()
0x1de54  stelem.ref
0x1de55  call     string [mscorlib]System.String::Concat(string[])
0x1de5a  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1de5f  leave.s  loc_1DE8B
0x1de61  stloc.s  4
0x1de63  ldc.i4.4
0x1de64  ldstr    aExShortcutremo_0// "Ex_ShortcutRemovalFailure"
0x1de69  call     string System.Deployment.Application.Resources::GetString(string s)
0x1de6e  ldloc.s  4
0x1de70  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x1de75  throw
0x1de76  stloc.s  5
0x1de78  ldc.i4.4
0x1de79  ldstr    aExShortcutremo_0// "Ex_ShortcutRemovalFailure"
0x1de7e  call     string System.Deployment.Application.Resources::GetString(string s)
0x1de83  ldloc.s  5
0x1de85  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x1de8a  throw
0x1de8b  ret
```
