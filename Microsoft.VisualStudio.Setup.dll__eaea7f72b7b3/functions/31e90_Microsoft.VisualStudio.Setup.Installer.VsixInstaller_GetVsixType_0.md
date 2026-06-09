# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetVsixType_0

- ea: `0x31e90`
- end: `0x3201a`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetVsixType_0`
- size: `394`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x32cf0`
- `0x33010`

## callees

- `0xed30`
- `0x2b920`
- `0x2b940`
- `0x2b9e0`
- `0x2b9f0`
- `0x31c60`
- `0x31e90`

## string_xrefs

- `0x31f2f`: `Failed to open file: {0}.`
- `0x31f9b`: `Failed to open file: {0}, size: {1}, hash: {2}, created: {3}, modified: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x31e90  ldarg.1
0x31e91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31e96  brtrue.s loc_31EA0
0x31e98  ldarg.1
0x31e99  call     bool [mscorlib]System.IO.File::Exists(string)
0x31e9e  brtrue.s loc_31EC7
0x31ea0  ldarg.2
0x31ea1  brtrue.s loc_31EA6
0x31ea3  ldnull
0x31ea4  br.s     loc_31EAC
0x31ea6  ldarg.2
0x31ea7  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_VsixId()
0x31eac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31eb1  brtrue   loc_32016
0x31eb6  ldarg.2
0x31eb7  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_ExtensionDir()
0x31ebc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31ec1  brtrue.s loc_31EC5
0x31ec3  ldc.i4.2
0x31ec4  ret
0x31ec5  ldc.i4.1
0x31ec6  ret
0x31ec7  nop
0x31ec8  ldarg.0
0x31ec9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x31ece  ldarg.1
0x31ecf  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string)
0x31ed4  stloc.0
0x31ed5  ldarg.0
0x31ed6  ldloc.0
0x31ed7  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetVsixType(class [mscorlib]System.IO.Stream vsixStream)
0x31edc  stloc.1
0x31edd  leave    loc_32018
0x31ee2  ldloc.0
0x31ee3  brfalse.s loc_31EEB
0x31ee5  ldloc.0
0x31ee6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31eeb  endfinally
0x31eec  isinst   [mscorlib]System.Exception
0x31ef1  dup
0x31ef2  brtrue.s loc_31EF8
0x31ef4  pop
0x31ef5  ldc.i4.0
0x31ef6  br.s     loc_31F13
0x31ef8  stloc.2
0x31ef9  ldloc.2
0x31efa  isinst   [mscorlib]System.UnauthorizedAccessException
0x31eff  brtrue.s loc_31F09
0x31f01  ldloc.2
0x31f02  isinst   [mscorlib]System.IO.IOException
0x31f07  brfalse.s loc_31F0F
0x31f09  ldarg.2
0x31f0a  ldnull
0x31f0b  cgt.un
0x31f0d  br.s     loc_31F10
0x31f0f  ldc.i4.0
0x31f10  ldc.i4.0
0x31f11  cgt.un
0x31f13  endfilter
0x31f15  pop
0x31f16  ldarg.2
0x31f17  brtrue.s loc_31F1C
0x31f19  ldnull
0x31f1a  br.s     loc_31F22
0x31f1c  ldarg.2
0x31f1d  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_VsixId()
0x31f22  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31f27  brtrue.s loc_31F5A
0x31f29  ldarg.0
0x31f2a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x31f2f  ldstr    aFailedToOpenFi// "Failed to open file: {0}."
0x31f34  ldc.i4.1
0x31f35  newarr   [mscorlib]System.Object
0x31f3a  dup
0x31f3b  ldc.i4.0
0x31f3c  ldarg.1
0x31f3d  stelem.ref
0x31f3e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x31f43  ldarg.2
0x31f44  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_ExtensionDir()
0x31f49  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31f4e  brtrue.s loc_31F53
0x31f50  ldc.i4.2
0x31f51  br.s     loc_31F54
0x31f53  ldc.i4.1
0x31f54  stloc.1
0x31f55  leave    loc_32018
0x31f5a  leave    loc_32016
0x31f5f  pop
0x31f60  ldstr    aUnknown// "unknown"
0x31f65  stloc.3
0x31f66  ldarg.0
0x31f67  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IHashingService Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_HashService()
0x31f6c  ldarg.1
0x31f6d  ldc.i4.1
0x31f6e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IHashingService::GetHashOfFile(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.HashAlgorithms)
0x31f73  stloc.3
0x31f74  leave.s  loc_31F79
0x31f76  pop
0x31f77  leave.s  loc_31F79
0x31f79  ldarg.0
0x31f7a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x31f7f  ldarg.1
0x31f80  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetFileSize(string)
0x31f85  stloc.s  4
0x31f87  ldarg.0
0x31f88  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x31f8d  ldarg.1
0x31f8e  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.FileTime [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetFileTime(string)
0x31f93  stloc.s  5
0x31f95  ldarg.0
0x31f96  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x31f9b  ldstr    aFailedToOpenFi_0// "Failed to open file: {0}, size: {1}, ha"...
0x31fa0  ldc.i4.5
0x31fa1  newarr   [mscorlib]System.Object
0x31fa6  dup
0x31fa7  ldc.i4.0
0x31fa8  ldarg.1
0x31fa9  stelem.ref
0x31faa  dup
0x31fab  ldc.i4.1
0x31fac  ldloc.s  4
0x31fae  box      [mscorlib]System.Int64
0x31fb3  stelem.ref
0x31fb4  dup
0x31fb5  ldc.i4.2
0x31fb6  ldloc.3
0x31fb7  stelem.ref
0x31fb8  dup
0x31fb9  ldc.i4.3
0x31fba  ldloc.s  5
0x31fbc  ldfld    valuetype [mscorlib]System.DateTimeOffset [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.FileTime::CreationTime
0x31fc1  box      [mscorlib]System.DateTimeOffset
0x31fc6  stelem.ref
0x31fc7  dup
0x31fc8  ldc.i4.4
0x31fc9  ldloc.s  5
0x31fcb  ldfld    valuetype [mscorlib]System.DateTimeOffset [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.FileTime::LastWriteTime
0x31fd0  box      [mscorlib]System.DateTimeOffset
0x31fd5  stelem.ref
0x31fd6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x31fdb  ldarg.0
0x31fdc  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x31fe1  ldarg.0
0x31fe2  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x31fe7  ldarg.1
0x31fe8  call     void Microsoft.VisualStudio.Setup.Extensions::TryQuarantinePayloadFile(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem filesystem, class [mscorlib]System.IServiceProvider serviceProvider, string payloadFile)
0x31fed  ldarg.2
0x31fee  brtrue.s loc_31FF3
0x31ff0  ldnull
0x31ff1  br.s     loc_31FF9
0x31ff3  ldarg.2
0x31ff4  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_VsixId()
0x31ff9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31ffe  brtrue.s loc_32014
0x32000  ldarg.2
0x32001  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_ExtensionDir()
0x32006  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3200b  brtrue.s loc_32010
0x3200d  ldc.i4.2
0x3200e  br.s     loc_32011
0x32010  ldc.i4.1
0x32011  stloc.1
0x32012  leave.s  loc_32018
0x32014  rethrow
0x32016  ldc.i4.0
0x32017  ret
0x32018  ldloc.1
0x32019  ret
```
