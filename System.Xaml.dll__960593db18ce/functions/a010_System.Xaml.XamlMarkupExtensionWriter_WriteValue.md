# System.Xaml.XamlMarkupExtensionWriter::WriteValue

- ea: `0xa010`
- end: `0xa038`
- name: `System.Xaml.XamlMarkupExtensionWriter::WriteValue`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0xa010`
- `0x11f20`
- `0x282e0`

## string_xrefs

- `0xa01a`: `XamlMarkupExtensionWriterCannotWriteNonstringValue`

## pseudocode

```c

```

## disassembly

```asm
0xa010  ldarg.1
0xa011  isinst   [mscorlib]System.String
0xa016  stloc.0
0xa017  ldloc.0
0xa018  brtrue.s loc_A02A
0xa01a  ldstr    aXamlmarkupexte_0// "XamlMarkupExtensionWriterCannotWriteNon"...
0xa01f  call     string System.Xaml.SR::Get(string id)
0xa024  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa029  throw
0xa02a  ldarg.0
0xa02b  ldfld    class WriterState System.Xaml.XamlMarkupExtensionWriter::currentState
0xa030  ldarg.0
0xa031  ldloc.0
0xa032  callvirt instance void WriterState::WriteValue(class System.Xaml.XamlMarkupExtensionWriter writer, string value)
0xa037  ret
```
