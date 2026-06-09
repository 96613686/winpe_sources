# Microsoft.VisualStudio.Setup.ChannelSets.Channel::.ctor

- ea: `0x17a40`
- end: `0x17b15`
- name: `Microsoft.VisualStudio.Setup.ChannelSets.Channel::.ctor`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18350`

## callees

- `0xc1a0`
- `0x17a40`
- `0x17b40`
- `0x17e20`

## string_xrefs

- `0x17ab6`: `The ChannelManifest must contain at least one one item of type ChannelProduct`
- `0x17b09`: `The ChannelManifest must contain distinct product identities of type ChannelProduct`

## pseudocode

```c

```

## disassembly

```asm
0x17a40  ldarg.0
0x17a41  call     instance void [mscorlib]System.Object::.ctor()
0x17a46  ldarg.1
0x17a47  ldstr    aChannelmanfies// "channelManfiest"
0x17a4c  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x17a51  ldarg.0
0x17a52  ldarg.1
0x17a53  stfld    class Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest Microsoft.VisualStudio.Setup.ChannelSets.Channel::<ChannelManifest>k__BackingField
0x17a58  ldarg.0
0x17a59  ldarg.0
0x17a5a  ldarg.2
0x17a5b  call     T0x2B00009C
0x17a60  stfld    class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelHeaderItem> Microsoft.VisualStudio.Setup.ChannelSets.Channel::<ChannelHeader>k__BackingField
0x17a65  ldarg.0
0x17a66  ldarg.0
0x17a67  ldarg.2
0x17a68  call     T0x2B00009D
0x17a6d  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>> Microsoft.VisualStudio.Setup.ChannelSets.Channel::<ProductSummaries>k__BackingField
0x17a72  ldarg.0
0x17a73  ldarg.0
0x17a74  ldarg.2
0x17a75  call     T0x2B00009E
0x17a7a  stfld    class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IManifestItem> Microsoft.VisualStudio.Setup.ChannelSets.Channel::<ProductManifest>k__BackingField
0x17a7f  ldarg.0
0x17a80  ldarg.0
0x17a81  ldc.i4.0
0x17a82  call     T0x2B00009F
0x17a87  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.ISetupManifestItem>> Microsoft.VisualStudio.Setup.ChannelSets.Channel::<SetupManifests>k__BackingField
0x17a8c  ldarg.0
0x17a8d  ldarg.0
0x17a8e  ldc.i4.0
0x17a8f  call     T0x2B0000A0
0x17a94  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.ISetupPackageItem>> Microsoft.VisualStudio.Setup.ChannelSets.Channel::<SetupPackages>k__BackingField
0x17a99  ldarg.0
0x17a9a  ldarg.0
0x17a9b  ldc.i4.0
0x17a9c  call     T0x2B0000A1
0x17aa1  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem>> Microsoft.VisualStudio.Setup.ChannelSets.Channel::<Bootstrappers>k__BackingField
0x17aa6  ldarg.2
0x17aa7  brfalse.s loc_17B14
0x17aa9  ldarg.0
0x17aaa  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>> Microsoft.VisualStudio.Setup.ChannelSets.Channel::get_ProductSummaries()
0x17aaf  call     T0x2B0000A2
0x17ab4  brtrue.s loc_17AC1
0x17ab6  ldstr    aTheChannelmani// "The ChannelManifest must contain at lea"...
0x17abb  newobj   instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelCompositionException::.ctor(string message)
0x17ac0  throw
0x17ac1  ldarg.0
0x17ac2  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>> Microsoft.VisualStudio.Setup.ChannelSets.Channel::get_ProductSummaries()
0x17ac7  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>, class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem> <>c::<>9__1_0
0x17acc  dup
0x17acd  brtrue.s loc_17AE6
0x17acf  pop
0x17ad0  ldsfld   class <>c <>c::<>9
0x17ad5  ldftn    instance class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem <>c::<.ctor>b__1_0(class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem> ps)
0x17adb  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>, class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>::.ctor(object, native int)
0x17ae0  dup
0x17ae1  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>, class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem> <>c::<>9__1_0
0x17ae6  call     T0x2B0000A3
0x17aeb  ldsfld   class Microsoft.VisualStudio.Setup.PackageIdentityComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::VersionIndependent
0x17af0  call     T0x2B0000A4
0x17af5  call     T0x2B0000A5
0x17afa  stloc.0
0x17afb  ldarg.0
0x17afc  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<class Microsoft.VisualStudio.Setup.ChannelSets.IProductSummaryItem>> Microsoft.VisualStudio.Setup.ChannelSets.Channel::get_ProductSummaries()
0x17b01  call     T0x2B0000A6
0x17b06  ldloc.0
0x17b07  beq.s    loc_17B14
0x17b09  ldstr    aTheChannelmani_0// "The ChannelManifest must contain distin"...
0x17b0e  newobj   instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelCompositionException::.ctor(string message)
0x17b13  throw
0x17b14  ret
```
