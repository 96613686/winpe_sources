# System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart

- ea: `0x249a0`
- end: `0x24a07`
- name: `System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart`
- size: `103`
- prototype: ``
- caller_count: `14`
- callee_count: `6`
- tags: ``

## callers

- `0x20b40`
- `0x212a0`
- `0x22200`
- `0x22470`
- `0x224e0`
- `0x22510`
- `0x226a0`
- `0x22d40`
- `0x22e80`
- `0x22f00`
- `0x24c40`
- `0x24e90`
- `0x24ec0`
- `0x25e90`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x24870`
- `0x248d0`
- `0x249a0`
- `0x25340`

## string_xrefs

- `0x249bb`: `ReachPackaging_OnlyWriters`

## pseudocode

```c

```

## disassembly

```asm
0x249a0  ldarg.0
0x249a1  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x249a6  brtrue.s loc_249B3
0x249a8  ldstr    aXpsmanager// "XpsManager"
0x249ad  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x249b2  throw
0x249b3  ldarg.0
0x249b4  call     instance bool System.Windows.Xps.Packaging.XpsManager::get_IsWriter()
0x249b9  brtrue.s loc_249CB
0x249bb  ldstr    aReachpackaging_18// "ReachPackaging_OnlyWriters"
0x249c0  call     string System.Windows.Xps.SR::Get(string id)
0x249c5  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x249ca  throw
0x249cb  ldarg.1
0x249cc  brtrue.s loc_249D9
0x249ce  ldstr    aContenttype// "contentType"
0x249d3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x249d8  throw
0x249d9  call     class [WindowsBase]MS.Internal.ContentType [WindowsBase]MS.Internal.ContentType::get_Empty()
0x249de  ldarg.1
0x249df  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x249e4  brfalse.s loc_249F6
0x249e6  ldstr    aReachpackaging_9// "ReachPackaging_InvalidType"
0x249eb  call     string System.Windows.Xps.SR::Get(string id)
0x249f0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x249f5  throw
0x249f6  ldarg.0
0x249f7  ldarg.1
0x249f8  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsManager::GenerateUniqueUri(class [WindowsBase]MS.Internal.ContentType contentType)
0x249fd  stloc.0
0x249fe  ldarg.0
0x249ff  ldarg.1
0x24a00  ldloc.0
0x24a01  call     instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GeneratePart(class [WindowsBase]MS.Internal.ContentType contentType, class [System]System.Uri partUri)
0x24a06  ret
```
