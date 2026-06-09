# Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::GetCustomChannelInfo

- ea: `0x566f0`
- end: `0x5680d`
- name: `Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::GetCustomChannelInfo`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x56810`
- `0x56840`

## callees

- `0x1b090`
- `0x566f0`
- `0x568c0`
- `0x568e0`
- `0x56af0`
- `0x56c40`

## string_xrefs

- `0x5677d`: `Failed to read layout channel manifest: `
- `0x567c2`: `Layout channel uri file does not exist: `
- `0x567ec`: `Failed to read layout channel: `

## pseudocode

```c

```

## disassembly

```asm
0x566f0  ldarg.1
0x566f1  brfalse.s loc_566FB
0x566f3  ldarg.1
0x566f4  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary::get_ChannelUri()
0x566f9  brtrue.s loc_56702
0x566fb  ldnull
0x566fc  stloc.1
0x566fd  leave    loc_5680B
0x56702  ldarg.0
0x56703  ldarg.1
0x56704  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary::get_ChannelUri()
0x56709  ldloca.s 0
0x5670b  callvirt instance bool Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::IsChannelUriValid(class [System]System.Uri channelUri, [out] string& channelUriString)
0x56710  brfalse  loc_567B6
0x56715  ldarg.0
0x56716  ldloc.0
0x56717  call     instance class Microsoft.VisualStudio.Setup.ResponseFile Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::ReadResponseFile(string)
0x5671c  stloc.2
0x5671d  ldloc.2
0x5671e  brfalse.s loc_5672D
0x56720  ldloc.2
0x56721  callvirt instance string Microsoft.VisualStudio.Setup.ResponseFile::get_ProductId()
0x56726  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x5672b  brfalse.s loc_5674F
0x5672d  ldarg.0
0x5672e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::logger
0x56733  dup
0x56734  brtrue.s loc_56739
0x56736  pop
0x56737  br.s     loc_56748
0x56739  ldstr    aLayoutChannelD// "Layout channel doesn't contain valid re"...
0x5673e  call     T0x2B000003
0x56743  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x56748  ldnull
0x56749  stloc.1
0x5674a  leave    loc_5680B
0x5674f  ldc.i4.1
0x56750  newarr   [mscorlib]System.String
0x56755  dup
0x56756  ldc.i4.0
0x56757  ldloc.2
0x56758  callvirt instance string Microsoft.VisualStudio.Setup.ResponseFile::get_ProductId()
0x5675d  stelem.ref
0x5675e  stloc.3
0x5675f  ldarg.0
0x56760  ldarg.1
0x56761  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary::get_ChannelUri()
0x56766  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::GetChannelManifest(class [System]System.Uri)
0x5676b  stloc.s  4
0x5676d  ldloc.s  4
0x5676f  brtrue.s loc_5679B
0x56771  ldarg.0
0x56772  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::logger
0x56777  dup
0x56778  brtrue.s loc_5677D
0x5677a  pop
0x5677b  br.s     loc_56797
0x5677d  ldstr    aFailedToReadLa// "Failed to read layout channel manifest:"...
0x56782  ldloc.0
0x56783  ldstr    asc_80DBA// "."
0x56788  call     string [mscorlib]System.String::Concat(string, string, string)
0x5678d  call     T0x2B000003
0x56792  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x56797  ldnull
0x56798  stloc.1
0x56799  leave.s  loc_5680B
0x5679b  ldloc.s  4
0x5679d  ldloc.0
0x5679e  newobj   instance void [System]System.Uri::.ctor(string)
0x567a3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::set_UpdateUri(class [System]System.Uri)
0x567a8  ldarg.0
0x567a9  ldarg.1
0x567aa  ldloc.2
0x567ab  ldloc.3
0x567ac  ldloc.s  4
0x567ae  call     instance class Microsoft.VisualStudio.Setup.Cache.CustomChannelInfo Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::GetChannelInfo(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelSummary channelSummary, class Microsoft.VisualStudio.Setup.ResponseFile responseFile, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> supportedProductIds, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest channelManifest)
0x567b3  stloc.1
0x567b4  leave.s  loc_5680B
0x567b6  ldarg.0
0x567b7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::logger
0x567bc  dup
0x567bd  brtrue.s loc_567C2
0x567bf  pop
0x567c0  br.s     loc_567DC
0x567c2  ldstr    aLayoutChannelU// "Layout channel uri file does not exist:"...
0x567c7  ldloc.0
0x567c8  ldstr    asc_80DBA// "."
0x567cd  call     string [mscorlib]System.String::Concat(string, string, string)
0x567d2  call     T0x2B000003
0x567d7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x567dc  leave.s  loc_56809
0x567de  stloc.s  5
0x567e0  ldarg.0
0x567e1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::logger
0x567e6  dup
0x567e7  brtrue.s loc_567EC
0x567e9  pop
0x567ea  br.s     loc_56807
0x567ec  ldstr    aFailedToReadLa_0// "Failed to read layout channel: "
0x567f1  ldloc.s  5
0x567f3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x567f8  call     string [mscorlib]System.String::Concat(string, string)
0x567fd  call     T0x2B000003
0x56802  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x56807  leave.s  loc_56809
0x56809  ldnull
0x5680a  ret
0x5680b  ldloc.1
0x5680c  ret
```
