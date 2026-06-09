# Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::TryRemoveChannelFeed

- ea: `0x52860`
- end: `0x528dd`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::TryRemoveChannelFeed`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x52400`
- `0x524d0`
- `0x528e0`

## callees

- `0xffb0`
- `0x52860`

## string_xrefs

- `0x5287a`: `Nothing to remove, channel feed {0} doesn't exist.`
- `0x528ba`: `Failed to delete channel feed at {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x52860  ldarg.0
0x52861  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::fileSystem
0x52866  ldarg.1
0x52867  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x5286c  brtrue.s loc_52890
0x5286e  ldarg.0
0x5286f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::logger
0x52874  dup
0x52875  brtrue.s loc_5287A
0x52877  pop
0x52878  br.s     loc_5288E
0x5287a  ldstr    aNothingToRemov// "Nothing to remove, channel feed {0} doe"...
0x5287f  ldc.i4.1
0x52880  newarr   [mscorlib]System.Object
0x52885  dup
0x52886  ldc.i4.0
0x52887  ldarg.1
0x52888  stelem.ref
0x52889  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5288e  ldc.i4.1
0x5288f  ret
0x52890  nop
0x52891  ldarg.0
0x52892  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::fileSystem
0x52897  ldarg.1
0x52898  ldloca.s 0
0x5289a  ldc.i4.0
0x5289b  ldc.i4.1
0x5289c  ldc.i4.2
0x5289d  ldc.i4   0x1F4
0x528a2  ldnull
0x528a3  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction)
0x528a8  pop
0x528a9  ldc.i4.1
0x528aa  stloc.0
0x528ab  leave.s  loc_528DB
0x528ad  stloc.1
0x528ae  ldarg.0
0x528af  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::logger
0x528b4  dup
0x528b5  brtrue.s loc_528BA
0x528b7  pop
0x528b8  br.s     loc_528D7
0x528ba  ldstr    aFailedToDelete_14// "Failed to delete channel feed at {0}: {"...
0x528bf  ldc.i4.2
0x528c0  newarr   [mscorlib]System.Object
0x528c5  dup
0x528c6  ldc.i4.0
0x528c7  ldarg.1
0x528c8  stelem.ref
0x528c9  dup
0x528ca  ldc.i4.1
0x528cb  ldloc.1
0x528cc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x528d1  stelem.ref
0x528d2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x528d7  leave.s  loc_528D9
0x528d9  ldc.i4.0
0x528da  ret
0x528db  ldloc.0
0x528dc  ret
```
