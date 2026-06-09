# Microsoft.VisualStudio.Setup.Activities.DeleteSwidTag::Invoke

- ea: `0x5c4e0`
- end: `0x5c552`
- name: `Microsoft.VisualStudio.Setup.Activities.DeleteSwidTag::Invoke`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0xfe50`
- `0x100c0`
- `0x596d0`
- `0x596f0`
- `0x5c4e0`
- `0x60910`

## string_xrefs

- `0x5c513`: `Removed SWID tag: {0}`
- `0x5c53d`: `Failed to remove SWID tag: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5c4e0  ldarga.s 1
0x5c4e2  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x5c4e7  ldarg.0
0x5c4e8  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5c4ed  ldc.i4.1
0x5c4ee  call     T0x2B00000C
0x5c4f3  stloc.0
0x5c4f4  ldarg.0
0x5c4f5  ldloc.0
0x5c4f6  ldloca.s 2
0x5c4f8  call     instance string Microsoft.VisualStudio.Setup.Activities.SwidTagActivity::GetPath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, [out] string& directory)
0x5c4fd  stloc.1
0x5c4fe  ldloc.0
0x5c4ff  ldloc.1
0x5c500  ldc.i4.2
0x5c501  ldc.i4   0x1F4
0x5c506  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileIfExists(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] int32 retryCount, [opt] int32 retryDelay)
0x5c50b  brfalse.s loc_5C537
0x5c50d  ldarg.0
0x5c50e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5c513  ldstr    aRemovedSwidTag// "Removed SWID tag: {0}"
0x5c518  ldc.i4.1
0x5c519  newarr   [mscorlib]System.Object
0x5c51e  dup
0x5c51f  ldc.i4.0
0x5c520  ldloc.1
0x5c521  stelem.ref
0x5c522  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5c527  ldloc.0
0x5c528  ldloc.2
0x5c529  ldc.i4.1
0x5c52a  ldc.i4.2
0x5c52b  ldc.i4   0x1F4
0x5c530  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteEmptyAncestorsWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] bool rebootOK, [opt] int32 retryCount, [opt] int32 retryDelay)
0x5c535  pop
0x5c536  ret
0x5c537  ldarg.0
0x5c538  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5c53d  ldstr    aFailedToRemove_1// "Failed to remove SWID tag: {0}"
0x5c542  ldc.i4.1
0x5c543  newarr   [mscorlib]System.Object
0x5c548  dup
0x5c549  ldc.i4.0
0x5c54a  ldloc.1
0x5c54b  stelem.ref
0x5c54c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5c551  ret
```
