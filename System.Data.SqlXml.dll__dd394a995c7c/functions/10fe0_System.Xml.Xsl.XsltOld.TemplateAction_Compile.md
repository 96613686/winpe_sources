# System.Xml.Xsl.XsltOld.TemplateAction::Compile

- ea: `0x10fe0`
- end: `0x11060`
- name: `System.Xml.Xsl.XsltOld.TemplateAction::Compile`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x54be0`

## callees

- `0x5900`
- `0x5b10`
- `0x5b20`
- `0x6480`
- `0x64b0`
- `0x7cc0`
- `0x10fe0`
- `0x11190`
- `0x11290`

## string_xrefs

- `0x10ffe`: `Xslt_TemplateNoAttrib`

## pseudocode

```c

```

## disassembly

```asm
0x10fe0  ldarg.0
0x10fe1  ldarg.1
0x10fe2  call     instance void System.Xml.Xsl.XsltOld.CompiledAction::CompileAttributes(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x10fe7  ldarg.0
0x10fe8  ldfld    int32 System.Xml.Xsl.XsltOld.TemplateAction::matchKey
0x10fed  ldc.i4.m1
0x10fee  bne.un.s loc_1102E
0x10ff0  ldarg.0
0x10ff1  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.TemplateAction::name
0x10ff6  ldnull
0x10ff7  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x10ffc  brfalse.s loc_1100F
0x10ffe  ldstr    aXsltTemplateno// "Xslt_TemplateNoAttrib"
0x11003  ldc.i4.0
0x11004  newarr   [mscorlib]System.String
0x11009  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x1100e  throw
0x1100f  ldarg.0
0x11010  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.TemplateAction::mode
0x11015  ldnull
0x11016  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Inequality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x1101b  brfalse.s loc_1102E
0x1101d  ldstr    aXsltInvalidmod// "Xslt_InvalidModeAttribute"
0x11022  ldc.i4.0
0x11023  newarr   [mscorlib]System.String
0x11028  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x1102d  throw
0x1102e  ldarg.1
0x1102f  ldarg.0
0x11030  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::BeginTemplate(class System.Xml.Xsl.XsltOld.TemplateAction template)
0x11035  ldarg.1
0x11036  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Recurse()
0x1103b  brfalse.s loc_11052
0x1103d  ldarg.0
0x1103e  ldarg.1
0x1103f  call     instance void System.Xml.Xsl.XsltOld.TemplateAction::CompileParameters(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x11044  ldarg.0
0x11045  ldarg.1
0x11046  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileTemplate(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x1104b  ldarg.1
0x1104c  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::ToParent()
0x11051  pop
0x11052  ldarg.1
0x11053  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::EndTemplate()
0x11058  ldarg.0
0x11059  ldarg.1
0x1105a  call     instance void System.Xml.Xsl.XsltOld.TemplateAction::AnalyzePriority(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x1105f  ret
```
