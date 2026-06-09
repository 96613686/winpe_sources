# Microsoft.VisualStudio.Setup.Extensions::ToChannelProductItem

- ea: `0x5ba0`
- end: `0x5c6d`
- name: `Microsoft.VisualStudio.Setup.Extensions::ToChannelProductItem`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x5ba0`
- `0x6c60`
- `0x6c70`
- `0x83a0`
- `0x9a50`
- `0x9a70`
- `0x9aa0`
- `0x9ac0`
- `0x9ae0`
- `0x9b00`
- `0x9d90`
- `0x9db0`
- `0xafe0`
- `0xb040`
- `0xb0d0`
- `0xc1a0`
- `0x17fb0`
- `0x17fd0`
- `0x18000`
- `0x18020`
- `0x18040`
- `0x18060`
- `0x180b0`
- `0x18d30`
- `0x18d70`
- `0x18d90`
- `0x18db0`
- `0x18de0`

## pseudocode

```c

```

## disassembly

```asm
0x5ba0  ldarg.0
0x5ba1  ldstr    aProduct// "product"
0x5ba6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x5bab  newobj   instance void Microsoft.VisualStudio.Setup.ChannelSets.ProductSummaryItem::.ctor()
0x5bb0  dup
0x5bb1  ldarg.0
0x5bb2  callvirt instance string Microsoft.VisualStudio.Setup.Package::get_Id()
0x5bb7  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelItem::set_Id(string value)
0x5bbc  dup
0x5bbd  ldarg.0
0x5bbe  callvirt instance string Microsoft.VisualStudio.Setup.Package::get_Branch()
0x5bc3  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelItem::set_Branch(string value)
0x5bc8  dup
0x5bc9  ldarg.0
0x5bca  callvirt instance string Microsoft.VisualStudio.Setup.Package::get_Chip()
0x5bcf  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelItem::set_Chip(string value)
0x5bd4  dup
0x5bd5  ldarg.0
0x5bd6  callvirt instance string Microsoft.VisualStudio.Setup.Package::get_Language()
0x5bdb  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelItem::set_Language(string value)
0x5be0  dup
0x5be1  ldarg.0
0x5be2  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Package::get_Version()
0x5be7  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelItem::set_Version(class [mscorlib]System.Version value)
0x5bec  dup
0x5bed  ldarg.0
0x5bee  callvirt instance class Microsoft.VisualStudio.Setup.Icon Microsoft.VisualStudio.Setup.Product::get_Icon()
0x5bf3  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ProductSummaryItem::set_Icon(class Microsoft.VisualStudio.Setup.Icon value)
0x5bf8  dup
0x5bf9  ldarg.0
0x5bfa  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Product::get_ReleaseNotes()
0x5bff  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ProductSummaryItem::set_ReleaseNotes(class [System]System.Uri value)
0x5c04  dup
0x5c05  ldarg.0
0x5c06  callvirt instance bool Microsoft.VisualStudio.Setup.Product::get_SupportsDownloadThenUpdate()
0x5c0b  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ProductSummaryItem::set_SupportsDownloadThenUpdate(bool value)
0x5c10  dup
0x5c11  ldarg.0
0x5c12  callvirt instance class Microsoft.VisualStudio.Setup.Requirement Microsoft.VisualStudio.Setup.Package::get_Requirements()
0x5c17  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ProductSummaryItem::set_Requirements(class Microsoft.VisualStudio.Setup.Requirement value)
0x5c1c  dup
0x5c1d  ldarg.0
0x5c1e  callvirt instance string Microsoft.VisualStudio.Setup.Package::get_ProductArch()
0x5c23  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelItem::set_ProductArch(string value)
0x5c28  stloc.0
0x5c29  ldloc.0
0x5c2a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.ChannelSets.ChannelItem::get_LocalizedResources()
0x5c2f  ldarg.0
0x5c30  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Package::get_LocalizedResources()
0x5c35  call     T0x2B000021
0x5c3a  ldarg.0
0x5c3b  stloc.1
0x5c3c  ldloc.1
0x5c3d  brtrue.s loc_5C42
0x5c3f  ldnull
0x5c40  br.s     loc_5C48
0x5c42  ldloc.1
0x5c43  callvirt instance class Microsoft.VisualStudio.Setup.ItemBuildInformation Microsoft.VisualStudio.Setup.IItemBuildInformation::get_BuildInformation()
0x5c48  brfalse.s loc_5C6B
0x5c4a  ldloc.0
0x5c4b  stloc.2
0x5c4c  ldloc.2
0x5c4d  brfalse.s loc_5C6B
0x5c4f  ldloc.2
0x5c50  newobj   instance void Microsoft.VisualStudio.Setup.ItemBuildInformation::.ctor()
0x5c55  callvirt instance void Microsoft.VisualStudio.Setup.IItemBuildInformation::set_BuildInformation(class Microsoft.VisualStudio.Setup.ItemBuildInformation value)
0x5c5a  ldloc.2
0x5c5b  callvirt instance class Microsoft.VisualStudio.Setup.ItemBuildInformation Microsoft.VisualStudio.Setup.IItemBuildInformation::get_BuildInformation()
0x5c60  ldloc.1
0x5c61  callvirt instance class Microsoft.VisualStudio.Setup.ItemBuildInformation Microsoft.VisualStudio.Setup.IItemBuildInformation::get_BuildInformation()
0x5c66  call     T0x2B000022
0x5c6b  ldloc.0
0x5c6c  ret
```
