# System.Xml.Xsl.XsltOld.CompiledAction::CompileAttributes

- ea: `0x5900`
- end: `0x596a`
- name: `System.Xml.Xsl.XsltOld.CompiledAction::CompileAttributes`
- size: `106`
- prototype: ``
- caller_count: `21`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4800`
- `0x4bb0`
- `0x4dc0`
- `0x5500`
- `0x56f0`
- `0x5850`
- `0x84a0`
- `0x8b40`
- `0x91c0`
- `0x9480`
- `0xa0e0`
- `0xa640`
- `0xafe0`
- `0xc200`
- `0x10300`
- `0x10fe0`
- `0x117c0`
- `0x11c50`
- `0x11ea0`
- `0x12150`
- `0x13120`

## callees

- `0x58f0`
- `0x5900`
- `0x5af0`
- `0x5ca0`
- `0xa8f0`
- `0xa950`
- `0xa960`
- `0xa9b0`
- `0xa9c0`

## pseudocode

```c

```

## disassembly

```asm
0x5900  ldarg.1
0x5901  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x5906  stloc.0
0x5907  ldloc.0
0x5908  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x590d  stloc.1
0x590e  ldloc.0
0x590f  callvirt instance bool System.Xml.Xsl.XsltOld.NavigatorInput::MoveToFirstAttribute()
0x5914  brfalse.s loc_5969
0x5916  ldloc.0
0x5917  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_NamespaceURI()
0x591c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5921  brtrue.s loc_595A
0x5923  nop
0x5924  ldarg.0
0x5925  ldarg.1
0x5926  callvirt instance bool System.Xml.Xsl.XsltOld.CompiledAction::CompileAttribute(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x592b  brtrue.s loc_594B
0x592d  ldstr    aXsltInvalidatt// "Xslt_InvalidAttribute"
0x5932  ldc.i4.2
0x5933  newarr   [mscorlib]System.String
0x5938  dup
0x5939  ldc.i4.0
0x593a  ldloc.0
0x593b  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x5940  stelem.ref
0x5941  dup
0x5942  ldc.i4.1
0x5943  ldloc.1
0x5944  stelem.ref
0x5945  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x594a  throw
0x594b  leave.s  loc_595A
0x594d  pop
0x594e  ldarg.1
0x594f  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::get_ForwardCompatibility()
0x5954  brtrue.s loc_5958
0x5956  rethrow
0x5958  leave.s  loc_595A
0x595a  ldloc.0
0x595b  callvirt instance bool System.Xml.Xsl.XsltOld.NavigatorInput::MoveToNextAttribute()
0x5960  brtrue.s loc_5916
0x5962  ldloc.0
0x5963  callvirt instance bool System.Xml.Xsl.XsltOld.NavigatorInput::ToParent()
0x5968  pop
0x5969  ret
```
