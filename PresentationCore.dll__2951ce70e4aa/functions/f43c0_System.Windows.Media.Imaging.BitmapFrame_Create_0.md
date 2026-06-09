# System.Windows.Media.Imaging.BitmapFrame::Create_0

- ea: `0xf43c0`
- end: `0xf43e0`
- name: `System.Windows.Media.Imaging.BitmapFrame::Create_0`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf43b0`

## callees

- `0xf4330`
- `0xf43c0`

## string_xrefs

- `0xf43c9`: `bitmapUri`

## pseudocode

```c

```

## disassembly

```asm
0xf43c0  ldarg.0
0xf43c1  ldnull
0xf43c2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xf43c7  brfalse.s loc_F43D4
0xf43c9  ldstr    aBitmapuri// "bitmapUri"
0xf43ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf43d3  throw
0xf43d4  ldnull
0xf43d5  ldarg.0
0xf43d6  ldnull
0xf43d7  ldc.i4.0
0xf43d8  ldc.i4.0
0xf43d9  ldarg.1
0xf43da  call     class System.Windows.Media.Imaging.BitmapFrame System.Windows.Media.Imaging.BitmapFrame::CreateFromUriOrStream(class [System]System.Uri baseUri, class [System]System.Uri uri, class [mscorlib]System.IO.Stream stream, valuetype System.Windows.Media.Imaging.BitmapCreateOptions createOptions, valuetype System.Windows.Media.Imaging.BitmapCacheOption cacheOption, class [System]System.Net.Cache.RequestCachePolicy uriCachePolicy)
0xf43df  ret
```
