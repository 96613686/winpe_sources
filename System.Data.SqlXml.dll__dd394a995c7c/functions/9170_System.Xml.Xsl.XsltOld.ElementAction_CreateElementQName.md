# System.Xml.Xsl.XsltOld.ElementAction::CreateElementQName

- ea: `0x9170`
- end: `0x91bf`
- name: `System.Xml.Xsl.XsltOld.ElementAction::CreateElementQName`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x91c0`
- `0x9300`

## callees

- `0x9170`
- `0xa570`
- `0xc0e0`
- `0xc1d0`

## string_xrefs

- `0x9171`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c

```

## disassembly

```asm
0x9170  ldarg.1
0x9171  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x9176  call     bool [mscorlib]System.String::op_Equality(string, string)
0x917b  brfalse.s loc_9192
0x917d  ldstr    aXsltReservedns// "Xslt_ReservedNS"
0x9182  ldc.i4.1
0x9183  newarr   [mscorlib]System.String
0x9188  dup
0x9189  ldc.i4.0
0x918a  ldarg.1
0x918b  stelem.ref
0x918c  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x9191  throw
0x9192  newobj   instance void System.Xml.Xsl.XsltOld.PrefixQName::.ctor()
0x9197  stloc.0
0x9198  ldloc.0
0x9199  ldarg.0
0x919a  callvirt instance void System.Xml.Xsl.XsltOld.PrefixQName::SetQName(string qname)
0x919f  ldarg.1
0x91a0  brtrue.s loc_91B6
0x91a2  ldloc.0
0x91a3  ldarg.2
0x91a4  ldloc.0
0x91a5  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Prefix
0x91aa  callvirt instance string System.Xml.Xsl.XsltOld.InputScopeManager::ResolveXmlNamespace(string prefix)
0x91af  stfld    string System.Xml.Xsl.XsltOld.PrefixQName::Namespace
0x91b4  br.s     loc_91BD
0x91b6  ldloc.0
0x91b7  ldarg.1
0x91b8  stfld    string System.Xml.Xsl.XsltOld.PrefixQName::Namespace
0x91bd  ldloc.0
0x91be  ret
```
