# System.Windows.Xps.Serialization.NullPackagingPolicy::AcquireResourceStreamForXpsFont

- ea: `0x2f920`
- end: `0x2f997`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::AcquireResourceStreamForXpsFont`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2e7c0`
- `0x2f920`

## string_xrefs

- `0x2f954`: `ReachSerialization_NoFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f920  ldnull
0x2f921  stloc.0
0x2f922  ldarg.0
0x2f923  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2f928  ldc.i4.2
0x2f929  beq.s    loc_2F995
0x2f92b  ldarg.0
0x2f92c  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2f931  brtrue.s loc_2F93A
0x2f933  ldarg.0
0x2f934  ldc.i4.1
0x2f935  stfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2f93a  ldarg.0
0x2f93b  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsFontRef
0x2f940  brtrue.s loc_2F980
0x2f942  ldnull
0x2f943  stloc.1
0x2f944  ldarg.0
0x2f945  ldfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriter
0x2f94a  brfalse.s loc_2F954
0x2f94c  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x2f951  stloc.1
0x2f952  br.s     loc_2F964
0x2f954  ldstr    aReachserializa_0// "ReachSerialization_NoFixedPageWriter"
0x2f959  call     string System.Windows.Xps.SR::Get(string id)
0x2f95e  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f963  throw
0x2f964  ldloc.1
0x2f965  brfalse.s loc_2F980
0x2f967  ldarg.0
0x2f968  ldloc.1
0x2f969  ldstr    aPackageFont// "package/font"
0x2f96e  ldc.i4.2
0x2f96f  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x2f974  newobj   instance void System.Windows.Xps.Serialization.XpsResourceStream::.ctor(class [mscorlib]System.IO.Stream stream, class [System]System.Uri uri)
0x2f979  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_fontResourceStream
0x2f97e  ldnull
0x2f97f  stloc.1
0x2f980  ldarg.0
0x2f981  ldarg.0
0x2f982  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsFontRef
0x2f987  ldc.i4.1
0x2f988  add
0x2f989  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsFontRef
0x2f98e  ldarg.0
0x2f98f  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_fontResourceStream
0x2f994  stloc.0
0x2f995  ldloc.0
0x2f996  ret
```
