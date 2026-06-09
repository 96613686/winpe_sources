# System.Xml.Xsl.XsltOld.Stylesheet::AddTemplate

- ea: `0x10b90`
- end: `0x10c6e`
- name: `System.Xml.Xsl.XsltOld.Stylesheet::AddTemplate`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x6470`

## callees

- `0x10b90`
- `0x10f80`
- `0x10f90`
- `0x10fb0`
- `0x10fd0`
- `0x116e0`
- `0x11700`

## string_xrefs

- `0x10bcc`: `Xslt_DupTemplateName`

## pseudocode

```c

```

## disassembly

```asm
0x10b90  ldarg.1
0x10b91  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.TemplateAction::get_Mode()
0x10b96  stloc.0
0x10b97  ldarg.1
0x10b98  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.TemplateAction::get_Name()
0x10b9d  ldnull
0x10b9e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Inequality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x10ba3  brfalse.s loc_10BEB
0x10ba5  ldarg.0
0x10ba6  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.Stylesheet::templateNameTable
0x10bab  ldarg.1
0x10bac  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.TemplateAction::get_Name()
0x10bb1  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x10bb6  brtrue.s loc_10BCC
0x10bb8  ldarg.0
0x10bb9  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.Stylesheet::templateNameTable
0x10bbe  ldarg.1
0x10bbf  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.TemplateAction::get_Name()
0x10bc4  ldarg.1
0x10bc5  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x10bca  br.s     loc_10BEB
0x10bcc  ldstr    aXsltDuptemplat// "Xslt_DupTemplateName"
0x10bd1  ldc.i4.1
0x10bd2  newarr   [mscorlib]System.String
0x10bd7  dup
0x10bd8  ldc.i4.0
0x10bd9  ldarg.1
0x10bda  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.TemplateAction::get_Name()
0x10bdf  callvirt instance string [mscorlib]System.Object::ToString()
0x10be4  stelem.ref
0x10be5  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x10bea  throw
0x10beb  ldarg.1
0x10bec  callvirt instance int32 System.Xml.Xsl.XsltOld.TemplateAction::get_MatchKey()
0x10bf1  ldc.i4.m1
0x10bf2  beq.s    loc_10C6D
0x10bf4  ldarg.0
0x10bf5  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.Stylesheet::modeManagers
0x10bfa  brtrue.s loc_10C07
0x10bfc  ldarg.0
0x10bfd  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x10c02  stfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.Stylesheet::modeManagers
0x10c07  ldloc.0
0x10c08  ldnull
0x10c09  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x10c0e  brfalse.s loc_10C16
0x10c10  ldsfld   class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.XmlQualifiedName::Empty
0x10c15  stloc.0
0x10c16  ldarg.0
0x10c17  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.Stylesheet::modeManagers
0x10c1c  ldloc.0
0x10c1d  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x10c22  castclass System.Xml.Xsl.XsltOld.TemplateManager
0x10c27  stloc.1
0x10c28  ldloc.1
0x10c29  brtrue.s loc_10C4F
0x10c2b  ldarg.0
0x10c2c  ldloc.0
0x10c2d  newobj   instance void System.Xml.Xsl.XsltOld.TemplateManager::.ctor(class System.Xml.Xsl.XsltOld.Stylesheet stylesheet, class [System.Xml]System.Xml.XmlQualifiedName mode)
0x10c32  stloc.1
0x10c33  ldarg.0
0x10c34  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.Stylesheet::modeManagers
0x10c39  ldloc.0
0x10c3a  ldloc.1
0x10c3b  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x10c40  ldloc.0
0x10c41  callvirt instance bool [System.Xml]System.Xml.XmlQualifiedName::get_IsEmpty()
0x10c46  brfalse.s loc_10C4F
0x10c48  ldarg.0
0x10c49  ldloc.1
0x10c4a  stfld    class System.Xml.Xsl.XsltOld.TemplateManager System.Xml.Xsl.XsltOld.Stylesheet::templates
0x10c4f  ldarg.1
0x10c50  ldarg.0
0x10c51  ldarg.0
0x10c52  ldfld    int32 System.Xml.Xsl.XsltOld.Stylesheet::templateCount
0x10c57  ldc.i4.1
0x10c58  add
0x10c59  stloc.2
0x10c5a  ldloc.2
0x10c5b  stfld    int32 System.Xml.Xsl.XsltOld.Stylesheet::templateCount
0x10c60  ldloc.2
0x10c61  callvirt instance void System.Xml.Xsl.XsltOld.TemplateAction::set_TemplateId(int32 value)
0x10c66  ldloc.1
0x10c67  ldarg.1
0x10c68  callvirt instance void System.Xml.Xsl.XsltOld.TemplateManager::AddTemplate(class System.Xml.Xsl.XsltOld.TemplateAction template)
0x10c6d  ret
```
