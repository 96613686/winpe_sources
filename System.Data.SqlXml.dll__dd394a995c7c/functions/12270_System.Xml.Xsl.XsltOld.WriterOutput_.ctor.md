# System.Xml.Xsl.XsltOld.WriterOutput::.ctor

- ea: `0x12270`
- end: `0x12293`
- name: `System.Xml.Xsl.XsltOld.WriterOutput::.ctor`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xca40`

## callees

- `0x12270`

## string_xrefs

- `0x12279`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x12270  ldarg.0
0x12271  call     instance void [mscorlib]System.Object::.ctor()
0x12276  ldarg.2
0x12277  brtrue.s loc_12284
0x12279  ldstr    aWriter// "writer"
0x1227e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12283  throw
0x12284  ldarg.0
0x12285  ldarg.2
0x12286  stfld    class [System.Xml]System.Xml.XmlWriter System.Xml.Xsl.XsltOld.WriterOutput::writer
0x1228b  ldarg.0
0x1228c  ldarg.1
0x1228d  stfld    class System.Xml.Xsl.XsltOld.Processor System.Xml.Xsl.XsltOld.WriterOutput::processor
0x12292  ret
```
