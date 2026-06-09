# System.Windows.Media.Imaging.BitmapFrame::Create_2

- ea: `0xf43f0`
- end: `0xf4410`
- name: `System.Windows.Media.Imaging.BitmapFrame::Create_2`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf43e0`

## callees

- `0xf4330`
- `0xf43f0`

## string_xrefs

- `0xf43f9`: `bitmapUri`

## pseudocode

```c

```

## disassembly

```asm
0xf43f0  ldarg.0
0xf43f1  ldnull
0xf43f2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xf43f7  brfalse.s loc_F4404
0xf43f9  ldstr    aBitmapuri// "bitmapUri"
0xf43fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf4403  throw
0xf4404  ldnull
0xf4405  ldarg.0
0xf4406  ldnull
0xf4407  ldarg.1
0xf4408  ldarg.2
0xf4409  ldarg.3
0xf440a  call     class System.Windows.Media.Imaging.BitmapFrame System.Windows.Media.Imaging.BitmapFrame::CreateFromUriOrStream(class [System]System.Uri baseUri, class [System]System.Uri uri, class [mscorlib]System.IO.Stream stream, valuetype System.Windows.Media.Imaging.BitmapCreateOptions createOptions, valuetype System.Windows.Media.Imaging.BitmapCacheOption cacheOption, class [System]System.Net.Cache.RequestCachePolicy uriCachePolicy)
0xf440f  ret
```
