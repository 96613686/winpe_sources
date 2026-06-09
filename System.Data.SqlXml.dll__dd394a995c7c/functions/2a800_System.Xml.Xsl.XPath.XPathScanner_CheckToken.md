# System.Xml.Xsl.XPath.XPathScanner::CheckToken

- ea: `0x2a800`
- end: `0x2a84f`
- name: `System.Xml.Xsl.XPath.XPathScanner::CheckToken`
- size: `79`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1d4d0`
- `0x1d6e0`
- `0x288a0`
- `0x28d20`
- `0x291d0`
- `0x29300`
- `0x2a7f0`

## callees

- `0x29f60`
- `0x2a800`
- `0x2a850`
- `0x2a890`

## string_xrefs

- `0x2a80f`: `XPath_EofExpected`
- `0x2a82a`: `XPath_TokenExpected`

## pseudocode

```c

```

## disassembly

```asm
0x2a800  ldarg.0
0x2a801  ldfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a806  ldarg.1
0x2a807  beq.s    loc_2A84E
0x2a809  ldarg.1
0x2a80a  ldc.i4.s 0x17
0x2a80c  bne.un.s loc_2A829
0x2a80e  ldarg.0
0x2a80f  ldstr    aXpathEofexpect// "XPath_EofExpected"
0x2a814  ldc.i4.1
0x2a815  newarr   [mscorlib]System.String
0x2a81a  dup
0x2a81b  ldc.i4.0
0x2a81c  ldarg.0
0x2a81d  call     instance string System.Xml.Xsl.XPath.XPathScanner::get_RawValue()
0x2a822  stelem.ref
0x2a823  call     instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x2a828  throw
0x2a829  ldarg.0
0x2a82a  ldstr    aXpathTokenexpe// "XPath_TokenExpected"
0x2a82f  ldc.i4.2
0x2a830  newarr   [mscorlib]System.String
0x2a835  dup
0x2a836  ldc.i4.0
0x2a837  ldarg.0
0x2a838  ldarg.1
0x2a839  call     instance string System.Xml.Xsl.XPath.XPathScanner::LexKindToString(valuetype System.Xml.Xsl.XPath.LexKind t)
0x2a83e  stelem.ref
0x2a83f  dup
0x2a840  ldc.i4.1
0x2a841  ldarg.0
0x2a842  call     instance string System.Xml.Xsl.XPath.XPathScanner::get_RawValue()
0x2a847  stelem.ref
0x2a848  call     instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x2a84d  throw
0x2a84e  ret
```
