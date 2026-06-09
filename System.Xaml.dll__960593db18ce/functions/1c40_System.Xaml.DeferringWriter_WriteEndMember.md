# System.Xaml.DeferringWriter::WriteEndMember

- ea: `0x1c40`
- end: `0x1cca`
- name: `System.Xaml.DeferringWriter::WriteEndMember`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1c40`
- `0x8750`
- `0xf380`
- `0x11f50`

## string_xrefs

- `0x1c66`: `TemplateNotCollected`
- `0x1c73`: `WriteEndMember`
- `0x1cb8`: `WriteEndMember`

## pseudocode

```c

```

## disassembly

```asm
0x1c40  ldarg.0
0x1c41  ldc.i4.0
0x1c42  stfld    bool System.Xaml.DeferringWriter::_handled
0x1c47  ldarg.0
0x1c48  ldfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1c4d  stloc.0
0x1c4e  ldloc.0
0x1c4f  switch   loc_1CC9, loc_1C97, loc_1C84, loc_1C66
0x1c64  br.s     loc_1C97
0x1c66  ldstr    aTemplatenotcol// "TemplateNotCollected"
0x1c6b  ldc.i4.1
0x1c6c  newarr   [mscorlib]System.Object
0x1c71  dup
0x1c72  ldc.i4.0
0x1c73  ldstr    aWriteendmember// "WriteEndMember"
0x1c78  stelem.ref
0x1c79  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c7e  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1c83  throw
0x1c84  ldarg.0
0x1c85  ldfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1c8a  callvirt instance void System.Xaml.XamlWriter::WriteEndMember()
0x1c8f  ldarg.0
0x1c90  ldc.i4.1
0x1c91  stfld    bool System.Xaml.DeferringWriter::_handled
0x1c96  ret
0x1c97  ldstr    aMissingcase// "MissingCase"
0x1c9c  ldc.i4.2
0x1c9d  newarr   [mscorlib]System.Object
0x1ca2  dup
0x1ca3  ldc.i4.0
0x1ca4  ldarg.0
0x1ca5  ldflda   valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1caa  constrained. System.Xaml.DeferringMode
0x1cb0  callvirt instance string [mscorlib]System.Object::ToString()
0x1cb5  stelem.ref
0x1cb6  dup
0x1cb7  ldc.i4.1
0x1cb8  ldstr    aWriteendmember// "WriteEndMember"
0x1cbd  stelem.ref
0x1cbe  call     string System.Xaml.SR::Get(string id, object[] args)
0x1cc3  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1cc8  throw
0x1cc9  ret
```
