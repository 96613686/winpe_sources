# System.Windows.Media.SolidColorBrush::DeserializeFrom

- ea: `0x93cf0`
- end: `0x93d06`
- name: `System.Windows.Media.SolidColorBrush::DeserializeFrom`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x93cf0`
- `0x93d10`

## string_xrefs

- `0x93cf3`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0x93cf0  ldarg.0
0x93cf1  brtrue.s loc_93CFE
0x93cf3  ldstr    aReader// "reader"
0x93cf8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x93cfd  throw
0x93cfe  ldarg.0
0x93cff  ldnull
0x93d00  call     object System.Windows.Media.SolidColorBrush::DeserializeFrom(class [mscorlib]System.IO.BinaryReader reader, class [System]System.ComponentModel.ITypeDescriptorContext context)
0x93d05  ret
```
