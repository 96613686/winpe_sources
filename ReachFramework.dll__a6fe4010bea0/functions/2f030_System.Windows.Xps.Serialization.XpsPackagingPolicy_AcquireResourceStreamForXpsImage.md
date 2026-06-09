# System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsImage

- ea: `0x2f030`
- end: `0x2f0c3`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsImage`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x21e30`
- `0x23f60`
- `0x25a70`
- `0x26480`
- `0x2e7c0`
- `0x2f030`

## string_xrefs

- `0x2f073`: `ReachSerialization_NoFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f030  ldnull
0x2f031  stloc.0
0x2f032  ldarg.0
0x2f033  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImageRef
0x2f038  brtrue.s loc_2F0AC
0x2f03a  ldarg.0
0x2f03b  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f040  brfalse.s loc_2F073
0x2f042  ldarg.0
0x2f043  ldarg.0
0x2f044  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f049  ldarg.1
0x2f04a  callvirt instance class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Packaging.IXpsFixedPageWriter::AddImage(string mimeType)
0x2f04f  stfld    class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImage
0x2f054  ldarg.0
0x2f055  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2f05a  ldarg.0
0x2f05b  ldfld    class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImage
0x2f060  ldc.i4.0
0x2f061  ldarg.0
0x2f062  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f067  castclass System.Windows.Xps.Packaging.INode
0x2f06c  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::AddItem(class System.Windows.Xps.Packaging.INode n, int32 number, class System.Windows.Xps.Packaging.INode parent)
0x2f071  br.s     loc_2F083
0x2f073  ldstr    aReachserializa_0// "ReachSerialization_NoFixedPageWriter"
0x2f078  call     string System.Windows.Xps.SR::Get(string id)
0x2f07d  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f082  throw
0x2f083  ldarg.0
0x2f084  ldfld    class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImage
0x2f089  brfalse.s loc_2F0AC
0x2f08b  ldarg.0
0x2f08c  ldarg.0
0x2f08d  ldfld    class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImage
0x2f092  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Xps.Packaging.XpsResource::GetStream()
0x2f097  ldarg.0
0x2f098  ldfld    class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImage
0x2f09d  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2f0a2  newobj   instance void System.Windows.Xps.Serialization.XpsResourceStream::.ctor(class [mscorlib]System.IO.Stream stream, class [System]System.Uri uri)
0x2f0a7  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_imageResourceStream
0x2f0ac  ldarg.0
0x2f0ad  ldarg.0
0x2f0ae  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImageRef
0x2f0b3  ldc.i4.1
0x2f0b4  add
0x2f0b5  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImageRef
0x2f0ba  ldarg.0
0x2f0bb  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_imageResourceStream
0x2f0c0  stloc.0
0x2f0c1  ldloc.0
0x2f0c2  ret
```
