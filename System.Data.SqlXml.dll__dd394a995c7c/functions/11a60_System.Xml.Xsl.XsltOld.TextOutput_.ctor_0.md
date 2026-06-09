# System.Xml.Xsl.XsltOld.TextOutput::.ctor_0

- ea: `0x11a60`
- end: `0x11a89`
- name: `System.Xml.Xsl.XsltOld.TextOutput::.ctor_0`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xc9e0`

## callees

- `0xf480`
- `0x11a60`

## string_xrefs

- `0x11a6a`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11a60  ldarg.0
0x11a61  ldarg.1
0x11a62  call     instance void System.Xml.Xsl.XsltOld.SequentialOutput::.ctor(class System.Xml.Xsl.XsltOld.Processor processor)
0x11a67  ldarg.2
0x11a68  brtrue.s loc_11A75
0x11a6a  ldstr    aWriter// "writer"
0x11a6f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11a74  throw
0x11a75  ldarg.0
0x11a76  ldarg.2
0x11a77  callvirt instance class [mscorlib]System.Text.Encoding [mscorlib]System.IO.TextWriter::get_Encoding()
0x11a7c  stfld    class [mscorlib]System.Text.Encoding System.Xml.Xsl.XsltOld.SequentialOutput::encoding
0x11a81  ldarg.0
0x11a82  ldarg.2
0x11a83  stfld    class [mscorlib]System.IO.TextWriter System.Xml.Xsl.XsltOld.TextOutput::writer
0x11a88  ret
```
