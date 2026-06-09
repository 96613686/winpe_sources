# Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::AddChannelFeed

- ea: `0x52400`
- end: `0x524cb`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::AddChannelFeed`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x52400`
- `0x52580`
- `0x52630`
- `0x52650`
- `0x52750`
- `0x527e0`
- `0x52860`

## string_xrefs

- `0x52401`: `feedUri`
- `0x5240c`: `feedFilePath`
- `0x52451`: `Failed to read the new channel feed {0}`

## pseudocode

```c

```

## disassembly

```asm
0x52400  ldarg.1
0x52401  ldstr    aFeeduri// "feedUri"
0x52406  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5240b  ldarg.2
0x5240c  ldstr    aFeedfilepath// "feedFilePath"
0x52411  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x52416  ldarg.0
0x52417  ldarg.1
0x52418  call     instance string Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::GetChannelFeedRoot(class [System]System.Uri uri)
0x5241d  stloc.0
0x5241e  ldarg.0
0x5241f  ldloc.0
0x52420  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelFeed Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::GetExistingChannelFeed(string)
0x52425  stloc.1
0x52426  ldloc.1
0x52427  brfalse.s loc_52482
0x52429  ldarg.0
0x5242a  ldloc.1
0x5242b  ldloc.0
0x5242c  call     instance bool Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::ChannelHashIsValid(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelFeed feed, string feedDirectory)
0x52431  brfalse.s loc_52482
0x52433  ldloc.1
0x52434  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelFeed::get_Version()
0x52439  stloc.2
0x5243a  ldarg.0
0x5243b  ldarg.2
0x5243c  ldloca.s 3
0x5243e  call     instance bool Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::TryReadChannelFeed(string path, [out] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelFeed& feed)
0x52443  brtrue.s loc_52467
0x52445  ldarg.0
0x52446  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::logger
0x5244b  dup
0x5244c  brtrue.s loc_52451
0x5244e  pop
0x5244f  br.s     loc_52465
0x52451  ldstr    aFailedToReadTh_0// "Failed to read the new channel feed {0}"
0x52456  ldc.i4.1
0x52457  newarr   [mscorlib]System.Object
0x5245c  dup
0x5245d  ldc.i4.0
0x5245e  ldarg.1
0x5245f  stelem.ref
0x52460  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x52465  ldc.i4.0
0x52466  ret
0x52467  ldloc.3
0x52468  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelFeed::get_Version()
0x5246d  stloc.s  4
0x5246f  ldloc.s  4
0x52471  brfalse.s loc_52482
0x52473  ldloc.2
0x52474  brfalse.s loc_52482
0x52476  ldloc.s  4
0x52478  ldloc.2
0x52479  call     bool [mscorlib]System.Version::op_LessThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x5247e  brfalse.s loc_52482
0x52480  ldc.i4.0
0x52481  ret
0x52482  nop
0x52483  ldarg.0
0x52484  ldloc.0
0x52485  ldarg.1
0x52486  ldarg.2
0x52487  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::AddChannelFeed(string channelRoot, class [System]System.Uri feedUri, string feedFilePath)
0x5248c  ldc.i4.1
0x5248d  stloc.s  5
0x5248f  leave.s  loc_524C8
0x52491  stloc.s  6
0x52493  ldarg.0
0x52494  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::logger
0x52499  dup
0x5249a  brtrue.s loc_5249F
0x5249c  pop
0x5249d  br.s     loc_524BB
0x5249f  ldstr    aFailedToAddCha// "Failed to add channel feed {0}: {1}"
0x524a4  ldarg.1
0x524a5  ldloc.s  6
0x524a7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x524ac  call     string [mscorlib]System.String::Format(string, object, object)
0x524b1  call     T0x2B000003
0x524b6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x524bb  ldarg.0
0x524bc  ldloc.0
0x524bd  call     instance bool Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::TryRemoveChannelFeed(string directory)
0x524c2  pop
0x524c3  ldc.i4.0
0x524c4  stloc.s  5
0x524c6  leave.s  loc_524C8
0x524c8  ldloc.s  5
0x524ca  ret
```
