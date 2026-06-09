# System.Xml.Xsl.XsltOld.AttributeAction::CreateAttributeQName

- ea: `0x4ab0`
- end: `0x4bae`
- name: `System.Xml.Xsl.XsltOld.AttributeAction::CreateAttributeQName`
- size: `254`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x4bb0`
- `0x4cb0`

## callees

- `0x4ab0`
- `0xa590`
- `0xc0d0`
- `0xc0e0`
- `0xc1d0`

## string_xrefs

- `0x4ab1`: `xmlns`
- `0x4b6e`: `xmlns`
- `0x4ac0`: `http://www.w3.org/2000/xmlns/`
- `0x4b80`: `http://www.w3.org/2000/xmlns/`
- `0x4b30`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x4ab0  ldarg.0
0x4ab1  ldstr    aXmlns// "xmlns"
0x4ab6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4abb  brfalse.s loc_4ABF
0x4abd  ldnull
0x4abe  ret
0x4abf  ldarg.1
0x4ac0  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x4ac5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4aca  brfalse.s loc_4AE1
0x4acc  ldstr    aXsltReservedns// "Xslt_ReservedNS"
0x4ad1  ldc.i4.1
0x4ad2  newarr   [mscorlib]System.String
0x4ad7  dup
0x4ad8  ldc.i4.0
0x4ad9  ldarg.1
0x4ada  stelem.ref
0x4adb  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x4ae0  throw
0x4ae1  newobj   instance void System.Xml.Xsl.XsltOld.PrefixQName::.ctor()
0x4ae6  stloc.0
0x4ae7  ldloc.0
0x4ae8  ldarg.0
0x4ae9  callvirt instance void System.Xml.Xsl.XsltOld.PrefixQName::SetQName(string qname)
0x4aee  ldloc.0
0x4aef  ldarg.1
0x4af0  brtrue.s loc_4B00
0x4af2  ldarg.2
0x4af3  ldloc.0
0x4af4  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Prefix
0x4af9  callvirt instance string System.Xml.Xsl.XsltOld.InputScopeManager::ResolveXPathNamespace(string prefix)
0x4afe  br.s     loc_4B01
0x4b00  ldarg.1
0x4b01  stfld    string System.Xml.Xsl.XsltOld.PrefixQName::Namespace
0x4b06  ldloc.0
0x4b07  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Prefix
0x4b0c  ldstr    aXml// "xml"
0x4b11  ldc.i4.4
0x4b12  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4b17  brfalse  loc_4BAC
0x4b1c  ldloc.0
0x4b1d  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Prefix
0x4b22  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b27  ldc.i4.3
0x4b28  bne.un.s loc_4B68
0x4b2a  ldloc.0
0x4b2b  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Namespace
0x4b30  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x4b35  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4b3a  brfalse.s loc_4B60
0x4b3c  ldloc.0
0x4b3d  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Name
0x4b42  ldstr    aLang// "lang"
0x4b47  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4b4c  brtrue.s loc_4BAC
0x4b4e  ldloc.0
0x4b4f  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Name
0x4b54  ldstr    aSpace// "space"
0x4b59  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4b5e  brtrue.s loc_4BAC
0x4b60  ldloc.0
0x4b61  callvirt instance void System.Xml.Xsl.XsltOld.PrefixQName::ClearPrefix()
0x4b66  br.s     loc_4BAC
0x4b68  ldloc.0
0x4b69  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Prefix
0x4b6e  ldstr    aXmlns// "xmlns"
0x4b73  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4b78  brfalse.s loc_4BAC
0x4b7a  ldloc.0
0x4b7b  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Namespace
0x4b80  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x4b85  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4b8a  brfalse.s loc_4BA6
0x4b8c  ldstr    aXsltInvalidpre// "Xslt_InvalidPrefix"
0x4b91  ldc.i4.1
0x4b92  newarr   [mscorlib]System.String
0x4b97  dup
0x4b98  ldc.i4.0
0x4b99  ldloc.0
0x4b9a  ldfld    string System.Xml.Xsl.XsltOld.PrefixQName::Prefix
0x4b9f  stelem.ref
0x4ba0  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x4ba5  throw
0x4ba6  ldloc.0
0x4ba7  callvirt instance void System.Xml.Xsl.XsltOld.PrefixQName::ClearPrefix()
0x4bac  ldloc.0
0x4bad  ret
```
