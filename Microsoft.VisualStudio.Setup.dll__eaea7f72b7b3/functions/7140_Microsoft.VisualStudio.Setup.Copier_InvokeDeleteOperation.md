# Microsoft.VisualStudio.Setup.Copier::InvokeDeleteOperation

- ea: `0x7140`
- end: `0x71d7`
- name: `Microsoft.VisualStudio.Setup.Copier::InvokeDeleteOperation`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x7010`

## callees

- `0x7140`
- `0xfed0`

## string_xrefs

- `0x718d`: `A reboot is required to delete file: {0}`
- `0x71b4`: `Failed to delete file: {0}, error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x7140  ldarg.0
0x7141  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Copier::logger
0x7146  dup
0x7147  brtrue.s loc_714C
0x7149  pop
0x714a  br.s     loc_7160
0x714c  ldstr    aDeletingFile0// "Deleting file: {0}"
0x7151  ldc.i4.1
0x7152  newarr   [mscorlib]System.Object
0x7157  dup
0x7158  ldc.i4.0
0x7159  ldarg.1
0x715a  stelem.ref
0x715b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7160  nop
0x7161  ldarg.0
0x7162  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Copier::fileSystem
0x7167  ldarg.1
0x7168  ldloca.s 0
0x716a  ldc.i4.1
0x716b  ldc.i4.2
0x716c  ldc.i4   0x1F4
0x7171  ldnull
0x7172  ldnull
0x7173  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x7178  brfalse.s loc_717E
0x717a  ldc.i4.1
0x717b  stloc.1
0x717c  leave.s  loc_71D5
0x717e  ldloc.0
0x717f  brfalse.s loc_71A5
0x7181  ldarg.0
0x7182  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Copier::logger
0x7187  dup
0x7188  brtrue.s loc_718D
0x718a  pop
0x718b  br.s     loc_71A1
0x718d  ldstr    aARebootIsRequi// "A reboot is required to delete file: {0"...
0x7192  ldc.i4.1
0x7193  newarr   [mscorlib]System.Object
0x7198  dup
0x7199  ldc.i4.0
0x719a  ldarg.1
0x719b  stelem.ref
0x719c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x71a1  ldc.i4.1
0x71a2  stloc.1
0x71a3  leave.s  loc_71D5
0x71a5  leave.s  loc_71D3
0x71a7  stloc.2
0x71a8  ldarg.0
0x71a9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Copier::logger
0x71ae  dup
0x71af  brtrue.s loc_71B4
0x71b1  pop
0x71b2  br.s     loc_71D1
0x71b4  ldstr    aFailedToDelete_1// "Failed to delete file: {0}, error: {1}"
0x71b9  ldc.i4.2
0x71ba  newarr   [mscorlib]System.Object
0x71bf  dup
0x71c0  ldc.i4.0
0x71c1  ldarg.1
0x71c2  stelem.ref
0x71c3  dup
0x71c4  ldc.i4.1
0x71c5  ldloc.2
0x71c6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x71cb  stelem.ref
0x71cc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x71d1  leave.s  loc_71D3
0x71d3  ldc.i4.0
0x71d4  ret
0x71d5  ldloc.1
0x71d6  ret
```
