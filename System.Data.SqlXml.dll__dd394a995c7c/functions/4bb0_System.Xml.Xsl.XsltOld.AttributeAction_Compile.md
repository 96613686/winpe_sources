# System.Xml.Xsl.XsltOld.AttributeAction::Compile

- ea: `0x4bb0`
- end: `0x4c4f`
- name: `System.Xml.Xsl.XsltOld.AttributeAction::Compile`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x544d0`

## callees

- `0x4ab0`
- `0x4bb0`
- `0x5900`
- `0x5970`
- `0x59f0`
- `0x5b10`
- `0x5b20`
- `0x5ee0`
- `0x7cc0`

## string_xrefs

- `0x4c01`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x4bb0  ldarg.0
0x4bb1  ldarg.1
0x4bb2  call     instance void System.Xml.Xsl.XsltOld.CompiledAction::CompileAttributes(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x4bb7  ldarg.0
0x4bb8  ldarg.1
0x4bb9  ldarg.0
0x4bba  ldfld    class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.AttributeAction::nameAvt
0x4bbf  ldstr    aName// "name"
0x4bc4  call     instance void System.Xml.Xsl.XsltOld.CompiledAction::CheckRequiredAttribute(class System.Xml.Xsl.XsltOld.Compiler compiler, object attrValue, string attrName)
0x4bc9  ldarg.0
0x4bca  ldarg.0
0x4bcb  ldflda   class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.AttributeAction::nameAvt
0x4bd0  call     string System.Xml.Xsl.XsltOld.CompiledAction::PrecalculateAvt(class System.Xml.Xsl.XsltOld.Avt& avt)
0x4bd5  stfld    string System.Xml.Xsl.XsltOld.AttributeAction::name
0x4bda  ldarg.0
0x4bdb  ldarg.0
0x4bdc  ldflda   class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.AttributeAction::nsAvt
0x4be1  call     string System.Xml.Xsl.XsltOld.CompiledAction::PrecalculateAvt(class System.Xml.Xsl.XsltOld.Avt& avt)
0x4be6  stfld    string System.Xml.Xsl.XsltOld.AttributeAction::nsUri
0x4beb  ldarg.0
0x4bec  ldfld    class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.AttributeAction::nameAvt
0x4bf1  brtrue.s loc_4C2C
0x4bf3  ldarg.0
0x4bf4  ldfld    class System.Xml.Xsl.XsltOld.Avt System.Xml.Xsl.XsltOld.AttributeAction::nsAvt
0x4bf9  brtrue.s loc_4C2C
0x4bfb  ldarg.0
0x4bfc  ldfld    string System.Xml.Xsl.XsltOld.AttributeAction::name
0x4c01  ldstr    aXmlns// "xmlns"
0x4c06  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x4c0b  brfalse.s loc_4C38
0x4c0d  ldarg.0
0x4c0e  ldarg.0
0x4c0f  ldfld    string System.Xml.Xsl.XsltOld.AttributeAction::name
0x4c14  ldarg.0
0x4c15  ldfld    string System.Xml.Xsl.XsltOld.AttributeAction::nsUri
0x4c1a  ldarg.1
0x4c1b  callvirt instance class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.Compiler::CloneScopeManager()
0x4c20  call     class System.Xml.Xsl.XsltOld.PrefixQName System.Xml.Xsl.XsltOld.AttributeAction::CreateAttributeQName(string name, string nsUri, class System.Xml.Xsl.XsltOld.InputScopeManager manager)
0x4c25  stfld    class System.Xml.Xsl.XsltOld.PrefixQName System.Xml.Xsl.XsltOld.AttributeAction::qname
0x4c2a  br.s     loc_4C38
0x4c2c  ldarg.0
0x4c2d  ldarg.1
0x4c2e  callvirt instance class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.Compiler::CloneScopeManager()
0x4c33  stfld    class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.AttributeAction::manager
0x4c38  ldarg.1
0x4c39  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Recurse()
0x4c3e  brfalse.s loc_4C4E
0x4c40  ldarg.0
0x4c41  ldarg.1
0x4c42  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileTemplate(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x4c47  ldarg.1
0x4c48  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::ToParent()
0x4c4d  pop
0x4c4e  ret
```
