# System.Xml.Xsl.XPath.XPathScanner::ScanNumber

- ea: `0x2a6b0`
- end: `0x2a73f`
- name: `System.Xml.Xsl.XPath.XPathScanner::ScanNumber`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x2a000`

## callees

- `0x29ef0`
- `0x29ff0`
- `0x2a6b0`
- `0x2a890`

## string_xrefs

- `0x2a72d`: `XPath_ScientificNotation`

## pseudocode

```c

```

## disassembly

```asm
0x2a6b0  br.s     loc_2A6B8
0x2a6b2  ldarg.0
0x2a6b3  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a6b8  ldarg.0
0x2a6b9  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a6be  call     bool System.Xml.Xsl.XPath.XPathScanner::IsAsciiDigit(char ch)
0x2a6c3  brtrue.s loc_2A6B2
0x2a6c5  ldarg.0
0x2a6c6  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a6cb  ldc.i4.s 0x2E
0x2a6cd  bne.un.s loc_2A6EA
0x2a6cf  ldarg.0
0x2a6d0  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a6d5  br.s     loc_2A6DD
0x2a6d7  ldarg.0
0x2a6d8  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a6dd  ldarg.0
0x2a6de  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a6e3  call     bool System.Xml.Xsl.XPath.XPathScanner::IsAsciiDigit(char ch)
0x2a6e8  brtrue.s loc_2A6D7
0x2a6ea  ldarg.0
0x2a6eb  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a6f0  ldc.i4.s 0xDF
0x2a6f2  and
0x2a6f3  ldc.i4.s 0x45
0x2a6f5  bne.un.s loc_2A73E
0x2a6f7  ldarg.0
0x2a6f8  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a6fd  ldarg.0
0x2a6fe  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a703  ldc.i4.s 0x2B
0x2a705  beq.s    loc_2A711
0x2a707  ldarg.0
0x2a708  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a70d  ldc.i4.s 0x2D
0x2a70f  bne.un.s loc_2A71F
0x2a711  ldarg.0
0x2a712  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a717  br.s     loc_2A71F
0x2a719  ldarg.0
0x2a71a  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a71f  ldarg.0
0x2a720  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a725  call     bool System.Xml.Xsl.XPath.XPathScanner::IsAsciiDigit(char ch)
0x2a72a  brtrue.s loc_2A719
0x2a72c  ldarg.0
0x2a72d  ldstr    aXpathScientifi// "XPath_ScientificNotation"
0x2a732  ldc.i4.0
0x2a733  newarr   [mscorlib]System.String
0x2a738  call     instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x2a73d  throw
0x2a73e  ret
```
