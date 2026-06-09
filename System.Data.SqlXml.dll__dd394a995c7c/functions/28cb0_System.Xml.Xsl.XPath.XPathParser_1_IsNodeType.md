# System.Xml.Xsl.XPath.XPathParser`1::IsNodeType

- ea: `0x28cb0`
- end: `0x28d08`
- name: `System.Xml.Xsl.XPath.XPathParser`1::IsNodeType`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x28cb0`
- `0x29f40`
- `0x29f50`

## string_xrefs

- `0x28cf9`: `comment`

## pseudocode

```c

```

## disassembly

```asm
0x28cb0  ldarg.0
0x28cb1  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_Prefix()
0x28cb6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x28cbb  brtrue.s loc_28D06
0x28cbd  ldarg.0
0x28cbe  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_Name()
0x28cc3  ldstr    aNode// "node"
0x28cc8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28ccd  brtrue.s loc_28D04
0x28ccf  ldarg.0
0x28cd0  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_Name()
0x28cd5  ldstr    aText// "text"
0x28cda  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28cdf  brtrue.s loc_28D04
0x28ce1  ldarg.0
0x28ce2  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_Name()
0x28ce7  ldstr    aProcessingInst// "processing-instruction"
0x28cec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28cf1  brtrue.s loc_28D04
0x28cf3  ldarg.0
0x28cf4  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_Name()
0x28cf9  ldstr    aComment// "comment"
0x28cfe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28d03  ret
0x28d04  ldc.i4.1
0x28d05  ret
0x28d06  ldc.i4.0
0x28d07  ret
```
