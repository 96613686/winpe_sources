# System.Windows.Xps.Packaging.XpsManager::GeneratePart

- ea: `0x248d0`
- end: `0x24995`
- name: `System.Windows.Xps.Packaging.XpsManager::GeneratePart`
- size: `197`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x21370`
- `0x22330`
- `0x22f80`
- `0x249a0`
- `0x24ac0`
- `0x24b60`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x1efa0`
- `0x200c0`
- `0x20120`
- `0x20140`
- `0x20160`
- `0x24870`
- `0x248d0`

## string_xrefs

- `0x248eb`: `ReachPackaging_OnlyWriters`

## pseudocode

```c

```

## disassembly

```asm
0x248d0  ldarg.0
0x248d1  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x248d6  brtrue.s loc_248E3
0x248d8  ldstr    aXpsmanager// "XpsManager"
0x248dd  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x248e2  throw
0x248e3  ldarg.0
0x248e4  call     instance bool System.Windows.Xps.Packaging.XpsManager::get_IsWriter()
0x248e9  brtrue.s loc_248FB
0x248eb  ldstr    aReachpackaging_18// "ReachPackaging_OnlyWriters"
0x248f0  call     string System.Windows.Xps.SR::Get(string id)
0x248f5  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x248fa  throw
0x248fb  ldarg.1
0x248fc  brtrue.s loc_24909
0x248fe  ldstr    aContenttype// "contentType"
0x24903  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24908  throw
0x24909  ldarg.1
0x2490a  callvirt instance string [mscorlib]System.Object::ToString()
0x2490f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x24914  brtrue.s loc_24935
0x24916  ldstr    aReachpackaging// "ReachPackaging_InvalidContentType"
0x2491b  ldc.i4.1
0x2491c  newarr   [mscorlib]System.Object
0x24921  dup
0x24922  ldc.i4.0
0x24923  ldarg.1
0x24924  stelem.ref
0x24925  call     string System.Windows.Xps.SR::Get(string id, object[] args)
0x2492a  ldstr    aContenttype// "contentType"
0x2492f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x24934  throw
0x24935  ldarg.0
0x24936  ldfld    valuetype [WindowsBase]System.IO.Packaging.CompressionOption System.Windows.Xps.Packaging.XpsManager::_compressionOption
0x2493b  stloc.0
0x2493c  ldarg.1
0x2493d  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_JpgContentType()
0x24942  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x24947  brtrue.s loc_24970
0x24949  ldarg.1
0x2494a  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_PngContentType()
0x2494f  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x24954  brtrue.s loc_24970
0x24956  ldarg.1
0x24957  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_TifContentType()
0x2495c  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x24961  brtrue.s loc_24970
0x24963  ldarg.1
0x24964  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_WdpContentType()
0x24969  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x2496e  brfalse.s loc_24972
0x24970  ldc.i4.m1
0x24971  stloc.0
0x24972  ldarg.0
0x24973  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24978  ldarg.2
0x24979  ldarg.1
0x2497a  callvirt instance string [mscorlib]System.Object::ToString()
0x2497f  ldloc.0
0x24980  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::CreatePart(class [System]System.Uri, string, valuetype [WindowsBase]System.IO.Packaging.CompressionOption)
0x24985  stloc.1
0x24986  ldarg.0
0x24987  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [WindowsBase]System.IO.Packaging.PackagePart> System.Windows.Xps.Packaging.XpsManager::_cachedParts
0x2498c  ldarg.2
0x2498d  ldloc.1
0x2498e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [WindowsBase]System.IO.Packaging.PackagePart>::set_Item(var<u1>, !!T0)
0x24993  ldloc.1
0x24994  ret
```
