# System.Windows.Media.Imaging.BitmapDecoder::Create_0

- ea: `0xf22f0`
- end: `0xf2311`
- name: `System.Windows.Media.Imaging.BitmapDecoder::Create_0`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf22e0`

## callees

- `0xf20c0`
- `0xf22f0`

## string_xrefs

- `0xf22f9`: `bitmapUri`

## pseudocode

```c

```

## disassembly

```asm
0xf22f0  ldarg.0
0xf22f1  ldnull
0xf22f2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xf22f7  brfalse.s loc_F2304
0xf22f9  ldstr    aBitmapuri// "bitmapUri"
0xf22fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf2303  throw
0xf2304  ldnull
0xf2305  ldarg.0
0xf2306  ldnull
0xf2307  ldarg.1
0xf2308  ldarg.2
0xf2309  ldarg.3
0xf230a  ldc.i4.1
0xf230b  call     class System.Windows.Media.Imaging.BitmapDecoder System.Windows.Media.Imaging.BitmapDecoder::CreateFromUriOrStream(class [System]System.Uri baseUri, class [System]System.Uri uri, class [mscorlib]System.IO.Stream stream, valuetype System.Windows.Media.Imaging.BitmapCreateOptions createOptions, valuetype System.Windows.Media.Imaging.BitmapCacheOption cacheOption, class [System]System.Net.Cache.RequestCachePolicy uriCachePolicy, bool insertInDecoderCache)
0xf2310  ret
```
