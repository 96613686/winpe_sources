# Microsoft.VisualStudio.Setup.Cache.CustomChannelRepository::ReadBaseInformationFromRegistry

- ea: `0x53ce0`
- end: `0x53de4`
- name: `Microsoft.VisualStudio.Setup.Cache.CustomChannelRepository::ReadBaseInformationFromRegistry`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x797f0`

## callees

- `0xee70`
- `0xeee0`
- `0x53ce0`

## string_xrefs

- `0x53d84`: `Failed to parse channelUri string `
- `0x53dbb`: `Failed to read channel summary definition for channel `

## pseudocode

```c

```

## disassembly

```asm
0x53ce0  ldarg.1
0x53ce1  ldarg.2
0x53ce2  ldc.i4.0
0x53ce3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x53ce8  stloc.0
0x53ce9  ldloc.0
0x53cea  ldsfld   string Microsoft.VisualStudio.Setup.Cache.CustomChannelRepository::ChannelUriKeyValue
0x53cef  ldnull
0x53cf0  call     T0x2B000269
0x53cf5  stloc.1
0x53cf6  ldloc.1
0x53cf7  ldc.i4.1
0x53cf8  ldloca.s 2
0x53cfa  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x53cff  brfalse.s loc_53D78
0x53d01  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary::.ctor()
0x53d06  dup
0x53d07  ldarg.2
0x53d08  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary::set_ChannelId(string)
0x53d0d  dup
0x53d0e  ldloc.2
0x53d0f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary::set_ChannelUri(class [System]System.Uri)
0x53d14  dup
0x53d15  ldloc.2
0x53d16  call     bool Microsoft.VisualStudio.Setup.Extensions::IsLayoutPath(class [System]System.Uri uri)
0x53d1b  brtrue.s loc_53D28
0x53d1d  ldloc.2
0x53d1e  call     bool Microsoft.VisualStudio.Setup.Extensions::IsWebHostedLayout(class [System]System.Uri uri)
0x53d23  brtrue.s loc_53D28
0x53d25  ldc.i4.2
0x53d26  br.s     loc_53D29
0x53d28  ldc.i4.3
0x53d29  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary::set_Type(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummaryType)
0x53d2e  ldloc.0
0x53d2f  ldsfld   string Microsoft.VisualStudio.Setup.Cache.CustomChannelRepository::ChannelDescriptionKeyValue
0x53d34  ldnull
0x53d35  call     T0x2B000269
0x53d3a  stloc.3
0x53d3b  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::.ctor()
0x53d40  dup
0x53d41  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x53d46  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x53d4b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::set_Language(string)
0x53d50  dup
0x53d51  ldarg.2
0x53d52  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::set_Title(string)
0x53d57  dup
0x53d58  ldarg.2
0x53d59  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::set_ChannelSuffix(string)
0x53d5e  dup
0x53d5f  ldloc.3
0x53d60  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::set_Description(string)
0x53d65  stloc.s  4
0x53d67  dup
0x53d68  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary::get_LocalizedResources()
0x53d6d  ldloc.s  4
0x53d6f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource>::Add(var<u1>)
0x53d74  stloc.s  5
0x53d76  leave.s  loc_53DE1
0x53d78  ldarg.0
0x53d79  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.CustomChannelRepository::logger
0x53d7e  dup
0x53d7f  brtrue.s loc_53D84
0x53d81  pop
0x53d82  br.s     loc_53D9E
0x53d84  ldstr    aFailedToParseC// "Failed to parse channelUri string "
0x53d89  ldloc.1
0x53d8a  ldstr    aSkippingThisCh// ". Skipping this channel summary definit"...
0x53d8f  call     string [mscorlib]System.String::Concat(string, string, string)
0x53d94  call     T0x2B000003
0x53d99  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x53d9e  ldnull
0x53d9f  stloc.s  5
0x53da1  leave.s  loc_53DE1
0x53da3  ldloc.0
0x53da4  brfalse.s loc_53DAC
0x53da6  ldloc.0
0x53da7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x53dac  endfinally
0x53dad  stloc.s  6
0x53daf  ldarg.0
0x53db0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.CustomChannelRepository::logger
0x53db5  dup
0x53db6  brtrue.s loc_53DBB
0x53db8  pop
0x53db9  br.s     loc_53DDC
0x53dbb  ldstr    aFailedToReadCh// "Failed to read channel summary definiti"...
0x53dc0  ldarg.2
0x53dc1  ldstr    asc_82BA2// ": "
0x53dc6  ldloc.s  6
0x53dc8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x53dcd  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x53dd2  call     T0x2B000003
0x53dd7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x53ddc  ldnull
0x53ddd  stloc.s  5
0x53ddf  leave.s  loc_53DE1
0x53de1  ldloc.s  5
0x53de3  ret
```
