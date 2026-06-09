# System.Xaml.DeferringWriter::SetLineInfo

- ea: `0x1e80`
- end: `0x1f0d`
- name: `System.Xaml.DeferringWriter::SetLineInfo`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x3ad0`

## callees

- `0x1e80`
- `0x1f20`
- `0x6760`
- `0x8750`
- `0x11f50`

## string_xrefs

- `0x1ea0`: `TemplateNotCollected`

## pseudocode

```c

```

## disassembly

```asm
0x1e80  ldarg.0
0x1e81  ldfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1e86  stloc.0
0x1e87  ldloc.0
0x1e88  switch   loc_1E9F, loc_1EBE, loc_1EC4, loc_1EA0
0x1e9d  br.s     loc_1EDA
0x1e9f  ret
0x1ea0  ldstr    aTemplatenotcol// "TemplateNotCollected"
0x1ea5  ldc.i4.1
0x1ea6  newarr   [mscorlib]System.Object
0x1eab  dup
0x1eac  ldc.i4.0
0x1ead  ldstr    aSetlineinfo// "SetLineInfo"
0x1eb2  stelem.ref
0x1eb3  call     string System.Xaml.SR::Get(string id, object[] args)
0x1eb8  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1ebd  throw
0x1ebe  ldarg.0
0x1ebf  call     instance void System.Xaml.DeferringWriter::StartDeferredList()
0x1ec4  ldarg.0
0x1ec5  ldfld    class System.Xaml.IXamlLineInfoConsumer System.Xaml.DeferringWriter::_deferredLineInfoConsumer
0x1eca  brfalse.s loc_1F0C
0x1ecc  ldarg.0
0x1ecd  ldfld    class System.Xaml.IXamlLineInfoConsumer System.Xaml.DeferringWriter::_deferredLineInfoConsumer
0x1ed2  ldarg.1
0x1ed3  ldarg.2
0x1ed4  callvirt instance void System.Xaml.IXamlLineInfoConsumer::SetLineInfo(int32 lineNumber, int32 linePosition)
0x1ed9  ret
0x1eda  ldstr    aMissingcase// "MissingCase"
0x1edf  ldc.i4.2
0x1ee0  newarr   [mscorlib]System.Object
0x1ee5  dup
0x1ee6  ldc.i4.0
0x1ee7  ldarg.0
0x1ee8  ldflda   valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1eed  constrained. System.Xaml.DeferringMode
0x1ef3  callvirt instance string [mscorlib]System.Object::ToString()
0x1ef8  stelem.ref
0x1ef9  dup
0x1efa  ldc.i4.1
0x1efb  ldstr    aSetlineinfo// "SetLineInfo"
0x1f00  stelem.ref
0x1f01  call     string System.Xaml.SR::Get(string id, object[] args)
0x1f06  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1f0b  throw
0x1f0c  ret
```
