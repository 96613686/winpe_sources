# System.Xaml.DeferringWriter::WriteValue

- ea: `0x1cd0`
- end: `0x1d8b`
- name: `System.Xaml.DeferringWriter::WriteValue`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1cd0`
- `0x1f20`
- `0x8750`
- `0xf390`
- `0x11f50`

## string_xrefs

- `0x1cf6`: `TemplateNotCollected`
- `0x1d03`: `WriteValue`
- `0x1d79`: `WriteValue`

## pseudocode

```c

```

## disassembly

```asm
0x1cd0  ldarg.0
0x1cd1  ldc.i4.0
0x1cd2  stfld    bool System.Xaml.DeferringWriter::_handled
0x1cd7  ldarg.0
0x1cd8  ldfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1cdd  stloc.0
0x1cde  ldloc.0
0x1cdf  switch   loc_1D8A, loc_1D14, loc_1D44, loc_1CF6
0x1cf4  br.s     loc_1D58
0x1cf6  ldstr    aTemplatenotcol// "TemplateNotCollected"
0x1cfb  ldc.i4.1
0x1cfc  newarr   [mscorlib]System.Object
0x1d01  dup
0x1d02  ldc.i4.0
0x1d03  ldstr    aWritevalue// "WriteValue"
0x1d08  stelem.ref
0x1d09  call     string System.Xaml.SR::Get(string id, object[] args)
0x1d0e  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1d13  throw
0x1d14  ldarg.1
0x1d15  isinst   System.Xaml.XamlNodeList
0x1d1a  brfalse.s loc_1D37
0x1d1c  ldarg.0
0x1d1d  ldarg.1
0x1d1e  castclass System.Xaml.XamlNodeList
0x1d23  stfld    class System.Xaml.XamlNodeList System.Xaml.DeferringWriter::_deferredList
0x1d28  ldarg.0
0x1d29  ldc.i4.3
0x1d2a  stfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1d2f  ldarg.0
0x1d30  ldc.i4.1
0x1d31  stfld    bool System.Xaml.DeferringWriter::_handled
0x1d36  ret
0x1d37  ldarg.0
0x1d38  call     instance void System.Xaml.DeferringWriter::StartDeferredList()
0x1d3d  ldarg.0
0x1d3e  ldc.i4.2
0x1d3f  stfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1d44  ldarg.0
0x1d45  ldfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1d4a  ldarg.1
0x1d4b  callvirt instance void System.Xaml.XamlWriter::WriteValue(object value)
0x1d50  ldarg.0
0x1d51  ldc.i4.1
0x1d52  stfld    bool System.Xaml.DeferringWriter::_handled
0x1d57  ret
0x1d58  ldstr    aMissingcase// "MissingCase"
0x1d5d  ldc.i4.2
0x1d5e  newarr   [mscorlib]System.Object
0x1d63  dup
0x1d64  ldc.i4.0
0x1d65  ldarg.0
0x1d66  ldflda   valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1d6b  constrained. System.Xaml.DeferringMode
0x1d71  callvirt instance string [mscorlib]System.Object::ToString()
0x1d76  stelem.ref
0x1d77  dup
0x1d78  ldc.i4.1
0x1d79  ldstr    aWritevalue// "WriteValue"
0x1d7e  stelem.ref
0x1d7f  call     string System.Xaml.SR::Get(string id, object[] args)
0x1d84  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1d89  throw
0x1d8a  ret
```
