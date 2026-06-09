# ErrorXPathExpression::CheckErrors

- ea: `0x543a0`
- end: `0x543cd`
- name: `ErrorXPathExpression::CheckErrors`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x543a0`: `Xslt_InvalidXPath`

## pseudocode

```c

```

## disassembly

```asm
0x543a0  ldstr    aXsltInvalidxpa// "Xslt_InvalidXPath"
0x543a5  ldc.i4.1
0x543a6  newarr   [mscorlib]System.String
0x543ab  dup
0x543ac  ldc.i4.0
0x543ad  ldarg.0
0x543ae  callvirt instance string [System.Xml]System.Xml.XPath.XPathExpression::get_Expression()
0x543b3  stelem.ref
0x543b4  ldarg.0
0x543b5  ldfld    string ErrorXPathExpression::baseUri
0x543ba  ldarg.0
0x543bb  ldfld    int32 ErrorXPathExpression::linePosition
0x543c0  ldarg.0
0x543c1  ldfld    int32 ErrorXPathExpression::lineNumber
0x543c6  ldnull
0x543c7  newobj   instance void [System.Xml]System.Xml.Xsl.XsltException::.ctor(string, string[], string, int32, int32, class [mscorlib]System.Exception)
0x543cc  throw
```
