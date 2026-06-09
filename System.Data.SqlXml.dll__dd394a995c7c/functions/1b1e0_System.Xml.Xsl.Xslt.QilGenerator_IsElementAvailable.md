# System.Xml.Xsl.Xslt.QilGenerator::IsElementAvailable

- ea: `0x1b1e0`
- end: `0x1b301`
- name: `System.Xml.Xsl.Xslt.QilGenerator::IsElementAvailable`
- size: `289`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1bcc0`
- `0x351b0`

## callees

- `0x1b1e0`

## string_xrefs

- `0x1b24d`: `comment`
- `0x1b20d`: `apply-templates`
- `0x1b22d`: `call-template`
- `0x1b26d`: `copy-of`

## pseudocode

```c

```

## disassembly

```asm
0x1b1e0  ldarg.0
0x1b1e1  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1b1e6  ldstr    aHttpWwwW3Org19// "http://www.w3.org/1999/XSL/Transform"
0x1b1eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b1f0  brfalse  loc_1B2FF
0x1b1f5  ldarg.0
0x1b1f6  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1b1fb  stloc.0
0x1b1fc  ldloc.0
0x1b1fd  ldstr    aApplyImports// "apply-imports"
0x1b202  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b207  brtrue   loc_1B2FD
0x1b20c  ldloc.0
0x1b20d  ldstr    aApplyTemplates// "apply-templates"
0x1b212  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b217  brtrue   loc_1B2FD
0x1b21c  ldloc.0
0x1b21d  ldstr    aAttribute// "attribute"
0x1b222  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b227  brtrue   loc_1B2FD
0x1b22c  ldloc.0
0x1b22d  ldstr    aCallTemplate// "call-template"
0x1b232  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b237  brtrue   loc_1B2FD
0x1b23c  ldloc.0
0x1b23d  ldstr    aChoose// "choose"
0x1b242  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b247  brtrue   loc_1B2FD
0x1b24c  ldloc.0
0x1b24d  ldstr    aComment// "comment"
0x1b252  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b257  brtrue   loc_1B2FD
0x1b25c  ldloc.0
0x1b25d  ldstr    aCopy// "copy"
0x1b262  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b267  brtrue   loc_1B2FD
0x1b26c  ldloc.0
0x1b26d  ldstr    aCopyOf// "copy-of"
0x1b272  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b277  brtrue   loc_1B2FD
0x1b27c  ldloc.0
0x1b27d  ldstr    aElement// "element"
0x1b282  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b287  brtrue.s loc_1B2FD
0x1b289  ldloc.0
0x1b28a  ldstr    aFallback// "fallback"
0x1b28f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b294  brtrue.s loc_1B2FD
0x1b296  ldloc.0
0x1b297  ldstr    aForEach// "for-each"
0x1b29c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2a1  brtrue.s loc_1B2FD
0x1b2a3  ldloc.0
0x1b2a4  ldstr    aIf// "if"
0x1b2a9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2ae  brtrue.s loc_1B2FD
0x1b2b0  ldloc.0
0x1b2b1  ldstr    aMessage// "message"
0x1b2b6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2bb  brtrue.s loc_1B2FD
0x1b2bd  ldloc.0
0x1b2be  ldstr    aNumber// "number"
0x1b2c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2c8  brtrue.s loc_1B2FD
0x1b2ca  ldloc.0
0x1b2cb  ldstr    aProcessingInst// "processing-instruction"
0x1b2d0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2d5  brtrue.s loc_1B2FD
0x1b2d7  ldloc.0
0x1b2d8  ldstr    aText// "text"
0x1b2dd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2e2  brtrue.s loc_1B2FD
0x1b2e4  ldloc.0
0x1b2e5  ldstr    aValueOf// "value-of"
0x1b2ea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2ef  brtrue.s loc_1B2FD
0x1b2f1  ldloc.0
0x1b2f2  ldstr    aVariable// "variable"
0x1b2f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b2fc  ret
0x1b2fd  ldc.i4.1
0x1b2fe  ret
0x1b2ff  ldc.i4.0
0x1b300  ret
```
