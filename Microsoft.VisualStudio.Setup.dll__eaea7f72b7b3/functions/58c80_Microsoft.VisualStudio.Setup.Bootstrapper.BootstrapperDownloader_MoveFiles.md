# Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::MoveFiles

- ea: `0x58c80`
- end: `0x58d08`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::MoveFiles`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x7ade0`

## callees

- `0xfda0`
- `0x588d0`
- `0x58920`
- `0x589e0`
- `0x58a00`
- `0x58c80`

## string_xrefs

- `0x58c95`: `Moving temporary bootstrapper files to: {0}`
- `0x58ce9`: `Failed to move temporary bootstrapper files: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x58c80  ldarg.0
0x58c81  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_FileSystem()
0x58c86  ldarg.0
0x58c87  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_RootDirectory()
0x58c8c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x58c91  ldarg.1
0x58c92  brfalse.s loc_58CAE
0x58c94  ldarg.1
0x58c95  ldstr    aMovingTemporar// "Moving temporary bootstrapper files to:"...
0x58c9a  ldc.i4.1
0x58c9b  newarr   [mscorlib]System.Object
0x58ca0  dup
0x58ca1  ldc.i4.0
0x58ca2  ldarg.0
0x58ca3  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_RootDirectory()
0x58ca8  stelem.ref
0x58ca9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x58cae  ldarg.0
0x58caf  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_FileSystem()
0x58cb4  ldarg.2
0x58cb5  ldarg.0
0x58cb6  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_BootstrapperPath()
0x58cbb  ldc.i4.1
0x58cbc  ldc.i4.2
0x58cbd  ldc.i4   0x1F4
0x58cc2  call     void Microsoft.VisualStudio.Setup.Extensions::MoveFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string source, string destination, [opt] bool replace, [opt] int32 retryCount, [opt] int32 retryDelay)
0x58cc7  ldarg.0
0x58cc8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_FileSystem()
0x58ccd  ldarg.3
0x58cce  ldarg.0
0x58ccf  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_InstallerPath()
0x58cd4  ldc.i4.1
0x58cd5  ldc.i4.2
0x58cd6  ldc.i4   0x1F4
0x58cdb  call     void Microsoft.VisualStudio.Setup.Extensions::MoveFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string source, string destination, [opt] bool replace, [opt] int32 retryCount, [opt] int32 retryDelay)
0x58ce0  ldc.i4.1
0x58ce1  stloc.0
0x58ce2  leave.s  loc_58D06
0x58ce4  stloc.1
0x58ce5  ldarg.1
0x58ce6  brfalse.s loc_58D02
0x58ce8  ldarg.1
0x58ce9  ldstr    aFailedToMoveTe// "Failed to move temporary bootstrapper f"...
0x58cee  ldc.i4.1
0x58cef  newarr   [mscorlib]System.Object
0x58cf4  dup
0x58cf5  ldc.i4.0
0x58cf6  ldloc.1
0x58cf7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x58cfc  stelem.ref
0x58cfd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x58d02  ldc.i4.0
0x58d03  stloc.0
0x58d04  leave.s  loc_58D06
0x58d06  ldloc.0
0x58d07  ret
```
