# System.Xml.Xsl.XsltOld.TextOnlyOutput::.ctor_0

- ea: `0x11990`
- end: `0x119b3`
- name: `System.Xml.Xsl.XsltOld.TextOnlyOutput::.ctor_0`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xa6a0`
- `0xc9e0`

## callees

- `0x11990`

## string_xrefs

- `0x11999`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11990  ldarg.0
0x11991  call     instance void [mscorlib]System.Object::.ctor()
0x11996  ldarg.2
0x11997  brtrue.s loc_119A4
0x11999  ldstr    aWriter// "writer"
0x1199e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x119a3  throw
0x119a4  ldarg.0
0x119a5  ldarg.1
0x119a6  stfld    class System.Xml.Xsl.XsltOld.Processor System.Xml.Xsl.XsltOld.TextOnlyOutput::processor
0x119ab  ldarg.0
0x119ac  ldarg.2
0x119ad  stfld    class [mscorlib]System.IO.TextWriter System.Xml.Xsl.XsltOld.TextOnlyOutput::writer
0x119b2  ret
```
