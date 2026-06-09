# System.Windows.Xps.Packaging.XpsManager::GenerateObfuscatedFontPart

- ea: `0x24a30`
- end: `0x24ab7`
- name: `System.Windows.Xps.Packaging.XpsManager::GenerateObfuscatedFontPart`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x22470`
- `0x22dc0`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x1fdd0`
- `0x200a0`
- `0x24870`
- `0x24a30`

## string_xrefs

- `0x24a4b`: `ReachPackaging_OnlyWriters`

## pseudocode

```c

```

## disassembly

```asm
0x24a30  ldarg.0
0x24a31  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24a36  brtrue.s loc_24A43
0x24a38  ldstr    aXpsmanager// "XpsManager"
0x24a3d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x24a42  throw
0x24a43  ldarg.0
0x24a44  call     instance bool System.Windows.Xps.Packaging.XpsManager::get_IsWriter()
0x24a49  brtrue.s loc_24A5B
0x24a4b  ldstr    aReachpackaging_18// "ReachPackaging_OnlyWriters"
0x24a50  call     string System.Windows.Xps.SR::Get(string id)
0x24a55  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x24a5a  throw
0x24a5b  ldstr    aResources// "/Resources/"
0x24a60  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x24a65  stloc.3
0x24a66  ldloca.s 3
0x24a68  constrained. [mscorlib]System.Guid
0x24a6e  callvirt instance string [mscorlib]System.Object::ToString()
0x24a73  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ObfuscatedFontExt()
0x24a78  call     string [mscorlib]System.String::Concat(string, string, string)
0x24a7d  stloc.0
0x24a7e  ldloc.0
0x24a7f  ldc.i4.2
0x24a80  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x24a85  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri)
0x24a8a  stloc.1
0x24a8b  ldarg.0
0x24a8c  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24a91  ldloc.1
0x24a92  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FontObfuscatedContentType()
0x24a97  callvirt instance string [mscorlib]System.Object::ToString()
0x24a9c  ldarg.0
0x24a9d  ldfld    valuetype [WindowsBase]System.IO.Packaging.CompressionOption System.Windows.Xps.Packaging.XpsManager::_compressionOption
0x24aa2  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::CreatePart(class [System]System.Uri, string, valuetype [WindowsBase]System.IO.Packaging.CompressionOption)
0x24aa7  stloc.2
0x24aa8  ldarg.0
0x24aa9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [WindowsBase]System.IO.Packaging.PackagePart> System.Windows.Xps.Packaging.XpsManager::_cachedParts
0x24aae  ldloc.1
0x24aaf  ldloc.2
0x24ab0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [WindowsBase]System.IO.Packaging.PackagePart>::set_Item(var<u1>, !!T0)
0x24ab5  ldloc.2
0x24ab6  ret
```
