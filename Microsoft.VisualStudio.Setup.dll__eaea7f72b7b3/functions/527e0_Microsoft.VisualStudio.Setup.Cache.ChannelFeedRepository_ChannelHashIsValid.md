# Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::ChannelHashIsValid

- ea: `0x527e0`
- end: `0x52854`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::ChannelHashIsValid`
- size: `116`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x52370`
- `0x52400`
- `0x528e0`

## callees

- `0x52610`
- `0x527e0`

## string_xrefs

- `0x527f4`: `The channel feed update URI is not set. Feed directory: `
- `0x52835`: `The channel manifest's update url and hash are not equal. Expected: `

## pseudocode

```c

```

## disassembly

```asm
0x527e0  ldarg.1
0x527e1  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelFeed::get_UpdateUri()
0x527e6  brtrue.s loc_5280B
0x527e8  ldarg.0
0x527e9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::logger
0x527ee  dup
0x527ef  brtrue.s loc_527F4
0x527f1  pop
0x527f2  br.s     loc_52809
0x527f4  ldstr    aTheChannelFeed// "The channel feed update URI is not set."...
0x527f9  ldarg.2
0x527fa  call     string [mscorlib]System.String::Concat(string, string)
0x527ff  call     T0x2B000003
0x52804  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x52809  ldc.i4.0
0x5280a  ret
0x5280b  ldarg.0
0x5280c  ldarg.1
0x5280d  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelFeed::get_UpdateUri()
0x52812  call     instance string Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::GetHashValue(class [System]System.Uri uri)
0x52817  stloc.0
0x52818  ldarg.2
0x52819  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x5281e  stloc.1
0x5281f  ldloc.0
0x52820  ldloc.1
0x52821  ldc.i4.5
0x52822  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x52827  brtrue.s loc_52852
0x52829  ldarg.0
0x5282a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelFeedRepository::logger
0x5282f  dup
0x52830  brtrue.s loc_52835
0x52832  pop
0x52833  br.s     loc_52850
0x52835  ldstr    aTheChannelMani_0// "The channel manifest's update url and h"...
0x5283a  ldloc.0
0x5283b  ldstr    aActual// ", Actual: "
0x52840  ldloc.1
0x52841  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x52846  call     T0x2B000003
0x5284b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x52850  ldc.i4.0
0x52851  ret
0x52852  ldc.i4.1
0x52853  ret
```
