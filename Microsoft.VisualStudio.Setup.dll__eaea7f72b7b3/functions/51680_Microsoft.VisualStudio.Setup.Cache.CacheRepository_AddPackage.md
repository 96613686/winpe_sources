# Microsoft.VisualStudio.Setup.Cache.CacheRepository::AddPackage

- ea: `0x51680`
- end: `0x517e4`
- name: `Microsoft.VisualStudio.Setup.Cache.CacheRepository::AddPackage`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0xfe50`
- `0x51680`
- `0x51ed0`
- `0x53f20`
- `0x541a0`
- `0x55580`
- `0x571b0`
- `0x571c0`

## string_xrefs

- `0x51765`: `' deleted because of policy.`
- `0x5178e`: `' deleted because its cache property is false.`
- `0x517b2`: `Failed to delete payload '`

## pseudocode

```c

```

## disassembly

```asm
0x51680  ldarg.0
0x51681  ldarg.1
0x51682  call     instance void Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::AddPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage package)
0x51687  ldarg.0
0x51688  call     instance class Microsoft.VisualStudio.Setup.Cache.InstanceRepository Microsoft.VisualStudio.Setup.Cache.CacheRepository::get_Instance()
0x5168d  dup
0x5168e  brtrue.s loc_51693
0x51690  pop
0x51691  br.s     loc_51699
0x51693  ldarg.1
0x51694  call     instance void Microsoft.VisualStudio.Setup.Cache.InstanceRepository::AddPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage package)
0x51699  ldarg.1
0x5169a  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage
0x5169f  stloc.0
0x516a0  ldloc.0
0x516a1  brfalse  loc_517E3
0x516a6  ldarg.0
0x516a7  ldloc.0
0x516a8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype Microsoft.VisualStudio.Setup.Cache.PayloadState> Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::GetPayloads(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package)
0x516ad  call     T0x2B000259
0x516b2  stloc.1
0x516b3  ldc.i4.0
0x516b4  stloc.2
0x516b5  br       loc_517DA
0x516ba  ldloc.1
0x516bb  ldloc.2
0x516bc  ldelem   Microsoft.VisualStudio.Setup.Cache.PayloadState
0x516c1  stloc.3
0x516c2  ldloca.s 3
0x516c4  call     instance string Microsoft.VisualStudio.Setup.Cache.PayloadState::get_Path()
0x516c9  stloc.s  4
0x516cb  ldloca.s 3
0x516cd  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload Microsoft.VisualStudio.Setup.Cache.PayloadState::get_Payload()
0x516d2  dup
0x516d3  brtrue.s loc_516D9
0x516d5  pop
0x516d6  ldc.i4.1
0x516d7  br.s     loc_516DE
0x516d9  call     instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload::get_Cache()
0x516de  stloc.s  5
0x516e0  ldarg.0
0x516e1  ldfld    bool Microsoft.VisualStudio.Setup.Cache.CacheRepository::keepPayloads
0x516e6  ldloc.s  5
0x516e8  and
0x516e9  brtrue   loc_517D6
0x516ee  ldloca.s 3
0x516f0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload Microsoft.VisualStudio.Setup.Cache.PayloadState::get_Payload()
0x516f5  dup
0x516f6  brtrue.s loc_516FC
0x516f8  pop
0x516f9  ldnull
0x516fa  br.s     loc_51701
0x516fc  call     instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload::get_Url()
0x51701  ldnull
0x51702  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x51707  brfalse.s loc_51738
0x51709  ldarg.0
0x5170a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.CacheRepository::log
0x5170f  dup
0x51710  brtrue.s loc_51718
0x51712  pop
0x51713  br       loc_517D6
0x51718  ldstr    aKeepingPayload// "Keeping payload '"
0x5171d  ldloc.s  4
0x5171f  ldstr    aBecauseItHasNo// "' because it has no URL."
0x51724  call     string [mscorlib]System.String::Concat(string, string, string)
0x51729  call     T0x2B000003
0x5172e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x51733  br       loc_517D6
0x51738  nop
0x51739  ldarg.0
0x5173a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.CacheRepository::fileSystem
0x5173f  ldloc.s  4
0x51741  ldc.i4.2
0x51742  ldc.i4   0x1F4
0x51747  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileIfExists(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] int32 retryCount, [opt] int32 retryDelay)
0x5174c  brfalse.s loc_517A2
0x5174e  ldloc.s  5
0x51750  brfalse.s loc_5177B
0x51752  ldarg.0
0x51753  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.CacheRepository::log
0x51758  dup
0x51759  brtrue.s loc_5175E
0x5175b  pop
0x5175c  br.s     loc_517A2
0x5175e  ldstr    aPayload_0// "Payload '"
0x51763  ldloc.s  4
0x51765  ldstr    aDeletedBecause// "' deleted because of policy."
0x5176a  call     string [mscorlib]System.String::Concat(string, string, string)
0x5176f  call     T0x2B000003
0x51774  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x51779  br.s     loc_517A2
0x5177b  ldarg.0
0x5177c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.CacheRepository::log
0x51781  dup
0x51782  brtrue.s loc_51787
0x51784  pop
0x51785  br.s     loc_517A2
0x51787  ldstr    aPayload_0// "Payload '"
0x5178c  ldloc.s  4
0x5178e  ldstr    aDeletedBecause_0// "' deleted because its cache property is"...
0x51793  call     string [mscorlib]System.String::Concat(string, string, string)
0x51798  call     T0x2B000003
0x5179d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x517a2  leave.s  loc_517D6
0x517a4  stloc.s  6
0x517a6  ldarg.0
0x517a7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.CacheRepository::log
0x517ac  dup
0x517ad  brtrue.s loc_517B2
0x517af  pop
0x517b0  br.s     loc_517D4
0x517b2  ldstr    aFailedToDelete_13// "Failed to delete payload '"
0x517b7  ldloc.s  4
0x517b9  ldstr    asc_9868C// "': "
0x517be  ldloc.s  6
0x517c0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x517c5  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x517ca  call     T0x2B000003
0x517cf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x517d4  leave.s  loc_517D6
0x517d6  ldloc.2
0x517d7  ldc.i4.1
0x517d8  add
0x517d9  stloc.2
0x517da  ldloc.2
0x517db  ldloc.1
0x517dc  ldlen
0x517dd  conv.i4
0x517de  blt      loc_516BA
0x517e3  ret
```
