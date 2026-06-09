# System.Xml.Xsl.XsltOld.XsltCompileContext::ElementAvailable

- ea: `0x12b00`
- end: `0x12c2c`
- name: `System.Xml.Xsl.XsltOld.XsltCompileContext::ElementAvailable`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x55720`

## callees

- `0xa570`
- `0xc100`
- `0x12b00`

## string_xrefs

- `0x12b78`: `comment`
- `0x12b38`: `apply-templates`
- `0x12b58`: `call-template`
- `0x12b98`: `copy-of`

## pseudocode

```c

```

## disassembly

```asm
0x12b00  ldarg.1
0x12b01  ldloca.s 1
0x12b03  ldloca.s 0
0x12b05  call     void System.Xml.Xsl.XsltOld.PrefixQName::ParseQualifiedName(string qname, [out] string& prefix, [out] string& local)
0x12b0a  ldarg.0
0x12b0b  ldfld    class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.XsltCompileContext::manager
0x12b10  ldloc.1
0x12b11  callvirt instance string System.Xml.Xsl.XsltOld.InputScopeManager::ResolveXmlNamespace(string prefix)
0x12b16  stloc.2
0x12b17  ldloc.2
0x12b18  ldstr    aHttpWwwW3Org19// "http://www.w3.org/1999/XSL/Transform"
0x12b1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b22  brfalse  loc_12C2A
0x12b27  ldloc.0
0x12b28  ldstr    aApplyImports// "apply-imports"
0x12b2d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b32  brtrue   loc_12C28
0x12b37  ldloc.0
0x12b38  ldstr    aApplyTemplates// "apply-templates"
0x12b3d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b42  brtrue   loc_12C28
0x12b47  ldloc.0
0x12b48  ldstr    aAttribute// "attribute"
0x12b4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b52  brtrue   loc_12C28
0x12b57  ldloc.0
0x12b58  ldstr    aCallTemplate// "call-template"
0x12b5d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b62  brtrue   loc_12C28
0x12b67  ldloc.0
0x12b68  ldstr    aChoose// "choose"
0x12b6d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b72  brtrue   loc_12C28
0x12b77  ldloc.0
0x12b78  ldstr    aComment// "comment"
0x12b7d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b82  brtrue   loc_12C28
0x12b87  ldloc.0
0x12b88  ldstr    aCopy// "copy"
0x12b8d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12b92  brtrue   loc_12C28
0x12b97  ldloc.0
0x12b98  ldstr    aCopyOf// "copy-of"
0x12b9d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12ba2  brtrue   loc_12C28
0x12ba7  ldloc.0
0x12ba8  ldstr    aElement// "element"
0x12bad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12bb2  brtrue.s loc_12C28
0x12bb4  ldloc.0
0x12bb5  ldstr    aFallback// "fallback"
0x12bba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12bbf  brtrue.s loc_12C28
0x12bc1  ldloc.0
0x12bc2  ldstr    aForEach// "for-each"
0x12bc7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12bcc  brtrue.s loc_12C28
0x12bce  ldloc.0
0x12bcf  ldstr    aIf// "if"
0x12bd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12bd9  brtrue.s loc_12C28
0x12bdb  ldloc.0
0x12bdc  ldstr    aMessage// "message"
0x12be1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12be6  brtrue.s loc_12C28
0x12be8  ldloc.0
0x12be9  ldstr    aNumber// "number"
0x12bee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12bf3  brtrue.s loc_12C28
0x12bf5  ldloc.0
0x12bf6  ldstr    aProcessingInst// "processing-instruction"
0x12bfb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c00  brtrue.s loc_12C28
0x12c02  ldloc.0
0x12c03  ldstr    aText// "text"
0x12c08  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c0d  brtrue.s loc_12C28
0x12c0f  ldloc.0
0x12c10  ldstr    aValueOf// "value-of"
0x12c15  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c1a  brtrue.s loc_12C28
0x12c1c  ldloc.0
0x12c1d  ldstr    aVariable// "variable"
0x12c22  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c27  ret
0x12c28  ldc.i4.1
0x12c29  ret
0x12c2a  ldc.i4.0
0x12c2b  ret
```
