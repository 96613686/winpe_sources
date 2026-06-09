# System.Windows.Markup.BamlWriter::VerifyWriteState

- ea: `0x9b0e0`
- end: `0x9b111`
- name: `System.Windows.Markup.BamlWriter::VerifyWriteState`
- size: `49`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x9a4c0`
- `0x9a4e0`
- `0x9a5a0`
- `0x9a610`
- `0x9a8a0`
- `0x9a930`
- `0x9aad0`
- `0x9ab00`
- `0x9acc0`
- `0x9adf0`
- `0x9ae20`
- `0x9ae80`
- `0x9b120`

## callees

- `0x38c40`
- `0x9b0e0`

## string_xrefs

- `0x9b0e8`: `BamlWriterClosed`
- `0x9b100`: `BamlWriterStartDoc`

## pseudocode

```c

```

## disassembly

```asm
0x9b0e0  ldarg.0
0x9b0e1  ldfld    bool System.Windows.Markup.BamlWriter::_closed
0x9b0e6  brfalse.s loc_9B0F8
0x9b0e8  ldstr    aBamlwriterclos// "BamlWriterClosed"
0x9b0ed  call     string System.Windows.SR::Get(string id)
0x9b0f2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9b0f7  throw
0x9b0f8  ldarg.0
0x9b0f9  ldfld    bool System.Windows.Markup.BamlWriter::_startDocumentWritten
0x9b0fe  brtrue.s loc_9B110
0x9b100  ldstr    aBamlwriterstar// "BamlWriterStartDoc"
0x9b105  call     string System.Windows.SR::Get(string id)
0x9b10a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9b10f  throw
0x9b110  ret
```
