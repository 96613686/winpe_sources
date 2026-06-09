# System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsFont

- ea: `0x2edc0`
- end: `0x2ee6d`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsFont`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x21de0`
- `0x23f60`
- `0x25a70`
- `0x26480`
- `0x2e7c0`
- `0x2edc0`

## string_xrefs

- `0x2ee1d`: `ReachSerialization_NoFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2edc0  ldnull
0x2edc1  stloc.0
0x2edc2  ldarg.0
0x2edc3  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2edc8  ldc.i4.2
0x2edc9  beq      loc_2EE6B
0x2edce  ldarg.0
0x2edcf  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2edd4  brtrue.s loc_2EDDD
0x2edd6  ldarg.0
0x2edd7  ldc.i4.1
0x2edd8  stfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2eddd  ldarg.0
0x2edde  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFontRef
0x2ede3  brtrue.s loc_2EE56
0x2ede5  ldarg.0
0x2ede6  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2edeb  brfalse.s loc_2EE1D
0x2eded  ldarg.0
0x2edee  ldarg.0
0x2edef  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2edf4  callvirt instance class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Packaging.IXpsFixedPageWriter::AddFont()
0x2edf9  stfld    class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFont
0x2edfe  ldarg.0
0x2edff  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2ee04  ldarg.0
0x2ee05  ldfld    class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFont
0x2ee0a  ldc.i4.0
0x2ee0b  ldarg.0
0x2ee0c  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2ee11  castclass System.Windows.Xps.Packaging.INode
0x2ee16  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::AddItem(class System.Windows.Xps.Packaging.INode n, int32 number, class System.Windows.Xps.Packaging.INode parent)
0x2ee1b  br.s     loc_2EE2D
0x2ee1d  ldstr    aReachserializa_0// "ReachSerialization_NoFixedPageWriter"
0x2ee22  call     string System.Windows.Xps.SR::Get(string id)
0x2ee27  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2ee2c  throw
0x2ee2d  ldarg.0
0x2ee2e  ldfld    class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFont
0x2ee33  brfalse.s loc_2EE56
0x2ee35  ldarg.0
0x2ee36  ldarg.0
0x2ee37  ldfld    class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFont
0x2ee3c  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Xps.Packaging.XpsResource::GetStream()
0x2ee41  ldarg.0
0x2ee42  ldfld    class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFont
0x2ee47  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2ee4c  newobj   instance void System.Windows.Xps.Serialization.XpsResourceStream::.ctor(class [mscorlib]System.IO.Stream stream, class [System]System.Uri uri)
0x2ee51  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontResourceStream
0x2ee56  ldarg.0
0x2ee57  ldarg.0
0x2ee58  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFontRef
0x2ee5d  ldc.i4.1
0x2ee5e  add
0x2ee5f  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFontRef
0x2ee64  ldarg.0
0x2ee65  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontResourceStream
0x2ee6a  stloc.0
0x2ee6b  ldloc.0
0x2ee6c  ret
```
