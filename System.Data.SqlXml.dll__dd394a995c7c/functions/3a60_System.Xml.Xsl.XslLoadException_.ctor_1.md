# System.Xml.Xsl.XslLoadException::.ctor_1

- ea: `0x3a60`
- end: `0x3a75`
- name: `System.Xml.Xsl.XslLoadException::.ctor_1`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16300`
- `0x215f0`

## callees

- `0x3760`
- `0x3ad0`

## string_xrefs

- `0x3a62`: `Xslt_CompileError2`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  ldarg.0
0x3a61  ldarg.1
0x3a62  ldstr    aXsltCompileerr// "Xslt_CompileError2"
0x3a67  ldnull
0x3a68  call     instance void System.Xml.Xsl.XslTransformException::.ctor(class [mscorlib]System.Exception inner, string res, string[] args)
0x3a6d  ldarg.0
0x3a6e  ldarg.2
0x3a6f  call     instance void System.Xml.Xsl.XslLoadException::SetSourceLineInfo(class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x3a74  ret
```
