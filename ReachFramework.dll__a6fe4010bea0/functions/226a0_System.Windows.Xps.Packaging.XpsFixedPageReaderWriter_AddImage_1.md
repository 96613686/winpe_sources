# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddImage_1

- ea: `0x226a0`
- end: `0x2271a`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddImage_1`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x22640`
- `0x22650`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x1efa0`
- `0x226a0`
- `0x22d40`
- `0x249a0`
- `0x259b0`
- `0x25aa0`

## string_xrefs

- `0x226a8`: `FixedPageReader`

## pseudocode

```c

```

## disassembly

```asm
0x226a0  ldarg.0
0x226a1  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x226a6  brtrue.s loc_226B3
0x226a8  ldstr    aFixedpagereade// "FixedPageReader"
0x226ad  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x226b2  throw
0x226b3  ldarg.1
0x226b4  brtrue.s loc_226C1
0x226b6  ldstr    aMimetype// "mimeType"
0x226bb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x226c0  throw
0x226c1  call     class [WindowsBase]MS.Internal.ContentType [WindowsBase]MS.Internal.ContentType::get_Empty()
0x226c6  ldarg.1
0x226c7  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x226cc  brfalse.s loc_226ED
0x226ce  ldstr    aReachpackaging// "ReachPackaging_InvalidContentType"
0x226d3  ldc.i4.1
0x226d4  newarr   [mscorlib]System.Object
0x226d9  dup
0x226da  ldc.i4.0
0x226db  ldarg.1
0x226dc  callvirt instance string [mscorlib]System.Object::ToString()
0x226e1  stelem.ref
0x226e2  call     string System.Windows.Xps.SR::Get(string id, object[] args)
0x226e7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x226ec  throw
0x226ed  ldarg.1
0x226ee  call     bool System.Windows.Xps.Packaging.XpsManager::SupportedImageType(class [WindowsBase]MS.Internal.ContentType imageContentType)
0x226f3  brtrue.s loc_22705
0x226f5  ldstr    aReachpackaging_0// "ReachPackaging_UnsupportedImageType"
0x226fa  call     string System.Windows.Xps.SR::Get(string id)
0x226ff  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x22704  throw
0x22705  ldarg.0
0x22706  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x2270b  ldarg.1
0x2270c  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart(class [WindowsBase]MS.Internal.ContentType contentType)
0x22711  stloc.0
0x22712  ldarg.0
0x22713  ldloc.0
0x22714  call     instance class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddImage(class [WindowsBase]System.IO.Packaging.PackagePart packagePart)
0x22719  ret
```
