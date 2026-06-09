# Microsoft.VisualStudio.Setup.Extensions::TryQuarantinePayloadFile

- ea: `0xed30`
- end: `0xedc4`
- name: `Microsoft.VisualStudio.Setup.Extensions::TryQuarantinePayloadFile`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x31e90`
- `0x61a30`

## callees

- `0xed30`
- `0xfcf0`

## string_xrefs

- `0xed67`: `Copying file from '{0}' to '{1}'`
- `0xeda0`: `Failed to copy '{0}' to '{1}': {2)`

## pseudocode

```c

```

## disassembly

```asm
0xed30  ldarg.1
0xed31  ldc.i4.0
0xed32  call     T0x2B000001
0xed37  stloc.0
0xed38  ldarg.0
0xed39  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_TemporaryDirectory()
0xed3e  ldstr    aVsQuarantine// "VS\\Quarantine"
0xed43  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xed48  ldarg.2
0xed49  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xed4e  call     string [mscorlib]System.IO.Path::GetFileName(string)
0xed53  ldarg.2
0xed54  call     string [mscorlib]System.IO.Path::GetFileName(string)
0xed59  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xed5e  stloc.1
0xed5f  ldloc.1
0xed60  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xed65  stloc.2
0xed66  ldloc.0
0xed67  ldstr    aCopyingFileFro// "Copying file from '{0}' to '{1}'"
0xed6c  ldc.i4.2
0xed6d  newarr   [mscorlib]System.Object
0xed72  dup
0xed73  ldc.i4.0
0xed74  ldarg.2
0xed75  stelem.ref
0xed76  dup
0xed77  ldc.i4.1
0xed78  ldloc.2
0xed79  stelem.ref
0xed7a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xed7f  ldarg.0
0xed80  ldloc.2
0xed81  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xed86  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0xed8b  ldarg.0
0xed8c  ldarg.2
0xed8d  ldloc.2
0xed8e  ldc.i4.2
0xed8f  ldc.i4   0x1F4
0xed94  call     void Microsoft.VisualStudio.Setup.Extensions::CopyFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string source, string destination, [opt] int32 retryCount, [opt] int32 retryDelay)
0xed99  leave.s  loc_EDC3
0xed9b  stloc.3
0xed9c  ldloc.0
0xed9d  brfalse.s loc_EDC1
0xed9f  ldloc.0
0xeda0  ldstr    aFailedToCopy0T// "Failed to copy '{0}' to '{1}': {2)"
0xeda5  ldc.i4.3
0xeda6  newarr   [mscorlib]System.Object
0xedab  dup
0xedac  ldc.i4.0
0xedad  ldarg.2
0xedae  stelem.ref
0xedaf  dup
0xedb0  ldc.i4.1
0xedb1  ldloc.2
0xedb2  stelem.ref
0xedb3  dup
0xedb4  ldc.i4.2
0xedb5  ldloc.3
0xedb6  callvirt instance string [mscorlib]System.Exception::get_Message()
0xedbb  stelem.ref
0xedbc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xedc1  leave.s  loc_EDC3
0xedc3  ret
```
