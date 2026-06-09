# System.Xaml.DeferringWriter::WriteEndObject

- ea: `0x1ad0`
- end: `0x1b89`
- name: `System.Xaml.DeferringWriter::WriteEndObject`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1ad0`
- `0x8750`
- `0xf360`
- `0xf4a0`
- `0x11f50`

## string_xrefs

- `0x1af6`: `TemplateNotCollected`
- `0x1b03`: `WriteEndObject`
- `0x1b77`: `WriteEndObject`

## pseudocode

```c

```

## disassembly

```asm
0x1ad0  ldarg.0
0x1ad1  ldc.i4.0
0x1ad2  stfld    bool System.Xaml.DeferringWriter::_handled
0x1ad7  ldarg.0
0x1ad8  ldfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1add  stloc.0
0x1ade  ldloc.0
0x1adf  switch   loc_1B88, loc_1B56, loc_1B14, loc_1AF6
0x1af4  br.s     loc_1B56
0x1af6  ldstr    aTemplatenotcol// "TemplateNotCollected"
0x1afb  ldc.i4.1
0x1afc  newarr   [mscorlib]System.Object
0x1b01  dup
0x1b02  ldc.i4.0
0x1b03  ldstr    aWriteendobject// "WriteEndObject"
0x1b08  stelem.ref
0x1b09  call     string System.Xaml.SR::Get(string id, object[] args)
0x1b0e  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1b13  throw
0x1b14  ldarg.0
0x1b15  ldfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1b1a  callvirt instance void System.Xaml.XamlWriter::WriteEndObject()
0x1b1f  ldarg.0
0x1b20  ldc.i4.1
0x1b21  stfld    bool System.Xaml.DeferringWriter::_handled
0x1b26  ldarg.0
0x1b27  ldarg.0
0x1b28  ldfld    int32 System.Xaml.DeferringWriter::_deferredTreeDepth
0x1b2d  ldc.i4.1
0x1b2e  sub
0x1b2f  stfld    int32 System.Xaml.DeferringWriter::_deferredTreeDepth
0x1b34  ldarg.0
0x1b35  ldfld    int32 System.Xaml.DeferringWriter::_deferredTreeDepth
0x1b3a  brtrue.s loc_1B88
0x1b3c  ldarg.0
0x1b3d  ldfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1b42  callvirt instance void System.Xaml.XamlWriter::Close()
0x1b47  ldarg.0
0x1b48  ldnull
0x1b49  stfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1b4e  ldarg.0
0x1b4f  ldc.i4.3
0x1b50  stfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1b55  ret
0x1b56  ldstr    aMissingcase// "MissingCase"
0x1b5b  ldc.i4.2
0x1b5c  newarr   [mscorlib]System.Object
0x1b61  dup
0x1b62  ldc.i4.0
0x1b63  ldarg.0
0x1b64  ldflda   valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1b69  constrained. System.Xaml.DeferringMode
0x1b6f  callvirt instance string [mscorlib]System.Object::ToString()
0x1b74  stelem.ref
0x1b75  dup
0x1b76  ldc.i4.1
0x1b77  ldstr    aWriteendobject// "WriteEndObject"
0x1b7c  stelem.ref
0x1b7d  call     string System.Xaml.SR::Get(string id, object[] args)
0x1b82  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1b87  throw
0x1b88  ret
```
