# System.Xml.Xsl.Runtime.XmlQueryOutput::WriteNamespaceDeclaration

- ea: `0x2fcf0`
- end: `0x2fd88`
- name: `System.Xml.Xsl.Runtime.XmlQueryOutput::WriteNamespaceDeclaration`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x2fdd0`
- `0x30150`

## callees

- `0x3780`
- `0x2f9a0`
- `0x2fb40`
- `0x2fcf0`
- `0x2fff0`
- `0x303c0`

## string_xrefs

- `0x2fd30`: `XmlIl_NmspConflict`

## pseudocode

```c

```

## disassembly

```asm
0x2fcf0  ldarg.0
0x2fcf1  ldc.i4.3
0x2fcf2  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::ConstructInEnumAttrs(valuetype [System.Xml]System.Xml.XPath.XPathNodeType rootType)
0x2fcf7  ldarg.0
0x2fcf8  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Xml.Xsl.Runtime.XmlQueryOutput::nsmgr
0x2fcfd  brtrue.s loc_2FD09
0x2fcff  ldarg.0
0x2fd00  ldarg.1
0x2fd01  ldarg.2
0x2fd02  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteNamespaceDeclarationUnchecked(string prefix, string ns)
0x2fd07  br.s     loc_2FD6C
0x2fd09  ldarg.0
0x2fd0a  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Xml.Xsl.Runtime.XmlQueryOutput::nsmgr
0x2fd0f  ldarg.1
0x2fd10  callvirt instance string [System.Xml]System.Xml.XmlNamespaceManager::LookupNamespace(string)
0x2fd15  stloc.0
0x2fd16  ldarg.2
0x2fd17  ldloc.0
0x2fd18  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2fd1d  brfalse.s loc_2FD6C
0x2fd1f  ldloc.0
0x2fd20  brfalse.s loc_2FD64
0x2fd22  ldarg.0
0x2fd23  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xml.Xsl.Runtime.XmlQueryOutput::usedPrefixes
0x2fd28  ldarg.1
0x2fd29  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2fd2e  brfalse.s loc_2FD64
0x2fd30  ldstr    aXmlilNmspconfl// "XmlIl_NmspConflict"
0x2fd35  ldc.i4.4
0x2fd36  newarr   [mscorlib]System.String
0x2fd3b  dup
0x2fd3c  ldc.i4.0
0x2fd3d  ldarg.1
0x2fd3e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2fd43  brfalse.s loc_2FD4C
0x2fd45  ldstr    asc_58B56// ":"
0x2fd4a  br.s     loc_2FD51
0x2fd4c  ldstr    asc_580D4// ""
0x2fd51  stelem.ref
0x2fd52  dup
0x2fd53  ldc.i4.1
0x2fd54  ldarg.1
0x2fd55  stelem.ref
0x2fd56  dup
0x2fd57  ldc.i4.2
0x2fd58  ldarg.2
0x2fd59  stelem.ref
0x2fd5a  dup
0x2fd5b  ldc.i4.3
0x2fd5c  ldloc.0
0x2fd5d  stelem.ref
0x2fd5e  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2fd63  throw
0x2fd64  ldarg.0
0x2fd65  ldarg.1
0x2fd66  ldarg.2
0x2fd67  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::AddNamespace(string prefix, string ns)
0x2fd6c  ldarg.0
0x2fd6d  ldfld    int32 System.Xml.Xsl.Runtime.XmlQueryOutput::depth
0x2fd72  brtrue.s loc_2FD7A
0x2fd74  ldarg.0
0x2fd75  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::EndTree()
0x2fd7a  ldarg.0
0x2fd7b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xml.Xsl.Runtime.XmlQueryOutput::usedPrefixes
0x2fd80  ldarg.1
0x2fd81  ldarg.2
0x2fd82  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2fd87  ret
```
