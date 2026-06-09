# System.Xml.Xsl.XsltOld.Processor::StartQuery

- ea: `0xcdb0`
- end: `0xcde6`
- name: `System.Xml.Xsl.XsltOld.Processor::StartQuery`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x4990`
- `0x9510`

## callees

- `0xcb80`
- `0xcdb0`

## string_xrefs

- `0xcdd5`: `XPath_NodeSetExpected`

## pseudocode

```c

```

## disassembly

```asm
0xcdb0  ldarg.0
0xcdb1  ldarg.2
0xcdb2  call     instance class [System.Xml]MS.Internal.Xml.XPath.Query System.Xml.Xsl.XsltOld.Processor::GetCompiledQuery(int32 key)
0xcdb7  stloc.0
0xcdb8  ldloc.0
0xcdb9  ldarg.1
0xcdba  callvirt instance object [System.Xml]MS.Internal.Xml.XPath.Query::Evaluate(class [System.Xml]System.Xml.XPath.XPathNodeIterator)
0xcdbf  stloc.1
0xcdc0  ldloc.1
0xcdc1  isinst   [System.Xml]System.Xml.XPath.XPathNodeIterator
0xcdc6  brfalse.s loc_CDD5
0xcdc8  ldarg.1
0xcdc9  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0xcdce  ldloc.0
0xcdcf  newobj   instance void [System.Xml]MS.Internal.Xml.XPath.XPathSelectionIterator::.ctor(class [System.Xml]System.Xml.XPath.XPathNavigator, class [System.Xml]MS.Internal.Xml.XPath.Query)
0xcdd4  ret
0xcdd5  ldstr    aXpathNodesetex// "XPath_NodeSetExpected"
0xcdda  ldc.i4.0
0xcddb  newarr   [mscorlib]System.String
0xcde0  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0xcde5  throw
```
