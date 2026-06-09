# Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::GetInstallerServicePath

- ea: `0x1ca0`
- end: `0x1cbb`
- name: `Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::GetInstallerServicePath`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1c30`

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  ldarg.0
0x1ca1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::fileSystem
0x1ca6  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x1cab  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerSubDirectory
0x1cb0  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerFileName
0x1cb5  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x1cba  ret
```
