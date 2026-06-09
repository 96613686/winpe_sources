# Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::GenerateResultFile

- ea: `0x1b10`
- end: `0x1b70`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::GenerateResultFile`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3c10`
- `0x5530`

## callees

- `0x18b0`
- `0x18e0`
- `0x1920`
- `0x19b0`
- `0x1b10`

## pseudocode

```c

```

## disassembly

```asm
0x1b10  ldarg.0
0x1b11  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_IsInitialized()
0x1b16  brfalse.s loc_1B6F
0x1b18  ldarg.0
0x1b19  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePrefix()
0x1b1e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b23  brtrue.s loc_1B6F
0x1b25  ldarg.0
0x1b26  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePath()
0x1b2b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b30  brtrue.s loc_1B6F
0x1b32  ldstr    a0Result1Log// "{0}_result_{1}.log"
0x1b37  ldarg.0
0x1b38  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePrefix()
0x1b3d  ldarg.1
0x1b3e  box      Microsoft.VisualStudio.Setup.OperationResult
0x1b43  call     string [mscorlib]System.String::Format(string, object, object)
0x1b48  stloc.0
0x1b49  ldarg.0
0x1b4a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_FileSystem()
0x1b4f  ldarg.0
0x1b50  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePath()
0x1b55  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1b5a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x1b5f  ldarg.0
0x1b60  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_FileSystem()
0x1b65  ldloc.0
0x1b66  ldc.i4.2
0x1b67  ldc.i4.3
0x1b68  ldc.i4.0
0x1b69  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateFile(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileMode, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAccess, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileShare)
0x1b6e  pop
0x1b6f  ret
```
