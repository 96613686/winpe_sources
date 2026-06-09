# System.Xml.Xsl.XsltOld.ElementAction::Compile

- ea: `0x91c0`
- end: `0x926e`
- name: `System.Xml.Xsl.XsltOld.ElementAction::Compile`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x54770`

## callees

- `0x5900`
- `0x5970`
- `0x59f0`
- `0x5b10`
- `0x5b20`
- `0x5ee0`
- `0x7cc0`
- `0x9170`
- `0x91c0`

## string_xrefs

- `0x9211`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x91c0  ldarg.0
0x91c1  ldarg.1
0x91c2  call     instance void System.Xml.Xsl.XsltOld.CompiledAction::CompileAttributes(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x91c7  ldarg.0
0x91c8  ldarg.1
0x91c9  ldarg.0
0x91ca  ldfld    class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.ElementAction::nameAvt
0x91cf  ldstr    aName// "name"
0x91d4  call     instance void System.Xml.Xsl.XsltOld.CompiledAction::CheckRequiredAttribute(class System.Xml.Xsl.XsltOld.Compiler compiler, object attrValue, string attrName)
0x91d9  ldarg.0
0x91da  ldarg.0
0x91db  ldflda   class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.ElementAction::nameAvt
0x91e0  call     string System.Xml.Xsl.XsltOld.CompiledAction::PrecalculateAvt(class System.Xml.Xsl.XsltOld.Avt& avt)
0x91e5  stfld    string System.Xml.Xsl.XsltOld.ElementAction::name
0x91ea  ldarg.0
0x91eb  ldarg.0
0x91ec  ldflda   class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.ElementAction::nsAvt
0x91f1  call     string System.Xml.Xsl.XsltOld.CompiledAction::PrecalculateAvt(class System.Xml.Xsl.XsltOld.Avt& avt)
0x91f6  stfld    string System.Xml.Xsl.XsltOld.ElementAction::nsUri
0x91fb  ldarg.0
0x91fc  ldfld    class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.ElementAction::nameAvt
0x9201  brtrue.s loc_923C
0x9203  ldarg.0
0x9204  ldfld    class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.ElementAction::nsAvt
0x9209  brtrue.s loc_923C
0x920b  ldarg.0
0x920c  ldfld    string System.Xml.Xsl.XsltOld.ElementAction::name
0x9211  ldstr    aXmlns// "xmlns"
0x9216  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x921b  brfalse.s loc_9248
0x921d  ldarg.0
0x921e  ldarg.0
0x921f  ldfld    string System.Xml.Xsl.XsltOld.ElementAction::name
0x9224  ldarg.0
0x9225  ldfld    string System.Xml.Xsl.XsltOld.ElementAction::nsUri
0x922a  ldarg.1
0x922b  callvirt instance class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.Compiler::CloneScopeManager()
0x9230  call     class System.Xml.Xsl.XsltOld.PrefixQName System.Xml.Xsl.XsltOld.ElementAction::CreateElementQName(string name, string nsUri, class System.Xml.Xsl.XsltOld.InputScopeManager manager)
0x9235  stfld    class System.Xml.Xsl.XsltOld.PrefixQName System.Xml.Xsl.XsltOld.ElementAction::qname
0x923a  br.s     loc_9248
0x923c  ldarg.0
0x923d  ldarg.1
0x923e  callvirt instance class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.Compiler::CloneScopeManager()
0x9243  stfld    class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.ElementAction::manager
0x9248  ldarg.1
0x9249  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Recurse()
0x924e  brfalse.s loc_925E
0x9250  ldarg.0
0x9251  ldarg.1
0x9252  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileTemplate(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x9257  ldarg.1
0x9258  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::ToParent()
0x925d  pop
0x925e  ldarg.0
0x925f  ldarg.0
0x9260  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.XsltOld.ContainerAction::containedActions
0x9265  ldnull
0x9266  ceq
0x9268  stfld    bool System.Xml.Xsl.XsltOld.ElementAction::empty
0x926d  ret
```
