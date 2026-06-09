# System.Xml.Xsl.XsltOld.Compiler::AddQuery_0

- ea: `0x64e0`
- end: `0x657a`
- name: `System.Xml.Xsl.XsltOld.Compiler::AddQuery_0`
- size: `154`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x64d0`
- `0x7530`
- `0xae20`
- `0x11060`
- `0x11090`

## callees

- `0x5af0`
- `0x5ca0`
- `0x64e0`
- `0xa910`
- `0xa920`
- `0xa9a0`
- `0x11af0`
- `0x54370`

## string_xrefs

- `0x6515`: `Xslt_InvalidXPath`

## pseudocode

```c

```

## disassembly

```asm
0x64e0  ldarg.s  4
0x64e2  brtrue.s loc_64F4
0x64e4  ldarg.0
0x64e5  ldfld    class [System.Xml]MS.Internal.Xml.XPath.QueryBuilder System.Xml.Xsl.XsltOld.Compiler::queryBuilder
0x64ea  ldarg.1
0x64eb  ldarg.2
0x64ec  ldarg.3
0x64ed  callvirt instance class [System.Xml]MS.Internal.Xml.XPath.Query [System.Xml]MS.Internal.Xml.XPath.QueryBuilder::Build(string, bool, bool)
0x64f2  br.s     loc_6502
0x64f4  ldarg.0
0x64f5  ldfld    class [System.Xml]MS.Internal.Xml.XPath.QueryBuilder System.Xml.Xsl.XsltOld.Compiler::queryBuilder
0x64fa  ldarg.1
0x64fb  ldarg.2
0x64fc  ldarg.3
0x64fd  callvirt instance class [System.Xml]MS.Internal.Xml.XPath.Query [System.Xml]MS.Internal.Xml.XPath.QueryBuilder::BuildPatternQuery(string, bool, bool)
0x6502  ldarg.1
0x6503  ldc.i4.0
0x6504  newobj   instance void [System.Xml]MS.Internal.Xml.XPath.CompiledXpathExpr::.ctor(class [System.Xml]MS.Internal.Xml.XPath.Query, string, bool)
0x6509  stloc.0
0x650a  leave.s  loc_6555
0x650c  stloc.1
0x650d  ldarg.0
0x650e  call     instance bool System.Xml.Xsl.XsltOld.Compiler::get_ForwardCompatibility()
0x6513  brtrue.s loc_652B
0x6515  ldstr    aXsltInvalidxpa// "Xslt_InvalidXPath"
0x651a  ldc.i4.1
0x651b  newarr   [mscorlib]System.String
0x6520  dup
0x6521  ldc.i4.0
0x6522  ldarg.1
0x6523  stelem.ref
0x6524  ldloc.1
0x6525  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[], class [mscorlib]System.Exception)
0x652a  throw
0x652b  ldarg.1
0x652c  ldarg.0
0x652d  call     instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x6532  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_BaseURI()
0x6537  ldarg.0
0x6538  call     instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x653d  callvirt instance int32 System.Xml.Xsl.XsltOld.NavigatorInput::get_LineNumber()
0x6542  ldarg.0
0x6543  call     instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x6548  callvirt instance int32 System.Xml.Xsl.XsltOld.NavigatorInput::get_LinePosition()
0x654d  newobj   instance void ErrorXPathExpression::.ctor(string expression, string baseUri, int32 lineNumber, int32 linePosition)
0x6552  stloc.0
0x6553  leave.s  loc_6555
0x6555  ldarg.0
0x6556  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.XsltOld.TheQuery> System.Xml.Xsl.XsltOld.Compiler::queryStore
0x655b  ldloc.0
0x655c  ldarg.0
0x655d  ldfld    class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.Compiler::scopeManager
0x6562  newobj   instance void System.Xml.Xsl.XsltOld.TheQuery::.ctor(class [System.Xml]MS.Internal.Xml.XPath.CompiledXpathExpr compiledQuery, class System.Xml.Xsl.XsltOld.InputScopeManager manager)
0x6567  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.XsltOld.TheQuery>::Add(var<u1>)
0x656c  ldarg.0
0x656d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.XsltOld.TheQuery> System.Xml.Xsl.XsltOld.Compiler::queryStore
0x6572  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.XsltOld.TheQuery>::get_Count()
0x6577  ldc.i4.1
0x6578  sub
0x6579  ret
```
