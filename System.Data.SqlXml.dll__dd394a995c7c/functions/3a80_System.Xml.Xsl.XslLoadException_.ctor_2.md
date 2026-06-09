# System.Xml.Xsl.XslLoadException::.ctor_2

- ea: `0x3a80`
- end: `0x3aca`
- name: `System.Xml.Xsl.XslLoadException::.ctor_2`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x420`
- `0x3780`
- `0x3a80`
- `0x3ad0`

## string_xrefs

- `0x3a81`: `Xml_UserException`

## pseudocode

```c

```

## disassembly

```asm
0x3a80  ldarg.0
0x3a81  ldstr    aXmlUserexcepti// "Xml_UserException"
0x3a86  ldc.i4.1
0x3a87  newarr   [mscorlib]System.String
0x3a8c  dup
0x3a8d  ldc.i4.0
0x3a8e  ldarg.1
0x3a8f  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_ErrorText()
0x3a94  stelem.ref
0x3a95  call     instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x3a9a  ldarg.1
0x3a9b  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerError::get_Line()
0x3aa0  stloc.0
0x3aa1  ldarg.1
0x3aa2  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerError::get_Column()
0x3aa7  stloc.1
0x3aa8  ldloc.0
0x3aa9  brtrue.s loc_3AAF
0x3aab  ldc.i4.0
0x3aac  stloc.1
0x3aad  br.s     loc_3AB4
0x3aaf  ldloc.1
0x3ab0  brtrue.s loc_3AB4
0x3ab2  ldc.i4.1
0x3ab3  stloc.1
0x3ab4  ldarg.0
0x3ab5  ldarg.1
0x3ab6  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_FileName()
0x3abb  ldloc.0
0x3abc  ldloc.1
0x3abd  ldloc.0
0x3abe  ldloc.1
0x3abf  newobj   instance void System.Xml.Xsl.SourceLineInfo::.ctor(string uriString, int32 startLine, int32 startPos, int32 endLine, int32 endPos)
0x3ac4  call     instance void System.Xml.Xsl.XslLoadException::SetSourceLineInfo(class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x3ac9  ret
```
