# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddChildrenFromChannelConfig

- ea: `0x4a280`
- end: `0x4a42c`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddChildrenFromChannelConfig`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4a430`

## callees

- `0x12ed0`
- `0x14cc0`
- `0x14db0`
- `0x14de0`
- `0x14e30`
- `0x46610`
- `0x46880`
- `0x46d40`
- `0x46d50`
- `0x46ea0`
- `0x46eb0`
- `0x4a200`
- `0x4a280`
- `0x4e9e0`
- `0x4fe80`
- `0x4fef0`
- `0x4ff10`

## string_xrefs

- `0x4a3fe`: `Warning: AddChildrenFromChannelConfig: Duplicated channel name '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x4a280  ldarg.0
0x4a281  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::m_cfgInst
0x4a286  castclass Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder
0x4a28b  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x4a290  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x4a295  newarr   Microsoft.Windows.ManagementUI.CombinedControls.EventsNode
0x4a29a  stloc.0
0x4a29b  ldc.i4.0
0x4a29c  stloc.1
0x4a29d  ldarg.0
0x4a29e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::m_cfgInst
0x4a2a3  castclass Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder
0x4a2a8  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_Children()
0x4a2ad  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x4a2b2  stloc.2
0x4a2b3  br       loc_4A38A
0x4a2b8  ldloc.2
0x4a2b9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a2be  castclass Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance
0x4a2c3  stloc.3
0x4a2c4  ldloc.3
0x4a2c5  isinst   Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder
0x4a2ca  stloc.s  4
0x4a2cc  ldloc.s  4
0x4a2ce  brfalse.s loc_4A33F
0x4a2d0  ldloc.0
0x4a2d1  ldloc.1
0x4a2d2  ldc.i4.0
0x4a2d3  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType type)
0x4a2d8  stelem.ref
0x4a2d9  ldloc.0
0x4a2da  ldloc.1
0x4a2db  ldelem.ref
0x4a2dc  ldloc.3
0x4a2dd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Config(class Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance value)
0x4a2e2  ldloc.0
0x4a2e3  ldloc.1
0x4a2e4  ldelem.ref
0x4a2e5  ldloc.s  4
0x4a2e7  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Name()
0x4a2ec  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x4a2f1  ldloc.0
0x4a2f2  ldloc.1
0x4a2f3  ldelem.ref
0x4a2f4  ldloc.0
0x4a2f5  ldloc.1
0x4a2f6  ldelem.ref
0x4a2f7  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Config()
0x4a2fc  castclass Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder
0x4a301  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Name()
0x4a306  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x4a30b  ldloc.0
0x4a30c  ldloc.1
0x4a30d  ldelem.ref
0x4a30e  ldstr    aEventsfolder// "EventsFolder"
0x4a313  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_ItemType(string value)
0x4a318  ldloc.s  4
0x4a31a  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_IsCorruptPublisher()
0x4a31f  brfalse.s loc_4A386
0x4a321  ldloc.s  4
0x4a323  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ConfigType Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_ConfigType()
0x4a328  ldc.i4.8
0x4a329  bne.un.s loc_4A386
0x4a32b  ldloc.0
0x4a32c  ldloc.1
0x4a32d  ldelem.ref
0x4a32e  ldstr    aPublishermetad// "PublisherMetaDataErrorDescriptionForPub"...
0x4a333  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4a338  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Description(string value)
0x4a33d  br.s     loc_4A386
0x4a33f  ldloc.0
0x4a340  ldloc.1
0x4a341  ldc.i4.1
0x4a342  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType type)
0x4a347  stelem.ref
0x4a348  ldloc.0
0x4a349  ldloc.1
0x4a34a  ldelem.ref
0x4a34b  ldloc.3
0x4a34c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Config(class Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance value)
0x4a351  ldloc.0
0x4a352  ldloc.1
0x4a353  ldelem.ref
0x4a354  ldloc.3
0x4a355  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Name()
0x4a35a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x4a35f  ldloc.0
0x4a360  ldloc.1
0x4a361  ldelem.ref
0x4a362  ldloc.0
0x4a363  ldloc.1
0x4a364  ldelem.ref
0x4a365  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Config()
0x4a36a  castclass Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig
0x4a36f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Name()
0x4a374  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x4a379  ldloc.0
0x4a37a  ldloc.1
0x4a37b  ldelem.ref
0x4a37c  ldstr    aEventsview// "EventsView"
0x4a381  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_ItemType(string value)
0x4a386  ldloc.1
0x4a387  ldc.i4.1
0x4a388  add
0x4a389  stloc.1
0x4a38a  ldloc.2
0x4a38b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a390  brtrue   loc_4A2B8
0x4a395  leave.s  loc_4A3AB
0x4a397  ldloc.2
0x4a398  isinst   [mscorlib]System.IDisposable
0x4a39d  stloc.s  5
0x4a39f  ldloc.s  5
0x4a3a1  brfalse.s loc_4A3AA
0x4a3a3  ldloc.s  5
0x4a3a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a3aa  endfinally
0x4a3ab  ldarg.0
0x4a3ac  call     instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x4a3b1  ldc.i4.3
0x4a3b2  beq.s    loc_4A3BB
0x4a3b4  ldarg.0
0x4a3b5  ldloc.0
0x4a3b6  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::SortNodes(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode[] nodes)
0x4a3bb  ldloc.0
0x4a3bc  stloc.s  6
0x4a3be  ldc.i4.0
0x4a3bf  stloc.s  7
0x4a3c1  br.s     loc_4A423
0x4a3c3  ldloc.s  6
0x4a3c5  ldloc.s  7
0x4a3c7  ldelem.ref
0x4a3c8  stloc.s  8
0x4a3ca  ldloc.s  8
0x4a3cc  ldarg.0
0x4a3cd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ParentNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x4a3d2  ldarg.0
0x4a3d3  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x4a3d8  ldloc.s  8
0x4a3da  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x4a3df  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x4a3e4  brtrue.s loc_4A3FC
0x4a3e6  ldarg.0
0x4a3e7  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x4a3ec  ldloc.s  8
0x4a3ee  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x4a3f3  ldloc.s  8
0x4a3f5  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x4a3fa  br.s     loc_4A41D
0x4a3fc  ldarg.0
0x4a3fd  ldnull
0x4a3fe  ldstr    aWarningAddchil// "Warning: AddChildrenFromChannelConfig: "...
0x4a403  ldc.i4.1
0x4a404  newarr   [mscorlib]System.Object
0x4a409  dup
0x4a40a  ldc.i4.0
0x4a40b  ldloc.s  8
0x4a40d  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x4a412  stelem.ref
0x4a413  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4a418  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0x4a41d  ldloc.s  7
0x4a41f  ldc.i4.1
0x4a420  add
0x4a421  stloc.s  7
0x4a423  ldloc.s  7
0x4a425  ldloc.s  6
0x4a427  ldlen
0x4a428  conv.i4
0x4a429  blt.s    loc_4A3C3
0x4a42b  ret
```
