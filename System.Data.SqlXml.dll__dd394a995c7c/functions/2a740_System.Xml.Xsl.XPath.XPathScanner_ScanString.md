# System.Xml.Xsl.XPath.XPathScanner::ScanString

- ea: `0x2a740`
- end: `0x2a7a2`
- name: `System.Xml.Xsl.XPath.XPathScanner::ScanString`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x2a000`

## callees

- `0x29ee0`
- `0x2a740`
- `0x2a890`

## string_xrefs

- `0x2a772`: `XPath_UnclosedString`

## pseudocode

```c

```

## disassembly

```asm
0x2a740  ldarg.0
0x2a741  ldfld    int32 System.Xml.Xsl.XPath.XPathScanner::curIndex
0x2a746  ldc.i4.1
0x2a747  add
0x2a748  stloc.0
0x2a749  ldarg.0
0x2a74a  ldfld    string System.Xml.Xsl.XPath.XPathScanner::xpathExpr
0x2a74f  ldarg.0
0x2a750  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a755  ldloc.0
0x2a756  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x2a75b  stloc.1
0x2a75c  ldloc.1
0x2a75d  ldc.i4.0
0x2a75e  bge.s    loc_2A783
0x2a760  ldarg.0
0x2a761  ldarg.0
0x2a762  ldfld    string System.Xml.Xsl.XPath.XPathScanner::xpathExpr
0x2a767  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2a76c  call     instance void System.Xml.Xsl.XPath.XPathScanner::SetSourceIndex(int32 index)
0x2a771  ldarg.0
0x2a772  ldstr    aXpathUncloseds// "XPath_UnclosedString"
0x2a777  ldc.i4.0
0x2a778  newarr   [mscorlib]System.String
0x2a77d  call     instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x2a782  throw
0x2a783  ldarg.0
0x2a784  ldarg.0
0x2a785  ldfld    string System.Xml.Xsl.XPath.XPathScanner::xpathExpr
0x2a78a  ldloc.0
0x2a78b  ldloc.1
0x2a78c  ldloc.0
0x2a78d  sub
0x2a78e  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2a793  stfld    string System.Xml.Xsl.XPath.XPathScanner::stringValue
0x2a798  ldarg.0
0x2a799  ldloc.1
0x2a79a  ldc.i4.1
0x2a79b  add
0x2a79c  call     instance void System.Xml.Xsl.XPath.XPathScanner::SetSourceIndex(int32 index)
0x2a7a1  ret
```
