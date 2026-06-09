# System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsResourceDictionary

- ea: `0x2f250`
- end: `0x2f2e2`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsResourceDictionary`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x21e20`
- `0x23f60`
- `0x25a70`
- `0x26480`
- `0x2e7c0`
- `0x2f250`

## string_xrefs

- `0x2f292`: `ReachSerialization_NoFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f250  ldnull
0x2f251  stloc.0
0x2f252  ldarg.0
0x2f253  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionaryRef
0x2f258  brtrue.s loc_2F2CB
0x2f25a  ldarg.0
0x2f25b  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f260  brfalse.s loc_2F292
0x2f262  ldarg.0
0x2f263  ldarg.0
0x2f264  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f269  callvirt instance class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Packaging.IXpsFixedPageWriter::AddResourceDictionary()
0x2f26e  stfld    class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionary
0x2f273  ldarg.0
0x2f274  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2f279  ldarg.0
0x2f27a  ldfld    class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionary
0x2f27f  ldc.i4.0
0x2f280  ldarg.0
0x2f281  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f286  castclass System.Windows.Xps.Packaging.INode
0x2f28b  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::AddItem(class System.Windows.Xps.Packaging.INode n, int32 number, class System.Windows.Xps.Packaging.INode parent)
0x2f290  br.s     loc_2F2A2
0x2f292  ldstr    aReachserializa_0// "ReachSerialization_NoFixedPageWriter"
0x2f297  call     string System.Windows.Xps.SR::Get(string id)
0x2f29c  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f2a1  throw
0x2f2a2  ldarg.0
0x2f2a3  ldfld    class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionary
0x2f2a8  brfalse.s loc_2F2CB
0x2f2aa  ldarg.0
0x2f2ab  ldarg.0
0x2f2ac  ldfld    class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionary
0x2f2b1  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Xps.Packaging.XpsResource::GetStream()
0x2f2b6  ldarg.0
0x2f2b7  ldfld    class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionary
0x2f2bc  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2f2c1  newobj   instance void System.Windows.Xps.Serialization.XpsResourceStream::.ctor(class [mscorlib]System.IO.Stream stream, class [System]System.Uri uri)
0x2f2c6  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_resourceDictionaryResourceStream
0x2f2cb  ldarg.0
0x2f2cc  ldarg.0
0x2f2cd  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionaryRef
0x2f2d2  ldc.i4.1
0x2f2d3  add
0x2f2d4  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionaryRef
0x2f2d9  ldarg.0
0x2f2da  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_resourceDictionaryResourceStream
0x2f2df  stloc.0
0x2f2e0  ldloc.0
0x2f2e1  ret
```
