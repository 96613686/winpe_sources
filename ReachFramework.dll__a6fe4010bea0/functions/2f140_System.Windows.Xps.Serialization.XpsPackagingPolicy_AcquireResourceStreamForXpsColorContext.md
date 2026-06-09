# System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsColorContext

- ea: `0x2f140`
- end: `0x2f1d2`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsColorContext`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x21e10`
- `0x23f60`
- `0x25a70`
- `0x26480`
- `0x2e7c0`
- `0x2f140`

## string_xrefs

- `0x2f182`: `ReachSerialization_NoFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f140  ldnull
0x2f141  stloc.0
0x2f142  ldarg.0
0x2f143  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContextRef
0x2f148  brtrue.s loc_2F1BB
0x2f14a  ldarg.0
0x2f14b  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f150  brfalse.s loc_2F182
0x2f152  ldarg.0
0x2f153  ldarg.0
0x2f154  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f159  callvirt instance class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Packaging.IXpsFixedPageWriter::AddColorContext()
0x2f15e  stfld    class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContext
0x2f163  ldarg.0
0x2f164  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2f169  ldarg.0
0x2f16a  ldfld    class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContext
0x2f16f  ldc.i4.0
0x2f170  ldarg.0
0x2f171  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f176  castclass System.Windows.Xps.Packaging.INode
0x2f17b  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::AddItem(class System.Windows.Xps.Packaging.INode n, int32 number, class System.Windows.Xps.Packaging.INode parent)
0x2f180  br.s     loc_2F192
0x2f182  ldstr    aReachserializa_0// "ReachSerialization_NoFixedPageWriter"
0x2f187  call     string System.Windows.Xps.SR::Get(string id)
0x2f18c  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f191  throw
0x2f192  ldarg.0
0x2f193  ldfld    class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContext
0x2f198  brfalse.s loc_2F1BB
0x2f19a  ldarg.0
0x2f19b  ldarg.0
0x2f19c  ldfld    class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContext
0x2f1a1  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Xps.Packaging.XpsResource::GetStream()
0x2f1a6  ldarg.0
0x2f1a7  ldfld    class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContext
0x2f1ac  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2f1b1  newobj   instance void System.Windows.Xps.Serialization.XpsResourceStream::.ctor(class [mscorlib]System.IO.Stream stream, class [System]System.Uri uri)
0x2f1b6  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_colorContextResourceStream
0x2f1bb  ldarg.0
0x2f1bc  ldarg.0
0x2f1bd  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContextRef
0x2f1c2  ldc.i4.1
0x2f1c3  add
0x2f1c4  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContextRef
0x2f1c9  ldarg.0
0x2f1ca  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_colorContextResourceStream
0x2f1cf  stloc.0
0x2f1d0  ldloc.0
0x2f1d1  ret
```
