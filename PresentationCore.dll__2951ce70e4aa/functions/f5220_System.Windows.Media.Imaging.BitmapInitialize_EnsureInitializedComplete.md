# System.Windows.Media.Imaging.BitmapInitialize::EnsureInitializedComplete

- ea: `0xf5220`
- end: `0xf5253`
- name: `System.Windows.Media.Imaging.BitmapInitialize::EnsureInitializedComplete`
- size: `51`
- prototype: ``
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xf6b20`
- `0xf6b50`
- `0xf6b80`
- `0xf6bb0`
- `0xf6be0`
- `0xf6c10`
- `0xf6db0`
- `0xf70a0`
- `0xf81e0`
- `0xf9b00`
- `0xfa160`
- `0xfa670`
- `0xfdd70`

## callees

- `0xf5200`
- `0xf5210`
- `0xf5220`
- `0x146e70`

## string_xrefs

- `0xf5228`: `Image_InitializationIncomplete`

## pseudocode

```c

```

## disassembly

```asm
0xf5220  ldarg.0
0xf5221  call     instance bool System.Windows.Media.Imaging.BitmapInitialize::get_IsInInit()
0xf5226  brfalse.s loc_F5239
0xf5228  ldstr    aImageInitializ// "Image_InitializationIncomplete"
0xf522d  ldnull
0xf522e  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0xf5233  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xf5238  throw
0xf5239  ldarg.0
0xf523a  call     instance bool System.Windows.Media.Imaging.BitmapInitialize::get_IsInitAtLeastOnce()
0xf523f  brtrue.s loc_F5252
0xf5241  ldstr    aImageNotinitia// "Image_NotInitialized"
0xf5246  ldnull
0xf5247  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0xf524c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xf5251  throw
0xf5252  ret
```
