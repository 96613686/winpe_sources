# System.Xml.Xsl.XPath.XPathQilFactory::EnsureNodeSet

- ea: `0x29b30`
- end: `0x29b4e`
- name: `System.Xml.Xsl.XPath.XPathQilFactory::EnsureNodeSet`
- size: `30`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x27600`
- `0x279e0`
- `0x27b40`
- `0x29780`

## callees

- `0x286e0`
- `0x29b00`
- `0x29b30`

## string_xrefs

- `0x29b3b`: `XPath_NodeSetExpected`

## pseudocode

```c

```

## disassembly

```asm
0x29b30  ldarg.0
0x29b31  ldarg.1
0x29b32  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::TryEnsureNodeSet(class System.Xml.Xsl.Qil.QilNode n)
0x29b37  stloc.0
0x29b38  ldloc.0
0x29b39  brtrue.s loc_29B4C
0x29b3b  ldstr    aXpathNodesetex// "XPath_NodeSetExpected"
0x29b40  ldc.i4.0
0x29b41  newarr   [mscorlib]System.String
0x29b46  newobj   instance void System.Xml.Xsl.XPath.XPathCompileException::.ctor(string resId, string[] args)
0x29b4b  throw
0x29b4c  ldloc.0
0x29b4d  ret
```
