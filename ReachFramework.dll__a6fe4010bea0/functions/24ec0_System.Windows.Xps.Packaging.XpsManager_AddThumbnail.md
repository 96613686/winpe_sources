# System.Windows.Xps.Packaging.XpsManager::AddThumbnail

- ea: `0x24ec0`
- end: `0x24f02`
- name: `System.Windows.Xps.Packaging.XpsManager::AddThumbnail`
- size: `66`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x20b90`
- `0x21330`
- `0x22540`
- `0x25e20`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x23d40`
- `0x249a0`
- `0x24ec0`
- `0x259f0`

## string_xrefs

- `0x24ec5`: `ReachPackaging_AlreadyHasThumbnail`

## pseudocode

```c

```

## disassembly

```asm
0x24ec0  ldnull
0x24ec1  stloc.0
0x24ec2  ldarg.3
0x24ec3  brfalse.s loc_24ED5
0x24ec5  ldstr    aReachpackaging_23// "ReachPackaging_AlreadyHasThumbnail"
0x24eca  call     string System.Windows.Xps.SR::Get(string id)
0x24ecf  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x24ed4  throw
0x24ed5  ldarg.1
0x24ed6  ldc.i4.1
0x24ed7  beq.s    loc_24EEC
0x24ed9  ldarg.1
0x24eda  brfalse.s loc_24EEC
0x24edc  ldstr    aReachpackaging_24// "ReachPackaging_UnsupportedThumbnailImag"...
0x24ee1  call     string System.Windows.Xps.SR::Get(string id)
0x24ee6  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x24eeb  throw
0x24eec  ldarg.0
0x24eed  ldarg.2
0x24eee  ldarg.0
0x24eef  ldarg.1
0x24ef0  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsManager::ImageTypeToString(valuetype System.Windows.Xps.Packaging.XpsImageType imageType)
0x24ef5  call     instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart(class [WindowsBase]MS.Internal.ContentType contentType)
0x24efa  newobj   instance void System.Windows.Xps.Packaging.XpsThumbnail::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x24eff  stloc.0
0x24f00  ldloc.0
0x24f01  ret
```
