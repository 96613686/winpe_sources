# Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::CreatePublishedChannelNode

- ea: `0x50220`
- end: `0x504d2`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::CreatePublishedChannelNode`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x500e0`

## callees

- `0x36430`
- `0x364e0`
- `0x39550`
- `0x39570`
- `0x4e9e0`
- `0x4e9f0`
- `0x4ea00`
- `0x4ea10`
- `0x4ea90`
- `0x4ecc0`
- `0x4fe70`
- `0x4fec0`
- `0x4fef0`
- `0x50220`
- `0x50610`
- `0x50870`
- `0x50970`
- `0x50a00`
- `0x50a60`
- `0x50ab0`
- `0x512a0`
- `0x512b0`
- `0x512c0`
- `0x519f0`
- `0x52010`
- `0x523d0`

## string_xrefs

- `0x50440`: `ConfigFolder:Initialize: adding `

## pseudocode

```c

```

## disassembly

```asm
0x50220  ldnull
0x50221  stloc.1
0x50222  ldnull
0x50223  stloc.2
0x50224  ldnull
0x50225  stloc.3
0x50226  ldarg.0
0x50227  ldsfld   string [mscorlib]System.String::Empty
0x5022c  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::GetPublishersWithChannels(string partialPublisherNames)
0x50231  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x50236  stloc.s  7
0x50238  br       loc_504AE
0x5023d  ldloc.s  7
0x5023f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x50244  castclass Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher
0x50249  stloc.s  8
0x5024b  ldnull
0x5024c  stloc.2
0x5024d  ldnull
0x5024e  stloc.3
0x5024f  ldnull
0x50250  stloc.1
0x50251  ldloc.s  8
0x50253  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_LocalizedPublisherName()
0x50258  ldloca.s 4
0x5025a  ldloca.s 6
0x5025c  ldloca.s 5
0x5025e  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::ParsePublisherName(string publisherName, [out] string& company, [out] string& productName, [out] string& publisher)
0x50263  brfalse.s loc_50284
0x50265  ldarg.0
0x50266  ldarg.2
0x50267  ldloc.s  8
0x50269  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_Identifier()
0x5026e  ldloc.s  4
0x50270  ldloc.s  6
0x50272  ldloc.s  5
0x50274  ldloca.s 2
0x50276  ldloca.s 3
0x50278  ldloca.s 1
0x5027a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::BuildPublisherNode(bool refreshRequired, string publisherIdentifier, string companyName, string productName, string publisherName, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& companyFolder, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& productFolder, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& publisherFolder)
0x5027f  br       loc_50305
0x50284  ldloc.s  8
0x50286  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_Identifier()
0x5028b  ldloca.s 4
0x5028d  ldloca.s 6
0x5028f  ldloca.s 5
0x50291  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::ParsePublisherName(string publisherName, [out] string& company, [out] string& productName, [out] string& publisher)
0x50296  brfalse.s loc_502B4
0x50298  ldarg.0
0x50299  ldarg.2
0x5029a  ldloc.s  8
0x5029c  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_Identifier()
0x502a1  ldloc.s  4
0x502a3  ldloc.s  6
0x502a5  ldloc.s  5
0x502a7  ldloca.s 2
0x502a9  ldloca.s 3
0x502ab  ldloca.s 1
0x502ad  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::BuildPublisherNode(bool refreshRequired, string publisherIdentifier, string companyName, string productName, string publisherName, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& companyFolder, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& productFolder, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& publisherFolder)
0x502b2  br.s     loc_50305
0x502b4  ldloc.s  8
0x502b6  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_LocalizedPublisherName()
0x502bb  stloc.s  9
0x502bd  ldarg.2
0x502be  brfalse.s loc_502DA
0x502c0  ldarg.0
0x502c1  ldloc.s  8
0x502c3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_Identifier()
0x502c8  ldloca.s 9
0x502ca  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::GetChildProductFolder(string identifier, string& publisherName)
0x502cf  stloc.1
0x502d0  ldloc.1
0x502d1  brfalse.s loc_502DA
0x502d3  ldloc.1
0x502d4  ldc.i4.0
0x502d5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::set_ConfigDeleted(bool value)
0x502da  ldloc.1
0x502db  brtrue.s loc_50305
0x502dd  ldc.i4.8
0x502de  ldloc.s  9
0x502e0  ldarg.0
0x502e1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x502e6  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ConfigType type, string path, class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext ctx)
0x502eb  stloc.1
0x502ec  ldloc.1
0x502ed  ldloc.s  8
0x502ef  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_Identifier()
0x502f4  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::set_Path(string value)
0x502f9  ldloc.1
0x502fa  ldloc.1
0x502fb  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Path()
0x50300  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::set_HierarchyPath(string value)
0x50305  ldloc.s  8
0x50307  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_ChannelReferences()
0x5030c  brfalse  loc_50430
0x50311  ldloc.s  8
0x50313  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_ChannelReferences()
0x50318  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x5031d  stloc.s  0xB
0x5031f  br       loc_5040D
0x50324  ldloc.s  0xB
0x50326  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5032b  castclass Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase
0x50330  stloc.s  0xC
0x50332  ldloc.s  0xC
0x50334  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_ChannelPath()
0x50339  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::IsGlobalChannel(string channel)
0x5033e  brtrue   loc_5040D
0x50343  ldloc.s  0xC
0x50345  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_Flag()
0x5034a  ldc.i4.1
0x5034b  and
0x5034c  brtrue   loc_5040D
0x50351  ldloc.1
0x50352  brfalse  loc_5040D
0x50357  ldnull
0x50358  stloc.0
0x50359  ldloc.s  8
0x5035b  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_LocalizedPublisherName()
0x50360  ldloc.s  8
0x50362  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_Identifier()
0x50367  ldloc.s  0xC
0x50369  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_Name()
0x5036e  call     string Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetChannelDisplayName(string publisherName, string nonLocalizedPublisherName, string channelPath)
0x50373  stloc.s  0xA
0x50375  ldarg.2
0x50376  brfalse.s loc_50395
0x50378  ldloc.1
0x50379  ldloc.s  0xC
0x5037b  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_ChannelPath()
0x50380  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::GetChildItemByPath(string configPath)
0x50385  isinst   Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig
0x5038a  stloc.0
0x5038b  ldloc.0
0x5038c  brfalse.s loc_50395
0x5038e  ldloc.0
0x5038f  ldc.i4.0
0x50390  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::set_ConfigDeleted(bool value)
0x50395  ldloc.0
0x50396  brtrue.s loc_503EE
0x50398  ldarg.0
0x50399  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x5039e  ldloc.s  0xC
0x503a0  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_ChannelPath()
0x503a5  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetChannel(string channelPath)
0x503aa  stloc.0
0x503ab  ldloc.0
0x503ac  ldloc.1
0x503ad  ldloc.s  0xC
0x503af  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_ChannelPath()
0x503b4  ldloc.s  0xA
0x503b6  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::GetUniqueChannelDisplayName(string channelPath, string channelNodeName)
0x503bb  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::set_Name(string value)
0x503c0  ldloc.0
0x503c1  ldloc.s  0xC
0x503c3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_Name()
0x503c8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::set_LocalizedDisplayName(string value)
0x503cd  ldloc.1
0x503ce  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x503d3  ldloc.0
0x503d4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x503d9  pop
0x503da  ldarg.0
0x503db  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x503e0  brfalse.s loc_503EE
0x503e2  ldarg.0
0x503e3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x503e8  ldloc.0
0x503e9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::SetChannel(class Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig ch)
0x503ee  ldarg.1
0x503ef  ldind.ref
0x503f0  ldloc.s  0xC
0x503f2  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_ChannelPath()
0x503f7  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x503fc  brtrue.s loc_5040D
0x503fe  ldarg.1
0x503ff  ldind.ref
0x50400  ldloc.s  0xC
0x50402  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_ChannelPath()
0x50407  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5040c  pop
0x5040d  ldloc.s  0xB
0x5040f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x50414  brtrue   loc_50324
0x50419  leave.s  loc_50430
0x5041b  ldloc.s  0xB
0x5041d  isinst   [mscorlib]System.IDisposable
0x50422  stloc.s  0xD
0x50424  ldloc.s  0xD
0x50426  brfalse.s loc_5042F
0x50428  ldloc.s  0xD
0x5042a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5042f  endfinally
0x50430  ldloc.2
0x50431  brtrue.s loc_50457
0x50433  ldarg.0
0x50434  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x50439  ldloc.1
0x5043a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5043f  pop
0x50440  ldstr    aConfigfolderIn// "ConfigFolder:Initialize: adding "
0x50445  ldloc.1
0x50446  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Name()
0x5044b  call     string [mscorlib]System.String::Concat(string, string)
0x50450  call     void [System]System.Diagnostics.Trace::WriteLine(string)
0x50455  br.s     loc_504AE
0x50457  ldloc.3
0x50458  brfalse.s loc_50475
0x5045a  ldloc.3
0x5045b  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x50460  ldloc.1
0x50461  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x50466  brtrue.s loc_50475
0x50468  ldloc.3
0x50469  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x5046e  ldloc.1
0x5046f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x50474  pop
0x50475  ldloc.2
0x50476  brfalse.s loc_50493
0x50478  ldloc.2
0x50479  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x5047e  ldloc.3
0x5047f  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x50484  brtrue.s loc_50493
0x50486  ldloc.2
0x50487  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x5048c  ldloc.3
0x5048d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x50492  pop
0x50493  ldarg.0
0x50494  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x50499  ldloc.2
0x5049a  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x5049f  brtrue.s loc_504AE
0x504a1  ldarg.0
0x504a2  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x504a7  ldloc.2
0x504a8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x504ad  pop
0x504ae  ldloc.s  7
0x504b0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x504b5  brtrue   loc_5023D
0x504ba  leave.s  loc_504D1
0x504bc  ldloc.s  7
0x504be  isinst   [mscorlib]System.IDisposable
0x504c3  stloc.s  0xD
0x504c5  ldloc.s  0xD
0x504c7  brfalse.s loc_504D0
0x504c9  ldloc.s  0xD
0x504cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x504d0  endfinally
0x504d1  ret
```
