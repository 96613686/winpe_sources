# Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::CreateCorruptChannelNode

- ea: `0x504e0`
- end: `0x5060e`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::CreateCorruptChannelNode`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x500e0`

## callees

- `0x36430`
- `0x39550`
- `0x4e9e0`
- `0x4ea10`
- `0x4ec60`
- `0x4f530`
- `0x4fe70`
- `0x4fec0`
- `0x4fef0`
- `0x504e0`
- `0x50610`

## string_xrefs

- `0x50596`: `ConfigFolder:Initialize: adding `

## pseudocode

```c

```

## disassembly

```asm
0x504e0  ldnull
0x504e1  stloc.0
0x504e2  ldnull
0x504e3  stloc.s  4
0x504e5  ldnull
0x504e6  stloc.s  5
0x504e8  ldarg.0
0x504e9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x504ee  brfalse.s loc_504FC
0x504f0  ldarg.0
0x504f1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x504f6  ldarg.2
0x504f7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::SetChannel(class Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig ch)
0x504fc  ldarg.2
0x504fd  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_OwningPublisher()
0x50502  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x50507  brtrue.s loc_50511
0x50509  ldarg.2
0x5050a  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_OwningPublisher()
0x5050f  br.s     loc_50517
0x50511  ldarg.2
0x50512  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_LocalizedDisplayName()
0x50517  stloc.s  6
0x50519  ldloc.s  6
0x5051b  ldloca.s 1
0x5051d  ldloca.s 3
0x5051f  ldloca.s 2
0x50521  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::ParsePublisherName(string publisherName, [out] string& company, [out] string& productName, [out] string& publisher)
0x50526  brfalse.s loc_5053C
0x50528  ldarg.0
0x50529  ldc.i4.0
0x5052a  ldloc.s  6
0x5052c  ldloc.1
0x5052d  ldloc.3
0x5052e  ldloc.2
0x5052f  ldloca.s 4
0x50531  ldloca.s 5
0x50533  ldloca.s 0
0x50535  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::BuildPublisherNode(bool refreshRequired, string publisherIdentifier, string companyName, string productName, string publisherName, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& companyFolder, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& productFolder, [out] class Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder& publisherFolder)
0x5053a  br.s     loc_50562
0x5053c  ldnull
0x5053d  stloc.s  4
0x5053f  ldc.i4.8
0x50540  ldarg.2
0x50541  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_LocalizedDisplayName()
0x50546  ldarg.0
0x50547  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x5054c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ConfigType type, string path, class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext ctx)
0x50551  stloc.0
0x50552  ldloc.0
0x50553  ldloc.s  6
0x50555  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::set_Path(string value)
0x5055a  ldloc.0
0x5055b  ldloc.s  6
0x5055d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::set_HierarchyPath(string value)
0x50562  ldloc.0
0x50563  brfalse.s loc_50585
0x50565  ldloc.0
0x50566  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x5056b  ldarg.2
0x5056c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x50571  pop
0x50572  ldarg.1
0x50573  ldind.ref
0x50574  ldarg.2
0x50575  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x5057a  brtrue.s loc_50585
0x5057c  ldarg.1
0x5057d  ldind.ref
0x5057e  ldarg.2
0x5057f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x50584  pop
0x50585  ldloc.s  4
0x50587  brtrue.s loc_505AC
0x50589  ldarg.0
0x5058a  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x5058f  ldloc.0
0x50590  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x50595  pop
0x50596  ldstr    aConfigfolderIn// "ConfigFolder:Initialize: adding "
0x5059b  ldloc.0
0x5059c  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Name()
0x505a1  call     string [mscorlib]System.String::Concat(string, string)
0x505a6  call     void [System]System.Diagnostics.Trace::WriteLine(string)
0x505ab  ret
0x505ac  ldloc.s  5
0x505ae  brfalse.s loc_505CD
0x505b0  ldloc.s  5
0x505b2  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x505b7  ldloc.0
0x505b8  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x505bd  brtrue.s loc_505CD
0x505bf  ldloc.s  5
0x505c1  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x505c6  ldloc.0
0x505c7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x505cc  pop
0x505cd  ldloc.s  4
0x505cf  brfalse.s loc_505F0
0x505d1  ldloc.s  4
0x505d3  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x505d8  ldloc.s  5
0x505da  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x505df  brtrue.s loc_505F0
0x505e1  ldloc.s  4
0x505e3  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x505e8  ldloc.s  5
0x505ea  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x505ef  pop
0x505f0  ldarg.0
0x505f1  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x505f6  ldloc.s  4
0x505f8  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x505fd  brtrue.s loc_5060D
0x505ff  ldarg.0
0x50600  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x50605  ldloc.s  4
0x50607  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5060c  pop
0x5060d  ret
```
