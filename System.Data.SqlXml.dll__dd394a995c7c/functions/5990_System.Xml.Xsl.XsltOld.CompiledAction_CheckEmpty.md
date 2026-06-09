# System.Xml.Xsl.XsltOld.CompiledAction::CheckEmpty

- ea: `0x5990`
- end: `0x59e1`
- name: `System.Xml.Xsl.XsltOld.CompiledAction::CheckEmpty`
- size: `81`
- prototype: ``
- caller_count: `11`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4700`
- `0x73a0`
- `0x7430`
- `0x7660`
- `0x78e0`
- `0x79c0`
- `0x8b40`
- `0xafe0`
- `0x10300`
- `0x11c50`
- `0x13120`

## callees

- `0x5990`
- `0x5af0`
- `0x5b00`
- `0x5b10`
- `0x5b20`
- `0xa930`
- `0xa940`

## string_xrefs

- `0x59bc`: `Xslt_NotEmptyContents`

## pseudocode

```c

```

## disassembly

```asm
0x5990  ldarg.1
0x5991  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x5996  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_Name()
0x599b  stloc.0
0x599c  ldarg.1
0x599d  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Recurse()
0x59a2  brfalse.s loc_59E0
0x59a4  ldarg.1
0x59a5  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x59aa  callvirt instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.XsltOld.NavigatorInput::get_NodeType()
0x59af  stloc.1
0x59b0  ldloc.1
0x59b1  ldc.i4.6
0x59b2  beq.s    loc_59D1
0x59b4  ldloc.1
0x59b5  ldc.i4.8
0x59b6  beq.s    loc_59D1
0x59b8  ldloc.1
0x59b9  ldc.i4.7
0x59ba  beq.s    loc_59D1
0x59bc  ldstr    aXsltNotemptyco// "Xslt_NotEmptyContents"
0x59c1  ldc.i4.1
0x59c2  newarr   [mscorlib]System.String
0x59c7  dup
0x59c8  ldc.i4.0
0x59c9  ldloc.0
0x59ca  stelem.ref
0x59cb  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x59d0  throw
0x59d1  ldarg.1
0x59d2  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Advance()
0x59d7  brtrue.s loc_59A4
0x59d9  ldarg.1
0x59da  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::ToParent()
0x59df  pop
0x59e0  ret
```
