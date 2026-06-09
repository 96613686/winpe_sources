# System.Xml.Xsl.XPath.XPathScanner::NextLex

- ea: `0x2a000`
- end: `0x2a3e9`
- name: `System.Xml.Xsl.XPath.XPathScanner::NextLex`
- size: `1001`
- prototype: ``
- caller_count: `17`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1d510`
- `0x1d550`
- `0x1d6e0`
- `0x1d820`
- `0x1d8f0`
- `0x1da60`
- `0x28940`
- `0x28a00`
- `0x28ad0`
- `0x28d20`
- `0x28e90`
- `0x28f80`
- `0x29030`
- `0x291d0`
- `0x29300`
- `0x29e60`
- `0x2a7f0`

## callees

- `0x29ee0`
- `0x29ef0`
- `0x29fd0`
- `0x29ff0`
- `0x2a000`
- `0x2a3f0`
- `0x2a4c0`
- `0x2a6b0`
- `0x2a740`
- `0x2a7b0`

## pseudocode

```c

```

## disassembly

```asm
0x2a000  ldarg.0
0x2a001  ldarg.0
0x2a002  ldfld    int32 System.Xml.Xsl.XPath.XPathScanner::curIndex
0x2a007  stfld    int32 System.Xml.Xsl.XPath.XPathScanner::prevLexEnd
0x2a00c  ldarg.0
0x2a00d  ldarg.0
0x2a00e  ldfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a013  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::prevKind
0x2a018  ldarg.0
0x2a019  call     instance void System.Xml.Xsl.XPath.XPathScanner::SkipSpace()
0x2a01e  ldarg.0
0x2a01f  ldarg.0
0x2a020  ldfld    int32 System.Xml.Xsl.XPath.XPathScanner::curIndex
0x2a025  stfld    int32 System.Xml.Xsl.XPath.XPathScanner::lexStart
0x2a02a  ldarg.0
0x2a02b  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a030  stloc.0
0x2a031  ldloc.0
0x2a032  ldc.i4.s 0x5B
0x2a034  bgt.un   loc_2A0D2
0x2a039  ldloc.0
0x2a03a  brfalse  loc_2A0E9
0x2a03f  ldloc.0
0x2a040  ldc.i4.s 0x21
0x2a042  sub
0x2a043  switch   loc_2A1EC, loc_2A25E, loc_2A27C, loc_2A0F2, loc_2A27C, loc_2A27C, loc_2A25E, loc_2A0F2, loc_2A0F2, loc_2A172, loc_2A1C0, loc_2A0F2, loc_2A1CF, loc_2A105, loc_2A189, loc_2A26D, loc_2A26D, loc_2A26D, loc_2A26D, loc_2A26D, loc_2A26D, loc_2A26D, loc_2A26D, loc_2A26D, loc_2A26D, loc_2A14B, loc_2A27C, loc_2A212, loc_2A1DE, loc_2A238, loc_2A27C, loc_2A0F2
0x2a0c8  ldloc.0
0x2a0c9  ldc.i4.s 0x5B
0x2a0cb  beq.s    loc_2A0F2
0x2a0cd  br       loc_2A27C
0x2a0d2  ldloc.0
0x2a0d3  ldc.i4.s 0x5D
0x2a0d5  beq.s    loc_2A0F2
0x2a0d7  ldloc.0
0x2a0d8  ldc.i4.s 0x7C
0x2a0da  beq      loc_2A1B1
0x2a0df  ldloc.0
0x2a0e0  ldc.i4.s 0x7D
0x2a0e2  beq.s    loc_2A0F2
0x2a0e4  br       loc_2A27C
0x2a0e9  ldarg.0
0x2a0ea  ldc.i4.s 0x17
0x2a0ec  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a0f1  ret
0x2a0f2  ldarg.0
0x2a0f3  ldarg.0
0x2a0f4  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a0f9  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a0fe  ldarg.0
0x2a0ff  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a104  ret
0x2a105  ldarg.0
0x2a106  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a10b  ldarg.0
0x2a10c  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a111  ldc.i4.s 0x2E
0x2a113  bne.un.s loc_2A124
0x2a115  ldarg.0
0x2a116  ldc.i4.s 0x10
0x2a118  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a11d  ldarg.0
0x2a11e  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a123  ret
0x2a124  ldarg.0
0x2a125  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a12a  call     bool System.Xml.Xsl.XPath.XPathScanner::IsAsciiDigit(char ch)
0x2a12f  brfalse.s loc_2A142
0x2a131  ldarg.0
0x2a132  ldarg.0
0x2a133  ldfld    int32 System.Xml.Xsl.XPath.XPathScanner::lexStart
0x2a138  call     instance void System.Xml.Xsl.XPath.XPathScanner::SetSourceIndex(int32 index)
0x2a13d  br       loc_2A26D
0x2a142  ldarg.0
0x2a143  ldc.i4.s 0x2E
0x2a145  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a14a  ret
0x2a14b  ldarg.0
0x2a14c  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a151  ldarg.0
0x2a152  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a157  ldc.i4.s 0x3A
0x2a159  bne.un.s loc_2A16A
0x2a15b  ldarg.0
0x2a15c  ldc.i4.s 0x11
0x2a15e  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a163  ldarg.0
0x2a164  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a169  ret
0x2a16a  ldarg.0
0x2a16b  ldc.i4.0
0x2a16c  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a171  ret
0x2a172  ldarg.0
0x2a173  ldc.i4.s 0x2A
0x2a175  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a17a  ldarg.0
0x2a17b  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a180  ldarg.0
0x2a181  ldc.i4.1
0x2a182  call     instance bool System.Xml.Xsl.XPath.XPathScanner::CheckOperator(bool star)
0x2a187  pop
0x2a188  ret
0x2a189  ldarg.0
0x2a18a  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a18f  ldarg.0
0x2a190  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a195  ldc.i4.s 0x2F
0x2a197  bne.un.s loc_2A1A8
0x2a199  ldarg.0
0x2a19a  ldc.i4.s 0x12
0x2a19c  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a1a1  ldarg.0
0x2a1a2  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a1a7  ret
0x2a1a8  ldarg.0
0x2a1a9  ldc.i4.s 0x2F
0x2a1ab  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a1b0  ret
0x2a1b1  ldarg.0
0x2a1b2  ldc.i4.s 0xF
0x2a1b4  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a1b9  ldarg.0
0x2a1ba  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a1bf  ret
0x2a1c0  ldarg.0
0x2a1c1  ldc.i4.s 9
0x2a1c3  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a1c8  ldarg.0
0x2a1c9  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a1ce  ret
0x2a1cf  ldarg.0
0x2a1d0  ldc.i4.s 0xA
0x2a1d2  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a1d7  ldarg.0
0x2a1d8  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a1dd  ret
0x2a1de  ldarg.0
0x2a1df  ldc.i4.3
0x2a1e0  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a1e5  ldarg.0
0x2a1e6  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a1eb  ret
0x2a1ec  ldarg.0
0x2a1ed  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a1f2  ldarg.0
0x2a1f3  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a1f8  ldc.i4.s 0x3D
0x2a1fa  bne.un.s loc_2A20A
0x2a1fc  ldarg.0
0x2a1fd  ldc.i4.4
0x2a1fe  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a203  ldarg.0
0x2a204  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a209  ret
0x2a20a  ldarg.0
0x2a20b  ldc.i4.0
0x2a20c  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a211  ret
0x2a212  ldarg.0
0x2a213  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a218  ldarg.0
0x2a219  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a21e  ldc.i4.s 0x3D
0x2a220  bne.un.s loc_2A230
0x2a222  ldarg.0
0x2a223  ldc.i4.6
0x2a224  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a229  ldarg.0
0x2a22a  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a22f  ret
0x2a230  ldarg.0
0x2a231  ldc.i4.5
0x2a232  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a237  ret
0x2a238  ldarg.0
0x2a239  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a23e  ldarg.0
0x2a23f  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a244  ldc.i4.s 0x3D
0x2a246  bne.un.s loc_2A256
0x2a248  ldarg.0
0x2a249  ldc.i4.8
0x2a24a  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a24f  ldarg.0
0x2a250  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a255  ret
0x2a256  ldarg.0
0x2a257  ldc.i4.7
0x2a258  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a25d  ret
0x2a25e  ldarg.0
0x2a25f  ldc.i4.s 0x16
0x2a261  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a266  ldarg.0
0x2a267  call     instance void System.Xml.Xsl.XPath.XPathScanner::ScanString()
0x2a26c  ret
0x2a26d  ldarg.0
0x2a26e  ldc.i4.s 0x13
0x2a270  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a275  ldarg.0
0x2a276  call     instance void System.Xml.Xsl.XPath.XPathScanner::ScanNumber()
0x2a27b  ret
0x2a27c  ldarg.0
0x2a27d  ldflda   valuetype [System.Xml]System.Xml.XmlCharType System.Xml.Xsl.XPath.XPathScanner::xmlCharType
0x2a282  ldarg.0
0x2a283  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a288  call     instance bool [System.Xml]System.Xml.XmlCharType::IsStartNCNameSingleChar(char)
0x2a28d  brfalse  loc_2A3DB
0x2a292  ldarg.0
0x2a293  ldc.i4.s 0x15
0x2a295  stfld    valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::kind
0x2a29a  ldarg.0
0x2a29b  ldarg.0
0x2a29c  call     instance string System.Xml.Xsl.XPath.XPathScanner::ScanNCName()
0x2a2a1  stfld    string System.Xml.Xsl.XPath.XPathScanner::name
0x2a2a6  ldarg.0
0x2a2a7  ldsfld   string [mscorlib]System.String::Empty
0x2a2ac  stfld    string System.Xml.Xsl.XPath.XPathScanner::prefix
0x2a2b1  ldarg.0
0x2a2b2  ldc.i4.0
0x2a2b3  stfld    bool System.Xml.Xsl.XPath.XPathScanner::canBeFunction
0x2a2b8  ldarg.0
0x2a2b9  ldc.i4.0
0x2a2ba  stfld    valuetype System.Xml.Xsl.XPath.XPathAxis System.Xml.Xsl.XPath.XPathScanner::axis
0x2a2bf  ldc.i4.0
0x2a2c0  stloc.1
0x2a2c1  ldarg.0
0x2a2c2  ldfld    int32 System.Xml.Xsl.XPath.XPathScanner::curIndex
0x2a2c7  stloc.2
0x2a2c8  ldarg.0
0x2a2c9  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a2ce  ldc.i4.s 0x3A
0x2a2d0  bne.un   loc_2A37F
0x2a2d5  ldarg.0
0x2a2d6  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a2db  ldarg.0
0x2a2dc  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a2e1  ldc.i4.s 0x3A
0x2a2e3  bne.un.s loc_2A2F9
0x2a2e5  ldarg.0
0x2a2e6  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a2eb  ldc.i4.1
0x2a2ec  stloc.1
0x2a2ed  ldarg.0
0x2a2ee  ldloc.2
0x2a2ef  call     instance void System.Xml.Xsl.XPath.XPathScanner::SetSourceIndex(int32 index)
0x2a2f4  br       loc_2A3C0
0x2a2f9  ldarg.0
0x2a2fa  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a2ff  ldc.i4.s 0x2A
0x2a301  bne.un.s loc_2A325
0x2a303  ldarg.0
0x2a304  call     instance void System.Xml.Xsl.XPath.XPathScanner::NextChar()
0x2a309  ldarg.0
0x2a30a  ldarg.0
0x2a30b  ldfld    string System.Xml.Xsl.XPath.XPathScanner::name
0x2a310  stfld    string System.Xml.Xsl.XPath.XPathScanner::prefix
0x2a315  ldarg.0
0x2a316  ldstr    asc_580B6// "*"
0x2a31b  stfld    string System.Xml.Xsl.XPath.XPathScanner::name
0x2a320  br       loc_2A3C0
0x2a325  ldarg.0
0x2a326  ldflda   valuetype [System.Xml]System.Xml.XmlCharType System.Xml.Xsl.XPath.XPathScanner::xmlCharType
0x2a32b  ldarg.0
0x2a32c  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a331  call     instance bool [System.Xml]System.Xml.XmlCharType::IsStartNCNameSingleChar(char)
0x2a336  brfalse.s loc_2A376
0x2a338  ldarg.0
0x2a339  ldarg.0
0x2a33a  ldfld    string System.Xml.Xsl.XPath.XPathScanner::name
0x2a33f  stfld    string System.Xml.Xsl.XPath.XPathScanner::prefix
0x2a344  ldarg.0
0x2a345  ldarg.0
0x2a346  call     instance string System.Xml.Xsl.XPath.XPathScanner::ScanNCName()
0x2a34b  stfld    string System.Xml.Xsl.XPath.XPathScanner::name
0x2a350  ldarg.0
0x2a351  ldfld    int32 System.Xml.Xsl.XPath.XPathScanner::curIndex
0x2a356  stloc.2
0x2a357  ldarg.0
0x2a358  call     instance void System.Xml.Xsl.XPath.XPathScanner::SkipSpace()
0x2a35d  ldarg.0
0x2a35e  ldarg.0
0x2a35f  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a364  ldc.i4.s 0x28
0x2a366  ceq
0x2a368  stfld    bool System.Xml.Xsl.XPath.XPathScanner::canBeFunction
0x2a36d  ldarg.0
0x2a36e  ldloc.2
0x2a36f  call     instance void System.Xml.Xsl.XPath.XPathScanner::SetSourceIndex(int32 index)
0x2a374  br.s     loc_2A3C0
0x2a376  ldarg.0
0x2a377  ldloc.2
0x2a378  call     instance void System.Xml.Xsl.XPath.XPathScanner::SetSourceIndex(int32 index)
0x2a37d  br.s     loc_2A3C0
0x2a37f  ldarg.0
0x2a380  call     instance void System.Xml.Xsl.XPath.XPathScanner::SkipSpace()
0x2a385  ldarg.0
0x2a386  ldfld    char System.Xml.Xsl.XPath.XPathScanner::curChar
0x2a38b  ldc.i4.s 0x3A
0x2a38d  bne.un.s loc_2A3B0
  ... truncated ...
```
